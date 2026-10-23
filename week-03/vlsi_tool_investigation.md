# VLSI DFT Tool Investigation: Yosys

## 1. Tool Name

Yosys - Open-Source Verilog RTL Synthesis Framework

## 2. Introduction

Yosys is an open-source framework used for Verilog RTL synthesis. It processes hardware descriptions and transforms them into representations of a digital circuit.

Official Website: https://yosyshq.net/yosys/

GitHub Repository: https://github.com/YosysHQ/yosys

## 3. Relevance to My Track

My VLSI track is Design for Test (DFT). Yosys is relevant because it helps me understand RTL synthesis, which is an important part of the digital design workflow.

DFT techniques improve the testability of digital circuits. Examples include scan chains, controllability, observability, and automatic test pattern generation (ATPG).

Understanding RTL synthesis helps me understand how the design moves from a hardware description toward later implementation and test-related activities.

However, Yosys should not automatically be considered a complete production DFT solution.

## 4. Important Features

- Reads and processes supported Verilog designs.
- Performs RTL synthesis and logic transformations.
- Supports netlist processing and optimisation.
- Can generate synthesised netlists for supported flows.
- Supports mapping to suitable target cell libraries.
- Provides an open-source environment for learning and experimentation.

The exact capabilities depend on the design and synthesis configuration.

## 5. Basic RTL Synthesis Flow

1. Write a Verilog RTL design.
2. Read the Verilog design into Yosys.
3. Check and process the design.
4. Perform synthesis using appropriate commands.
5. Generate a synthesised netlist.
6. Inspect the synthesis results.
7. Understand how the resulting netlist relates to downstream implementation and test activities.

The exact flow depends on the design and target technology.

## 6. Relevance to DFT Concepts

### Scan Chains

Scan chains connect scan-enabled flip-flops so test data can be shifted into and out of internal registers.

### Controllability

Controllability describes how easily an internal circuit node can be set to a required logic value during testing.

### Observability

Observability describes how easily the effect of an internal circuit node can be observed at an output.

### Automatic Test Pattern Generation (ATPG)

ATPG generates test patterns intended to detect specified faults in a digital circuit.

### Fault Coverage

Fault coverage measures the proportion of the targeted faults detected by the applied test patterns, according to the selected fault model and evaluation method.

These are core DFT concepts. Investigating Yosys helps explain the synthesis stage, while additional appropriate tools or flows may be needed for scan insertion and ATPG.

## 7. Advantages

- Open-source software for learning and experimentation.
- Useful for understanding Verilog RTL synthesis.
- Helps connect digital design theory with netlist generation.
- Allows practice using simple, non-confidential Verilog examples.
- Can be used as a foundation for custom synthesis flows.

## 8. Limitations

- Yosys is primarily an RTL synthesis framework.
- Synthesis is not the same as a complete DFT flow.
- Scan insertion, ATPG, fault simulation, and fault-coverage analysis require appropriate additional capabilities or tools.
- Results depend on the design, configuration, and available technology libraries.
- Yosys is not a replacement for every commercial EDA tool.

## 9. Investigation Method

1. Visit the official Yosys website.
2. Read the project overview and documentation.
3. Identify its RTL synthesis capabilities.
4. Compare its role with the requirements of a DFT workflow.
5. Record the documentation evidence reviewed.
6. If possible, run a simple non-confidential Verilog example and record the actual output.

Related reference for scan insertion: https://openroad.readthedocs.io/en/latest/main/src/dft/README.html

The OpenROAD DFT documentation describes features such as scan replacement, scan-chain planning, and scan-chain stitching. These are separate capabilities and should not be attributed to Yosys alone.

## 10. Practical Activity Status

- Official website identified: Yes.
- Official GitHub repository identified: Yes.
- Documentation reviewed: Complete after reading the relevant pages.
- Yosys installed and tested: Record the actual result.
- Verilog example synthesised: Record the actual result, if completed.

## 11. Learning Outcome

This investigation helped me understand that RTL synthesis and DFT are related but different activities. Synthesis processes a hardware description, while DFT focuses on improving circuit testability.

I also learned that scan insertion and ATPG are specialised activities that may require additional tools and a suitable workflow.

## 12. References

1. Yosys official website: https://yosyshq.net/yosys/
2. Yosys GitHub repository: https://github.com/YosysHQ/yosys
3. OpenROAD DFT documentation: https://openroad.readthedocs.io/en/latest/main/src/dft/README.html

## Conclusion

Yosys is a useful open-source tool for learning RTL synthesis. Investigating it helps build a foundation for understanding the digital design flow and how it relates to DFT. Practical testing and further study of scan insertion and ATPG can extend this knowledge.
