 Leak Detection and Localization in Water Distribution Networks using Graph Neural Networks
 Project Overview

This project investigates leak detection and localization in water distribution networks (WDNs) using Graph Neural Networks (GNNs).
The water network is modeled as a graph where:

nodes represent junctions,

edges represent pipes,

node features consist of pressure/flow-based measurements obtained from hydraulic simulations.

The objective is to identify the most probable leak location given network-wide sensor measurements.

Motivation

Leak localization in WDNs is a challenging inverse problem due to:

hydraulic nonlinearity,

pressure propagation effects,

topological symmetry leading to ambiguous signatures.

Traditional machine learning methods struggle to incorporate network topology explicitly.
Graph Neural Networks provide a natural framework to encode spatial and relational information inherent in WDNs.

Methodology Overview

Simulate leak scenarios using EPANET

Extract pressure/flow-based node features

Represent the WDN as a graph

Train a GNN to classify the leak location

Evaluate performance across multiple benchmark networks

Experimental Progression

This project was intentionally developed incrementally, with each stage revealing new insights.

Stage 1: Net1

Purpose: Validate correctness of pipeline

Characteristics:

Small network

Low topological symmetry

Clear pressure signatures

Outcome:

High classification accuracy

Fast convergence

Insight:

Confirmed that GNNs can learn pressure propagation patterns

Net1 served as a proof-of-concept rather than a realistic benchmark.

Stage 2: Net2 

Purpose: Test robustness on a more realistic network

Challenges observed:

Symmetric junctions

Similar pressure signatures for different leak locations

Outcome:

Top-1 accuracy plateaued around 50–60%

Key Insight:

The inverse problem is not uniquely solvable from single-snapshot pressure data

Performance is limited by hydraulic observability, not model capacity

This stage was critical in understanding physics-imposed limits.

Stage 3: rede-sub-a-alt Network 

Purpose: Investigate effect of network topology on performance

Approach:

Used rede-sub-a-alt.inp EPANET model

Generated a fresh dataset using the same simulation pipeline

Outcome:

Test accuracy reached ~90%

Reason:

Reduced symmetry

Better hydraulic distinguishability

Conclusion:

Leak localization performance depends strongly on network structure

Results Summary
Network	Characteristics	Test Accuracy
Net1	Small, simple	High
Net2	Symmetric, ambiguous	~0.5–0.6
rede-sub-a-alt	Well-conditioned	~0.90
