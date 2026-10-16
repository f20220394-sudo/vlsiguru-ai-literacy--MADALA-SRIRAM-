# Mission 1 — Build the AI and ML Landscape

## 1. What is AI?
Artificial intelligence (AI) is the broad field of creating computer systems that perform tasks associated with intelligent behaviour, such as recognising patterns, planning, understanding language, or making recommendations.

Machine learning is one part of AI. Instead of writing every decision as a fixed rule, an ML system uses examples to learn patterns that can help it make predictions on new examples.

## 2. Concept map

```text
Artificial Intelligence (AI)
├── Rule-based systems: people write explicit rules
└── Machine Learning (ML): patterns are learned from data
    ├── Supervised learning
    ├── Unsupervised learning
    ├── Reinforcement learning
    └── Deep learning: ML using multi-layer neural networks

Generative AI: systems that create content (text, images, audio, code)
└── Some generative AI systems use deep learning

Large Language Models (LLMs)
└── Models trained to process and generate language; many modern LLMs
    use transformer architectures
```

This is a simplified map, not a strict tree in which every term is the same kind of category. Generative AI describes a capability, deep learning describes a family of model methods, and LLM describes a type of language model.

## 3. Five distinctions

1. **AI vs ML:** AI is the broad field; ML is a family of approaches within it.
2. **Rule-based programming vs ML:** In a rule-based program, developers write the decision rules. In ML, a training procedure learns patterns from examples.
3. **ML vs deep learning:** Deep learning is a subset of ML that uses neural networks with multiple layers.
4. **Generative AI vs LLM:** Generative AI can create different types of content. An LLM is focused on language and is one possible technology behind generative systems.
5. **Automation vs AI:** Automation means a task runs with less human intervention. A timer or fixed script can automate a task without learning or intelligent pattern recognition. AI can also use rules without ML.

## 4. Three examples and classifications

| Example | Classification | Reason |
|---|---|---|
| A script sends a report every day at 9 a.m. | Automation, not necessarily AI | It follows a fixed schedule and does not learn from examples. |
| A program applies hand-written rules to flag a voltage above a specified limit | Rule-based program; may be considered a simple AI system in some contexts, but not ML | The threshold is explicitly programmed. |
| A model learns from historical chip measurements to predict whether timing will pass | ML, specifically supervised classification if the target is pass/fail | It learns a relationship from labelled examples. |

## 5. What is programmed and what is learned?
People define the objective, collect and prepare data, select a learning method, choose evaluation metrics, and set deployment constraints. During training, the algorithm adjusts model parameters based on data and an optimisation procedure. The learned model then uses those parameters during inference. The model does not automatically know whether its predictions are correct in every new situation.

## 6. Limitations
An ML system can learn misleading patterns if the data is poor, biased, or different from the real use case. A good result on historical examples does not prove that the system will work reliably in every environment.

## Sources to consult
- Google, Introduction to Machine Learning: https://developers.google.com/machine-learning/intro-to-ml
- IBM, What is machine learning?: https://www.ibm.com/think/topics/machine-learning

