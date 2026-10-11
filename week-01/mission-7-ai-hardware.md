# Mission 7 — What Actually Runs AI?

## Answers

### 1. What is a CPU good at?
A CPU is a general-purpose processor designed to run a wide range of operating-system and application tasks. It is flexible and good at coordinating work, handling control flow, and executing many kinds of sequential or moderately parallel operations.

### 2. What is a GPU and why is it useful for AI?
A GPU contains many processing units designed to perform many similar operations in parallel. Neural-network workloads often involve large matrix and tensor operations, so suitable GPUs can process these operations efficiently.

### 3. What is an NPU / AI accelerator?
An NPU or AI accelerator is specialized hardware designed to speed up common neural-network operations with particular performance or energy-efficiency goals. Capabilities vary by chip.

### 4. What is parallel computation?
Parallel computation means carrying out multiple operations at the same time, rather than completing every operation one after another. Not every part of an AI workload can be parallelized equally.

### 5. Why do AI systems depend on compute and memory?
Models require computation to perform operations and memory to store model parameters, inputs, intermediate values, and outputs. Data movement and memory capacity/bandwidth can become important performance limits as well as raw arithmetic speed.

### 6. Training versus inference
- **Training:** The model processes training data and updates parameters through an optimization process. It usually requires repeated computation across many examples.
- **Inference:** The trained model is used to produce predictions or generated outputs for new inputs. Large-model inference can still require substantial compute and memory.

## Hardware/software diagram

```text
AI Application
      ↓
AI Model
      ↓
Software / Framework
      ↓
CPU / GPU / AI Accelerator
      ↕
    Memory
```

The diagram is simplified: actual systems can move data between multiple memory levels and processors, and the application/framework may coordinate work across several devices.

## Real workload example

**Workload:** Generating a response with a large language model.

A GPU or purpose-built AI accelerator can be useful because model inference relies heavily on matrix/tensor operations. Memory is also important because model parameters and intermediate data must be accessible during generation. A CPU may coordinate the application, handle requests, and perform other general-purpose tasks.

## Engineering takeaway

AI is software running on a physical computing system. Performance depends on the model and algorithm as well as the processor, parallelism, memory capacity, memory bandwidth, and software implementation.
