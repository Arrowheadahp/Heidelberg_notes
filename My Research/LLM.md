## Large Language Models
This is the brain of of [[Agent]]. During inference it repeatedly ==predicts the next token to be used==. It cannot do anything else. It keeps on generating tokens until the EOS token is reached.
### Training
This breaks language and other media into chunks or ==tokens== and then encodes. It is trained to predict the next token coming using the representation of the last transformed token. Most of the LLMs use [[Transformer]] for their training and inference and is trained to minimize the [[Cross Entropy]] loss.
### Inference
During inference all it does is next token prediction according to a temperature hyperparameter. 

![How Large Language Model](https://youtu.be/LPZh9BOjkQs?si=UBFv9eW0VNbiPcd3)

### Examples of LLMs
1. GPT3.5
2. Claude sonnet 5.5
3. GLM3.5
4. Gemini 3.8