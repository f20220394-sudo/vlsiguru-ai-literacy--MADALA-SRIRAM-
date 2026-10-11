# Week 01 — AI Verification Log

## Objective
The objective of this activity is to check whether an AI-generated answer is correct, complete, and supported by reliable evidence.

## Experiment 1: Can an AI Sound Confident and Still Be Wrong?

**Prompt used:**

"Does a fluent and confident answer from a large language model guarantee that the information is correct?"

**AI answer summary:**

A language model can generate fluent and convincing text, but fluency does not guarantee factual accuracy. Some answers may contain incorrect or unsupported information.

**Verification source:**

OpenAI — How ChatGPT and our foundation models are developed  
https://openai.com/index/how-chatgpt-and-our-foundation-models-are-developed/

**Verification method:**

I compared the general claim with the source's explanation of how language models generate responses. The source helps explain the generation process, but it does not independently verify every possible answer.

**Result:** The claim that confidence guarantees correctness is not valid.

**Lesson learned:**

AI-generated answers should be checked against reliable sources. A convincing explanation is not a substitute for evidence.

## Experiment 2: How Does an LLM Generate Text?

**Question:** Does an autoregressive language model generate text by predicting tokens sequentially?

**Verification source:**

Vaswani et al., *Attention Is All You Need*  
https://arxiv.org/abs/1706.03762

**Verification method:**

I reviewed the research paper's description of the Transformer architecture and compared it with the simplified explanation of next-token generation.

**Result:** The paper supports the use of Transformer architectures in sequence-processing tasks. The next-token explanation is a simplified mental model and should not be treated as a complete description of every language model.

**Lesson learned:**

Technical explanations should be checked against appropriate documentation, and the limitations of a source must be understood.

## Personal verification record

**Claim checked:** A fluent AI-generated answer is not automatically guaranteed to be correct.

**Source inspected:** The official OpenAI explanation of ChatGPT and its foundation models, or another relevant official source I actually reviewed.

**Evidence recorded:** I checked the source to understand how ChatGPT works and compared its explanation with the claim. A general description of how a language model works does not prove that every individual response is correct.

**Final result:** I learned that important AI-generated claims need to be checked against relevant evidence instead of being accepted solely because they sound convincing.
