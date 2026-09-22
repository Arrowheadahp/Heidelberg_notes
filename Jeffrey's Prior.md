#aigenerated 
# Jeffreys' Prior — an intuitive rediscovery (Q39)

## Setup: what is "uninformed", really?

Bayesian inverse problem: $p(f \mid g) \propto p(g \mid f)\, p(f)$. When you know nothing about $f$, you want a prior that adds *no* information. The naive candidate: "uniform = max ignorance."

## The paradox that breaks uniform (rediscover it yourself)

Suppose you know nothing about a **rate/length-scale** parameter $\theta > 0$ — say, theflug intensity of a radioactive source, or the width of a blur kernel. You write down: *uniform on $\theta$*: $p(\theta) \propto 1$ on $[1, 10]$.

**But "theta" wasn't sacred — it was a choice.** Physicists parameterise rates by their rate constant $\theta$ *or* by the **decay time** $\tau = 1/\theta$. If you're truly ignorant, your answer must not depend on that reparameterisation. Now check:

$$p_u(\theta) \propto 1 \quad\Rightarrow\quad p_u(\tau) = p_u(\theta)\left|\frac{d\theta}{d\tau}\right| = \frac{1}{\tau^2} \neq \text{const}.$$

The same ignorance变成了 $\tau$-density $1/\tau^2$ — *not* uniform. So the uniform prior secretly asserts "short lifetimes are much more likely than long ones." **Contradiction in terms: a uniform prior is only uniform in one particular coordinate system; it is informative in every other.** (This is the Visit-the-Informant / Bertrand-style paradox flavour of the [principle of indifference](https://en.wikipedia.org/wiki/Principle_of_indifference) failing.)

Your Fisher information is $\mathcal{I}(\theta) = \mathbb{E}\!\left[(\partial_\theta \log p(g\mid\theta))^2\right]$ — then $\sqrt{\mathcal I}$ transforms *exactly* like a density under a change of variables: that's the **only(ish)** function that does this, and it solves the invariance equation. So:

## Jeffreys' construction: invariance as a design requirement

**Harold Jeffreys** (*Theory of Probability*, 1939 — earlier germs in his 1931/1932 work with Dorothy Wrinch on scientific inference) asked: can we pick a prior policy $p$ that is **consistent under reparameterisation**? The requirement:

$$p(\theta)\,d\theta = p(\phi)\,d\phi \quad\text{whenever}\quad \phi = \phi(\theta),$$

i.e. the prior as a *measure* must transform correctly. Jeffreys identified the (unique, up to constants) solution:

$$\boxed{\; p_J(\theta) \;\propto\; \sqrt{\det \mathcal{I}(\theta)} \;}$$

**Intuition for the formula:** $\mathcal I(\theta)$ measures "how loudly the data speak at this $\theta$" — how much information each additional observation carries. Where the likelihood is *sharp* (data constrain $\theta$ tightly), the prior should be *soft* (get out of the way); where the likelihood is *flat/vague*, the prior may lean in without corrupting conclusions. $\sqrt{\mathcal I}$ does exactly this — and it's precisely the transformation law (Jacobian) of a density, which is why the invariance is automatic. Jeffreys called the uniform prior a "bogus" solution to the problem of ignorance for this exact reason.

## Examples you should have ready (exam!)

**1. Gaussian location $\mu$, known $\sigma^2$ (Day 4, Q31 setting — shot noise):**
$\mathcal I(\mu) = 1/\sigma^2$ — constant in $\mu$. So
$$p_J(\mu) \propto 1 \quad\text{(flat!)}$$
✅ **Uniform IS the Jeffreys prior here.** Your instinct was right — but only in a *location* parameter.

**2. Gaussian scale $\sigma$, known $\mu$:**
$\log p = -\log\sigma - (g-\mu)^2/2\sigma^2 \Rightarrow \mathcal I(\sigma) = 2/\sigma^2$, so
$$p_J(\sigma) \propto \frac{1}{\sigma} \qquad \left(= \frac{1}{\sigma^2} \text{ if you instead treat } \sigma^2 \text{ as the parameter}\right)$$
NOT flat. Flat-on-$\sigma$ and flat-on-$\sigma^2$ are *different, mutually inconsistent* claims — Jeffreys resolves this arbitrariness. (In log-coordinates this is just $p(\log\sigma) =$ const — the natural "scale-free" statement: I'm equally ignorant across decades.)

**3. Poisson rate $\lambda$ (your counting-data friend from RL):**
$\mathcal I(\lambda) = 1/\lambda \Rightarrow p_J(\lambda) \propto 1/\sqrt{\lambda}$ — the [neutral prior](https://en.wikipedia.org/wiki/Jeffreys_prior) for how much of today's dose you get. The famous **Jeffreys prior / uniform → same posterior when data dominate**: with even a handful of counts, the likelihood swamps the prior difference. 🎓 Note $\int_0^\infty \lambda^{-1/2}d\lambda$ diverges (improper prior) — that's fine, the posterior is still proper as long as data arrive.

**Inverse-problem form** (generic matrix problem, per the slides in `3.2-detstochmet3.pdf` §80–83):
$$p_J(f)\;\propto\;\sqrt{\det\big(\bar A^\top \bar A\big)}$$
the determinant of the Fisher information of the Gaussian observation model — the geometric "volume-distortion" of how the forward operator squashes probability mass.

## The broader takeaway (state this in the exam)

The uniform prior fails because **"uninformative" is not coordinate-free.** Jeffreys' principle: pick the prior whose *invariance group* matches the problem's reparameterisation symmetry, with $\sqrt{\det\mathcal I}$ as the unique solution. Uniform is fine (and correct) for **location** parameters like $\mu$ with fixed noise; it is actively misleading for **scale/rate** parameters like $\sigma$, $\lambda$, $\tau$ — where ignorance lives in *log-space*, and flatness in a linear coordinate silently encodes an unphysical preference.

---

**Retrieval check, from memory:** (1) Why does uniform-on-$\theta$ imply non-uniform-on-$1/\theta$, and why is that a *logical* failure rather than a modelling choice? (2) State Jeffreys' formula and the intuition "data speak loudly → prior steps back." (3) What does $p_J$ become for Gaussian $\mu$, for Gaussian $\sigma$, for Poisson $\lambda$? If any piece shakes loose, revisit lesson [0004-bayes-poisson-iterative.html](lessons/0004-bayes-poisson-iterative.html) §10 and the [glossary](reference/glossary.html) entry, then try to re-derive $\mathcal I(\sigma) = 2/\sigma^2$ with pen and paper before checking.