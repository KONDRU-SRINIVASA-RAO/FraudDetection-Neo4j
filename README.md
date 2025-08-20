# Fraud Detection with Neo4j and PaySim Dataset  
_A graph-based approach to uncovering financial deception_  
**Author:** KONDRU SRINIVASA RAO

## Overview

This repository demonstrates how graph data science can be applied to detect and investigate financial fraud using Neo4j's Graph Data Science (GDS) library. The project uses the PaySim dataset—a synthetic simulation of mobile money transactions—to explore patterns of deception, identity misuse, and suspicious financial behavior.

Rather than treating fraud as isolated events, we model it as a network of interactions. Graphs allow us to ask deeper questions: Who is connected to whom? Which transactions form suspicious clusters? Are there hidden intermediaries facilitating illicit flows?

## Why Graphs for Fraud?

Traditional fraud detection often relies on rule-based systems or statistical models. These approaches struggle when fraudsters operate in groups, use synthetic identities, or exploit indirect relationships.

Graphs offer a different lens. They let us:
- Visualize relationships between entities (accounts, transactions, devices)
- Detect communities and anomalies
- Trace paths of money movement
- Identify central actors and hidden facilitators

## Problem Definition

### What is Fraud?

Fraud is the intentional deception of individuals or organizations for financial gain. It often involves misrepresentation of identity, services, or intent. In this project, we focus on two major types:

- **First-party fraud**: Individuals misrepresent themselves to gain favorable terms or default on obligations.
- **Synthetic identity fraud**: Fraudsters create fake identities or combine real and fake data to open accounts and conduct transactions.

### Additional Categories (for context)

- **Second-party fraud**: Someone willingly shares their identity with another to commit fraud.
- **Third-party fraud**: A fraudster uses someone else's identity without consent.

## Dataset: PaySim

PaySim is a synthetic dataset that simulates mobile money transactions. It captures realistic patterns of transfers, payments, and cash-outs, making it ideal for testing fraud detection algorithms.

Key features:
- Millions of transactions
- Multiple transaction types (TRANSFER, CASH_OUT, PAYMENT, etc.)
- Account balances, timestamps, and flags for fraud

For more on the dataset, see [Dave Voutila’s blog post](https://www.sisu.io/posts/paysim/) which provides background on its generation and structure.

## Modules

This project is organized into two main modules:

### Module 1: First-Party Fraud Detection
We use graph algorithms to identify accounts that exhibit suspicious behavior—such as rapid transfers, circular transactions, or unusually high connectivity.

### Module 2: Money Mule Identification
Money mules act as intermediaries, moving illicit funds between accounts. We use centrality measures and community detection to flag potential mules based on their position in the transaction graph.

## Workflow Summary

1. Load and preprocess the PaySim dataset into Neo4j
2. Construct a graph model: nodes (accounts), relationships (transactions)
3. Apply GDS algorithms:
   - Node similarity
   - PageRank
   - Louvain community detection
   - Anomaly detection
4. Label suspicious entities and visualize fraud rings

## Requirements

- Neo4j 4.x or later
- Graph Data Science Library (GDS)
- Python (for data preprocessing and integration)
- PaySim dataset (CSV format)

## Getting Started

Clone the repository and follow the setup instructions in `fraud-detection.py`. The Cypher queries are embedded in the script and can be run directly against your Neo4j instance.

```bash
git clone https://github.com/KONDRU-SRINIVASA-RAO/FraudDetection-Neo4j.git
```

## License

This project is licensed under the MIT License.

If you'd like help formatting this for GitHub Pages or adding visuals like graph snapshots or query results, I’d be happy to assist. You could also expand this into a technical blog or tutorial series if you're planning to share it with the broader data science or cybersecurity community.
