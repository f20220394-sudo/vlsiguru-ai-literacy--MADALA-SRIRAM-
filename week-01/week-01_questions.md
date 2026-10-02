# Week 01 Assessment Solutions & Working Guide

## Artificial Intelligence, Machine Learning, Deep Learning, Generative AI, and AI Agents

## Q1. AIML → Deep Learning → Generative AI → AI Agents

### A — Answer

Artificial Intelligence (AI) is a branch of computer science that focuses on developing systems capable of performing tasks that normally require human intelligence, such as reasoning, learning, problem-solving, and decision-making.

Machine Learning (ML) is a subset of AI that enables computers to learn patterns from data and make predictions or decisions without requiring programmers to define every rule manually.

Deep Learning (DL) is a subset of machine learning that uses artificial neural networks with multiple layers to identify complex patterns in data such as images, speech, and text.

Generative AI (GenAI) refers to AI systems that create new content, including text, images, audio, videos, and computer code, based on patterns learned during training.

AI Agent is a system that uses AI models, tools, and feedback to work toward a specific goal. Depending on its design, it can plan tasks, gather information, make decisions, and perform actions with limited human supervision.

### Relationship Between These Concepts

Artificial Intelligence (AI)

Machine Learning (ML)

Deep Learning (DL)

Generative AI

AI Agent: A system that can use AI models and tools to accomplish goals

GenAI is commonly built using deep learning. AI agents are a system-level concept and can use different kinds of AI models and tools.

### Real-Life Examples

1. AI: A computer program that plays chess.

2. ML: An email application that identifies spam messages using learned patterns.

3. DL: A facial recognition system that identifies a person from an image.

4. GenAI: An application that writes an email or creates an image from a text prompt.

5. AI Agent: A customer support system that checks an order, initiates an eligible refund, and sends a confirmation.

### E — Evidence

AI, ML, and DL are related fields with different scopes. Generative AI commonly uses deep neural networks, while agents combine models with additional software components to perform tasks.

### V — Verification

The definitions can be compared with established AI textbooks, machine learning references, and official technical documentation.

### R — Reflection

Understanding these concepts helps distinguish systems that follow fixed rules, models that learn patterns, tools that generate content, and agents that perform actions. An AI model does not automatically become an agent simply because it produces intelligent responses.

## Q2. Is Everything That Looks Intelligent Actually AI?

### A — Answer

Not every system that appears intelligent uses artificial intelligence. Some applications operate through predefined instructions, while others use models trained on data.

| Scenario                                       | Classification                       | Explanation                                                                 |
| ---------------------------------------------- | ------------------------------------ | --------------------------------------------------------------------------- |
| Calculator computing 25 × 16                   | Traditional software                 | Performs arithmetic using predefined operations.                            |
| Temperature alarm activated above 80°C         | Rule-based software                  | Compares the temperature against a fixed threshold.                         |
| Email spam detection                           | Machine learning, if trained on data | Identifies patterns associated with spam and legitimate emails.             |
| Automatic text summarizer using an LLM         | Generative AI                        | Produces a shorter version of the supplied text.                            |
| Navigation application estimating arrival time | Often machine learning-based         | May use historical traffic, current road conditions, and prediction models. |

### Traditional Programming vs. Artificial Intelligence

Traditional programming: A developer writes explicit instructions describing what the program should do.

Example:

Python

Run

```
temperature = 85

if temperature > 80:
    print("Warning: High temperature")
else:
    print("Temperature is normal")
```

Machine learning: A model learns statistical relationships from training examples and applies them to new inputs.

For example, a spam filter can learn from previously labeled emails instead of relying exclusively on manually written keyword rules.

### E — Evidence

The distinction depends on how a system works internally, rather than how intelligent its output appears.

### V — Verification

To classify a system correctly, examine whether it uses fixed instructions, learned model parameters, or a combination of both.

### R — Reflection

Simple software can solve many problems efficiently without AI. Machine learning is particularly useful when identifying patterns from complex data is more practical than writing rules for every possible situation.

## Q3. What Happens When You Ask a Large Language Model a Question?

### A — Answer

A Large Language Model (LLM) processes a prompt and generates a response through several computational steps.

1. Tokenization: The input text is converted into tokens, which may represent words, word fragments, punctuation, or other text units.

2. Context preparation: The tokens are combined with relevant conversation history and applicable instructions.

3. Model processing: The neural network processes the input using learned parameters and attention mechanisms.

4. Probability calculation: The model calculates a probability distribution over possible next tokens.

