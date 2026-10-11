# Mission 4 — How an LLM Produces an Answer

## Beginner explanation

A large language model (LLM) processes the prompt as tokens. During generation, it estimates a probability distribution over possible next tokens, selects a token according to its decoding settings, and repeats the process using the growing sequence. The selected tokens form the response.

For example, after the prompt “The sun rises in the…”, a language model may assign a high probability to “east.” It is not simply looking up a sentence in a database; it generates a sequence based on learned patterns and the context it receives. This process can produce useful explanations, but it can also produce inaccurate or unsupported claims.

## Two claims to check

1. **Claim:** GPT-style language models generate output by predicting next tokens.  
   **Verification source:** OpenAI, “How ChatGPT and our foundation models are developed” — https://openai.com/index/how-chatgpt-and-our-foundation-models-are-developed/  
   Check the current page and note the relevant passage before submission.

2. **Claim:** A transformer's attention mechanism helps the model use contextual relationships between tokens.  
   **Verification source:** Vaswani et al., “Attention Is All You Need” — https://arxiv.org/abs/1706.03762  
   Review the paper's abstract and model description before submission.

## What the AI explanation does well

The next-token description gives a useful beginner mental model of text generation and explains why the model produces a sequence one token at a time.

## What needs clarification

“Predicting the next token” is a simplified description, not the whole architecture. It does not by itself explain training, attention, tokenization, decoding settings, tool use, or the sources of factual errors. Also, a model's fluent response is not proof that the content is true.

## Final explanation in my own words

An LLM uses patterns learned during training and the current prompt to estimate what token should come next. It repeats this step to create an answer. The answer can sound confident even when it is wrong, so important claims must be checked against reliable sources or tested independently.
