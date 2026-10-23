# AI Tools Exploration

## 1. Objective

The objective of this activity is to explore AI tools for engineering learning, improve prompts, compare AI-generated explanations, and verify technical claims using reliable sources.

## 2. AI Tools Explored

### ChatGPT

ChatGPT can help explain DFT concepts, organise technical information, improve prompts, and provide examples for digital design and Python programming.

### Google Gemini

Gemini can provide alternative explanations of engineering concepts, help organise information, and support technical learning through examples.

### Claude

Claude is an AI assistant that can support technical explanations, document analysis, writing, and coding.

### NotebookLM

NotebookLM helps users study provided sources, summarise documents, and ask questions grounded in reference material.

### Perplexity

Perplexity supports web research and helps users discover sources that can be checked against original documentation.

The descriptions of Claude, NotebookLM, and Perplexity are introductory observations. I should record direct testing only for tools I have actually used.

## 3. Prompt Engineering Experiment

### Basic Prompt

Explain DFT in VLSI.

### Improved Prompt

I am a BTech ECE student specialising in VLSI Design for Test (DFT). Explain DFT in beginner-friendly language. Cover scan chains, controllability, observability, automatic test pattern generation (ATPG), and fault coverage. Explain the purpose of each concept and provide one simple example. Use clear headings and keep the explanation concise.

### Observation

The improved prompt specifies my educational background, specialisation, required concepts, examples, and preferred output format. This gives the AI a clearer direction and can produce a more structured explanation.

## 4. Comparison of ChatGPT and Google Gemini

### Task

Ask both tools the following question:

"What is a scan chain in DFT, and how does it help test a digital circuit?"

### Comparison

| Criterion | ChatGPT | Google Gemini |
|---|---|---|
| Main concept | Explain scan chains and their purpose | Explain scan chains and their purpose |
| Technical detail | Check how it explains scan flip-flops and shifting | Check how it explains scan flip-flops and shifting |
| Examples | Record the example provided | Record the example provided |
| Structure | Evaluate clarity and organisation | Evaluate clarity and organisation |
| Follow-up learning | Check whether further explanations are useful | Check whether further explanations are useful |

### Comparison Findings

A scan chain connects scan-enabled flip-flops so that test data can be shifted into internal registers and circuit responses can be shifted out. This improves access to internal states during testing.

The comparison should be completed using the actual responses from both tools. I should record their differences in explanation, examples, and technical detail rather than assume that one tool is always better.

## 5. Verification of a Technical Claim

### Claim

Yosys is an open-source framework for Verilog RTL synthesis.

### Official Sources

- Yosys official website: https://yosyshq.net/yosys/
- Yosys official GitHub repository: https://github.com/YosysHQ/yosys

### Verification Process

1. Open the official Yosys website.
2. Read the project overview.
3. Check the official GitHub repository and documentation.
4. Identify the description of its RTL synthesis capabilities.
5. Compare the evidence with the original claim.

### Verification Result

The official Yosys project documentation describes Yosys as an open-source RTL synthesis framework with support for synthesizable Verilog. This supports the claim.

Source: https://github.com/YosysHQ/yosys

### Relevance to DFT

RTL synthesis is part of the digital design workflow. Understanding synthesis helps explain how a design moves from an RTL description toward a netlist that may be used in subsequent implementation and test-related activities.

Yosys synthesis alone should not be assumed to provide every capability required for a complete production DFT flow.

## 6. Responsible AI Usage

- Check technical claims against official documentation.
- Do not assume a confident answer is automatically correct.
- Avoid uploading confidential RTL, netlists, or proprietary design information to public AI tools.
- Review and test AI-generated code before using it.
- Record the actual results of experiments.
- Understand and explain the work in my own words.

## 7. Conclusion

This activity helped me understand how clear prompts can improve AI-generated explanations. Comparing AI tools can reveal differences in structure, examples, and technical detail. Independent verification remains essential when learning engineering concepts and investigating open-source tools.