5. Token selection: A decoding procedure selects the next token based on the distribution and generation settings.

6. Repeated generation: The selected token is added to the sequence, and the process repeats until a stopping condition is reached.

7. Response delivery: The resulting token sequence is converted into text and presented to the user.

### LLM Processing Flow

User enters a prompt

Text is converted into tokens

Model processes the context

Next-token probabilities are calculated

A token is selected

Generation repeats until completion

Final response is displayed

### Training vs. Inference

* Training: The model's parameters are adjusted using training data to learn statistical patterns.

* Inference: The trained model processes a new prompt to generate an output.

### Why Can an LLM Produce Incorrect Information?

An LLM generates text based on learned patterns and the supplied context. It does not automatically verify every statement against an authoritative database. Consequently, a response may sound convincing while containing incorrect information.

### E — Evidence

Transformer architectures and autoregressive language-modeling methods provide the technical foundation for many modern LLMs.

### V — Verification

The explanation can be checked against the research paper Attention Is All You Need and official documentation describing language-model inference.

### R — Reflection

Fluent language is not proof of factual accuracy. Important technical claims should be checked against reliable documentation, and generated code should be tested before use.

## Q4. Hallucination Experiment: Can AI Sound Confident and Still Be Wrong?

### A — Answer

An AI hallucination occurs when an AI system produces information that is incorrect, fabricated, or unsupported by the available evidence.

Consider the following experiment.

| Question                                   | Example AI Response                                | Verification                                                | Result                  |
| ------------------------------------------ | -------------------------------------------------- | ----------------------------------------------------------- | ----------------------- |
| What is the speed of light in a vacuum?    | Approximately 186,282 miles per second             | Compare with the defined speed of light and convert units.  | Correct approximation   |
| Who wrote a fictional research paper?      | The model supplies an author and publication year. | Search scholarly databases and publisher records.           | Must be verified        |
| What does a specific software function do? | The model describes its behavior.                  | Check the official API documentation and test the function. | Depends on the evidence |

The speed of light in a vacuum is exactly 299,792,458 metres per second. Its equivalent in miles per second is approximately 186,282.397.

### Why Do Hallucinations Occur?

* The model may generate a plausible continuation without sufficient factual support.

* The prompt may be ambiguous or missing essential information.

* The model may lack access to current information.

* The training data may contain errors or conflicting statements.

* The model may combine unrelated facts into an incorrect answer.

### E — Evidence

A reliable hallucination experiment compares a model's claims with independent evidence, such as scientific standards, original publications, and official documentation.

### V — Verification

Check each claim individually rather than accepting an entire response because some of its statements are correct.

### R — Reflection

Confidence, grammar, and presentation style do not guarantee correctness. Independent verification is necessary whenever an incorrect answer could affect a decision or technical outcome.

## Q5. AI Assistant vs. Search Engine vs. Authoritative Reference

### A — Answer

Different information sources serve different purposes. An AI assistant synthesizes information, a search engine helps discover sources, and an authoritative reference provides documented information within a defined scope.

| Feature             | AI Assistant                         | Search Engine                  | Authoritative Reference                        |
| ------------------- | ------------------------------------ | ------------------------------ | ---------------------------------------------- |
| Main purpose        | Explain and generate content         | Find relevant information      | Provide documented facts or specifications     |
| Explanation         | Usually conversational               | Depends on the pages found     | Often technical and precise                    |
| Traceability        | Depends on available citations       | Links to source pages          | Usually includes identifiable documentation    |
| Current information | Depends on model and available tools | Can locate recent publications | Depends on the publication and revision date   |
| Main limitation     | May generate unsupported claims      | May surface unreliable sources | May require specialized knowledge to interpret |

### When Should Each Be Used?

* AI assistant: For learning concepts, brainstorming, drafting text, and understanding unfamiliar terminology.

* Search engine: For discovering recent publications, websites, documentation, and different perspectives.

* Authoritative reference: For confirming technical specifications, standards, legal requirements, and safety-related information.

An authoritative source is not automatically infallible. Its relevance, publication date, scope, and reliability must still be assessed.

### E — Evidence

The comparison is based on the different functions of content-generation systems, information-retrieval systems, and primary technical references.

### V — Verification

Compare AI-generated statements with the original documentation and confirm that the source directly supports the claim.

### R — Reflection

AI tools can accelerate research, but engineers remain responsible for checking sources and establishing that the evidence supports their conclusions.

## Q6. What Is an AI Agent?

### A — Answer

