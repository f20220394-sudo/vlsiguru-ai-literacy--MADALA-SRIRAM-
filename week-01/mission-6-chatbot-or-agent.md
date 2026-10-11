# Mission 6 — Chatbot or Agent?

## Comparison table

| Term | Meaning | Example |
|---|---|---|
| LLM | A model trained to process and generate language | A language model drafting an explanation |
| AI application | A product or program that uses one or more AI capabilities | A study assistant app |
| RAG (retrieval-augmented generation) | Retrieves relevant information and supplies it to a model to help answer a question | A chatbot that searches a course PDF before answering |
| Tool-using assistant | A model-based assistant that can call defined tools, such as a calculator or search function | An assistant that calculates a result with a calculator tool |
| Agent | A system that can select and carry out steps toward a goal, often using tools and feedback, within its designed permissions | A travel-planning workflow that checks options and prepares an itinerary for user review |

The exact boundary between “assistant” and “agent” varies across systems and definitions. Tool access alone does not automatically make a system fully autonomous.

## Simple flow diagram

```text
User request
    ↓
Model interprets the request
    ↓
Does it need information or a tool?
    ├── No → Draft response
    └── Yes → Retrieve information / call an allowed tool
                         ↓
                  Observe the result
                         ↓
              Model checks next step
                         ↓
                Final response or action
```

## Everyday agentic-workflow example

A calendar-planning assistant could inspect a user's permitted availability, identify possible meeting slots, draft an invitation, and ask the user to approve it before sending. The workflow involves multiple steps and tools. In a real system, permissions and confirmation requirements matter.

## Key distinction

A basic chatbot may only respond to the current message. A RAG system adds retrieval, a tool-using assistant can invoke specific functions, and an agent-like workflow can plan and execute multiple steps toward a goal. These are overlapping design patterns rather than perfectly exclusive categories.
