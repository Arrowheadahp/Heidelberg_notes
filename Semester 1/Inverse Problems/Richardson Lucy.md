#aigenerated
# Richardson–Lucy (RL) — exam-ready explanation (Q36/Q37)

## The setting

Linear inverse problem with **Poisson noise**:

$$g_i \sim \text{Poisson}\left( \sum_j A_{ij} f_j \right), \qquad i = 1,\dots,m$$

This is the physical model of **counting experiments**: photon-limited imaging, PET/SPECT emission tomography, fluorescence microscopy, gamma-ray astronomy. The count $g_i$ in detector pixel $i$ is Poisson-distributed with mean given by the blurred/blurred-and-mixed signal $\sum_j A_{ij} f_j$. Crucially, **least squares is the wrong data misfit here** — the ML fit for Poisson noise is instead:

$$D_{KL}(g, Af) = \sum_i \Big[ (Af)_i - g_i \log\big((Af)_i\big) + \log g_i! \Big],$$

i.e. the KL divergence between the data $g$ and the model prediction $Af$ (Day 4, Q32/Q34 — you already derived this from the Poisson log-likelihood).

## The iteration (memorise this form)

$$\boxed{\; f_j^{\,\text{new}} = \frac{f_j^{\,\text{old}}}{\sum_i A_{ij}} \sum_i A_{ij}\, \frac{g_i}{\sum_k A_{ik} f_k^{\,\text{old}}} \;}$$

Read it in words:
1. **Forward project** current estimate → predicted mean $(Af)_i$
2. **Ratio** the actual data against the prediction → $g_i / (Af)_i$ (a "correction image")
3. **Back-project** those ratios through $\bar A$ (adjoint/transposed system matrix), weighting by $A_{ij}$
4. **Normalise** by the column sums $\sum_i A_{ij}$ (interpretable: each update is the *conditional expected value* of $f_j$ given the data — an EM step)
5. Repeat

Two structural properties you must state in the exam:
- It is **multiplicative** (a correction factor multiplies the current estimate), so $f^{(0)} > 0 \Rightarrow f^{(k)} > 0$ for all $k$ — **positivity is preserved by construction**, no projection needed.
- Each iteration **increases the Poisson log-likelihood** (monotone), and it is exactly the **EM (expectation–maximisation) algorithm** specialised to the Poisson/emission-tomography case (slides §58–77).

## How it was found

Two independent derivations, ~18 years apart, both astronomically motivated:
- **William Hadley Richardson (1972)**: derived the iteration *purely algebraically* as an iterative method to "deconvolve" — he noticed this multiplicative scheme has a fixed point at the least-squares/Poisson solution and converges under conditions.
- **Leon Lucy (1974)**, [Astron. J. 79:745](https://ui.adsabs.harvard.edu/abs/1974AJ.....79..745L/abstract): derived an *identical* iteration from a **probabilistic argument** (maximising Poisson likelihood), which is why the derivation holds up theoretically.
- The modern theoretical grounding came in the 1980s via **Dempster–Laird–Ruberin's EM algorithm (1977)** and especially **Shepp & Vardi (1982)**, who showed RL is EM applied to maximum-likelihood reconstruction in PET. That's the "hidden" view: the missing data are the photon counts attributed to each source pixel; E-step assigns expected counts, M-step re-estimates $f_j$ as the conditional mean.

## Why RL is better than Landweber (Q37)

**Landweber** is plain **gradient descent on the least-squares data term** $\tfrac12\|\bar Af - \bar g\|^2$ with stepsize $0 < s < 2/\|\bar A\|^2$:

$$f^{(k+1)} = P_C\!\big(f^{(k)} - s(\bar A^\top \bar A f^{(k)} - \bar A^\top \bar g)\big)$$

Comparison (state all three):

| | Landweber | Richardson–Lucy |
|---|---|---|
| Noise model | Generic least squares (implicitly Gaussian) | **Correct Poisson ML** via KL data term |
| Positivity | Additive steps destroy it — needs POCS projection $P_C$ to patch it step-by-step | **Preserved by construction** (multiplicative) |
| Convergence | Slower here | **Faster** (demonstrated empirically by the provided `LandweberVsRichardsonLucy.py` — the RL MSE curve drops lower/faster) |

Deeper reason: Landweber minimises a *mis-specified* misfit for Poisson data. The Gaussian assumption heavily penalises high-count outliers and allows negative overshoots; RL's scaling-matched correction $g_i/(Af)_i$ is the statistically natural residual for counting noise (relative errors matter, not absolute). Note also the honest caveat you should know for transfer questions: RL *amplifies noise with iterations* — it needs early stopping or embedded regularisation (Q38) — but *given the correct noise model*, it's the right method.

Impact: this remains **the standard reconstruction algorithm** in PET/CT imaging, astronomy, and fluorescence microscopy (e.g. the dominant deconvolution option in ImageJ/Fiji), precisely because it respects photon-counting statistics and principal physics — all intensities stay non-negative.

---

**Retrieval check (answer from memory before rereading):** Can you reproduce the boxed update? Can you name the three reasons RL > Landweber? If either wobbles, revisit lesson [0004-bayes-poisson-iterative.html](lessons/0004-bayes-poisson-iterative.html) §7–9 and the question's [reference](all-questions-model-answers.md) entry, then try running `Inverse Problem Slides/LandweberVsRichardsonLucy.py` to see the convergence gap yourself.

Want a quiz loop on this, or shall I add anything (e.g. the Q38 regularised-RL form) to your answer prep?