An AI agent is a system designed to pursue a goal by using an AI model, available tools, observations, and an execution process. Some agents operate independently for several steps, while others require approval before performing important actions.

### Important Concepts

| Concept              | Meaning                                                                                              |
| -------------------- | ---------------------------------------------------------------------------------------------------- |
| LLM                  | A neural network trained to process and generate language.                                           |
| LLM application      | Software that connects a language model to an interface and other application features.              |
| RAG system           | Retrieval-Augmented Generation, which retrieves relevant information and supplies it to a model.     |
| Tool-using assistant | A system that can request actions through tools such as calculators or APIs.                         |
| AI agent             | A goal-oriented system that can coordinate model reasoning, tools, observations, and multiple steps. |

### AI Agent Workflow

User specifies a goal

Agent interprets the task and plans steps

Selects and calls an appropriate tool

Receives and evaluates the result

Completes the task or performs another step

### Example: Travel Planning Agent

Suppose a user requests a three-day trip within a budget of ₹25,000.

The agent could:

1. Collect travel dates and destination preferences.

2. Retrieve available transport and accommodation options.

3. Calculate estimated costs using a calculator.

4. Compare the results with the budget.

5. Revise the itinerary if the estimated cost exceeds the limit.

6. Present the proposed itinerary for review.

Bookings or payments should require appropriate authorization before execution.

### E — Evidence

Agent architectures commonly combine language models, tools, task orchestration, and feedback from external systems.

### V — Verification

A system should be evaluated for task completion, tool-call correctness, error recovery, and compliance with permission boundaries.

### R — Reflection

An LLM primarily processes and generates content. An agent uses a broader software workflow to achieve goals, which introduces additional concerns involving permissions, reliability, and unintended actions.

## Q7. Where Should Humans Still Make the Decision?

### A — Answer

Human oversight is important whenever AI-assisted decisions may significantly affect people's safety, rights, finances, or opportunities.

| Situation                           | Potential Risk                                | Verification Required                        | Human Responsibility                 |
| ----------------------------------- | --------------------------------------------- | -------------------------------------------- | ------------------------------------ |
| Safety-critical software deployment | Defects or security vulnerabilities           | Testing, code review, security analysis      | Authorized engineering reviewer      |
| Medical recommendations             | Incorrect interpretation or treatment advice  | Clinical evidence and qualified review       | Healthcare professional              |
| Legal document preparation          | Incorrect clauses or legal interpretation     | Current legislation and legal review         | Qualified legal professional         |
| Financial decisions                 | Incorrect assumptions or underestimated risks | Validated calculations and risk assessment   | Responsible financial decision-maker |
| Hiring and recruitment              | Bias or inaccurate candidate assessments      | Job-related evidence and fairness evaluation | Authorized hiring personnel          |

### Principles for Responsible AI Use

1. Treat AI-generated results as outputs that may require verification.

2. Match the level of review to the potential consequences of an error.

3. Test systems under realistic and unusual conditions.

4. Protect confidential and personal information.

5. Maintain records of significant decisions and verification steps.

6. Obtain human authorization for consequential actions when required.

### E — Evidence

Risk-management frameworks, including the NIST AI Risk Management Framework, provide guidance for identifying, assessing, and managing AI-related risks.

### V — Verification

A responsible deployment process should define review requirements, testing criteria, accountability, and escalation procedures before the system is used.

### R — Reflection

Human oversight is not simply a final formality. It should be incorporated into the design, testing, deployment, and monitoring of systems where failures could have serious consequences.

## Q8. Find AI Around You

### A — Answer

Many everyday applications use AI, while others rely on traditional programming. Some combine both approaches.

| Application                     | AI Involved?              | Possible Technique                                 | Alternative or Supporting Method                    |
| ------------------------------- | ------------------------- | -------------------------------------------------- | --------------------------------------------------- |
| Video streaming recommendations | Often yes                 | Recommendation models                              | Display popular content using fixed rankings        |
| Smartphone camera autofocus     | Depends on implementation | Computer vision or learned image-processing models | Contrast detection or phase-detection techniques    |
| Basic temperature thermostat    | Not necessarily           | A simple model is not required                     | Fixed temperature thresholds                        |
| Voice assistant                 | Commonly yes              | Speech recognition and learned wake-word detection | Limited command matching in controlled environments |
| Credit card fraud detection     | Often yes                 | Classification and anomaly detection               | Fixed transaction rules and thresholds              |

### E — Evidence

Product documentation, engineering publications, and technical descriptions can help establish which methods are used by a particular implementation.

### V — Verification

The presence of an AI-branded feature does not prove that every component uses machine learning. Confirm the actual implementation where possible.

### R — Reflection

Understanding AI in everyday applications helps identify where learned patterns provide benefits and where simpler, deterministic methods may be sufficient.

## Q9. Prediction, Classification, and Generation

### A — Answer

Machine learning and AI applications can be grouped by the type of output they produce. These categories can overlap, depending on the system's design.

| Task                                                     | Main Category                      | Explanation                                             |
| -------------------------------------------------------- | ---------------------------------- | ------------------------------------------------------- |
| Estimating a house's market price                        | Prediction / Regression            | Estimates a numerical value.                            |
| Determining whether an image contains a cat              | Classification                     | Assigns an image to a category.                         |
| Writing an email from an instruction                     | Generation                         | Produces new text.                                      |
| Estimating whether a customer will cancel a subscription | Classification / Prediction        | Estimates a churn probability or assigns a churn label. |
| Summarizing a research paper                             | Generation                         | Produces a shorter representation of the source.        |
| Identifying fraudulent transactions                      | Classification / Anomaly detection | Identifies transactions that may be fraudulent.         |
| Creating an image from a text description                | Generation                         | Produces new visual content.                            |
| Estimating the next token in a sentence                  | Prediction                         | Assigns probabilities to possible next tokens.          |

### Why Is Next-Token Prediction Important for LLMs?

Many autoregressive language models generate text by predicting one token at a time. This mechanism can support tasks such as summarization, translation, question answering, and code generation.

For example, when asked to summarize a paragraph, the model generates a new sequence of tokens that represents the main information in a shorter form.

However, not every AI system uses next-token prediction. Image generators, classifiers, and other models may use different architectures and objectives.

### E — Evidence

Machine learning textbooks describe regression, classification, and generative modeling as different approaches to learning and producing outputs.

### V — Verification

The classification of a task should be based on its intended output and the model's actual objective, not just the wording of the user request.

### R — Reflection

Recognizing the differences between prediction, classification, and generation helps select suitable methods and evaluate whether a system is producing the expected type of result.

## Q10. Design Your Personal AI Verification Protocol

### A — Answer

A personal AI verification protocol is a repeatable procedure for evaluating AI-generated information before using it in an assignment, program, or engineering task.

### Seven-Step Verification Process

Step 1: Define the problem

Specify the task, expected result, constraints, and success criteria.

Step 2: Identify assumptions

Determine whether the response depends on unstated conditions, missing inputs, or uncertain facts.

Step 3: Check reliable sources

Verify factual claims against official documentation, original research, or relevant standards.

Step 4: Test the output

Run generated code in a safe environment and check calculations with independent methods.

Step 5: Evaluate edge cases

Test missing values, unexpected inputs, boundary conditions, and failure scenarios.

Step 6: Accept, revise, or reject

Make a decision based on the evidence, test results, and requirements.

Step 7: Document the process

Record the prompt, generated output, sources checked, tests performed, and changes made.

### Worked Example: Verifying a Python CSV Parser

Suppose an AI generates a Python function that reads timestamps from a CSV file.

* Step 1: Define the requirement: read timestamps and convert them into valid date-time objects.

* Step 2: Identify assumptions: the generated function may assume a specific date format and column name.

* Step 3: Check the official Python documentation for the CSV and date-time functions used.

* Step 4: Run the function against a small sample file.

* Step 5: Test empty fields, malformed timestamps, missing columns, and duplicate rows.

* Step 6: Correct any errors and verify that the revised function meets the requirements.

* Step 7: Record the final code, test cases, results, and relevant documentation.

### E — Evidence

Software verification and validation practices provide a foundation for checking whether a solution meets its requirements and behaves correctly.

### V — Verification

A protocol is effective when it produces repeatable checks, identifies errors, and provides enough documentation for another person to review the results.

### R — Reflection

A structured verification process reduces dependence on the apparent confidence of AI-generated answers. It encourages evidence-based decisions, safer implementation, and greater accountability.

## Overall Conclusion

Artificial intelligence includes a range of techniques, from traditional rule-based systems to machine learning and generative models. AI agents extend these capabilities by coordinating models, tools, and multi-step workflows.

The key lesson from Week 01 is that AI-generated information should be evaluated according to evidence, testing, and the consequences of potential errors. Understanding how these systems work enables students and engineers to use them more effectively while retaining responsibility for the final result.
