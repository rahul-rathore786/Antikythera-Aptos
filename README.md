# Antikythera: DeFi AI Agent on the Aptos

**Submitted by: Rahul Rathore**

[![Hackathon Badge](https://img.shields.io/badge/Hackathon-Aptos%20x%20GCP%3A%20AI%20Agent%20Takeover-blue)](https://thunderdome.hackerearth.com/#overview)
[![Submission Link](https://img.shields.io/badge/View%20Submission-HackerEarth-green)](https://thunderdome.hackerearth.com/challenges/hackathon/ai-agent-thunderdome/dashboard/bfdebb0/submission/published/antikythera-defi-ai-agent-on-the-aptos/view/)

Antikythera is an AI-powered agent designed to interact with the Aptos blockchain, providing real-time on-chain data and enabling seamless DeFi operations. This project was submitted to the **Aptos x GCP: AI Agent Takeover hackathon**, a 4-week builder sprint where developers launch autonomous agents on the Aptos blockchain using open, modular Web3 + AI tools.



## Overview

Antikythera is an AI Agent that integrates accurate, real-time on-chain data from various protocols and applications on the Aptos Blockchain. It aims to overcome the limitations of previous AI assistants by providing live data access and the ability to interact with DApps.

![Cover 1](https://github.com/0xinevitable/antikythera/raw/main/.github/assets/cover-1.png)

For example, unlike assistants with pre-trained knowledge, Antikythera can answer questions like "Which protocol has the highest TVL on Aptos?" with a detailed, up-to-date markdown table.

![Antikythera vs Aptos Assistant](https://github.com/0xinevitable/antikythera/raw/main/.github/assets/vs-aptos-assistant.jpg?v=3)

Antikythera can handle a wide range of queries, identify optimal prices, arbitrage/yield opportunities, and current swap routes across Aptos protocols. It's designed with the potential to execute actions on behalf of users.

![Cover 2](https://github.com/0xinevitable/antikythera/raw/main/.github/assets/cover-2.png)

## Key Features

*   **Real-time On-chain Data:** Accesses live data from the Aptos blockchain.
*   **DeFi Capabilities:** Identifies trading opportunities, best swap routes, and yield farming options.
*   **Natural Language Interaction:** Users can query and instruct the agent using natural language.
*   **Tool Integration:** Leverages function calling to interact with external tools and APIs (e.g., DeFiLlama, DEX aggregators).
*   **Powered by AAK & Echelon SDK:** Utilizes the Aptos Agent Kit (AAK) for high-level Aptos interactions and the Echelon SDK for core Echelon protocol communication.

## Tech Stack

*   **Blockchain:** Aptos
*   **Frontend:** Next.js, React, TypeScript, Tailwind CSS
*   **Core Logic:** TypeScript
*   **Key Packages:**
    *   `packages/aak`: The Aptos Agent Kit for Aptos-specific interactions and DeFi tools.
    *   `packages/echelon-sdk`: SDK for interacting with the Echelon protocol.
    *   `packages/frontend`: The user-facing web application.
*   **Package Management:** Yarn Workspaces
*   **Build System:** Turborepo

## Getting Started

This project is a monorepo. Follow these steps to set it up and run the frontend:

### Prerequisites

*   [Node.js](https://nodejs.org/) (LTS version recommended)
*   [Yarn](https://classic.yarnpkg.com/en/docs/install) (Classic or Berry)

### Installation

1.  **Clone the repository:**
    ```bash
    git clone <your-repo-url>
    cd antikythera-aptos
    ```
2.  **Install dependencies from the root directory:**
    This will install dependencies for all packages in the monorepo.
    ```bash
    yarn install
    ```

### Running the Frontend

1.  **Navigate to the frontend package:**
    ```bash
    cd packages/frontend
    ```
2.  **Start the development server:**
    ```bash
    yarn dev
    ```
3.  Open your browser and go to [http://localhost:3000](http://localhost:3000).


## On-chain AI Agents

- We're witnessing the emergence of automated AI agents capable of making autonomous decisions. This trend is exemplified by projects like [AutoGPT](https://github.com/Significant-Gravitas/AutoGPT), [AgentGPT](https://github.com/reworkd/AgentGPT), [Claude Engineer](https://github.com/Doriandarko/claude-engineer), etc. These leverage Large Language Models (LLMs) as their core but require integration with external data and execution environments to fully realize their potential.

- That's where **Function Calling** comes in, enabling LLMs to reliably use external tools and APIs. By defining "Tools" as structured interfaces, LLMs can generate appropriate function calls based on user inputs, allowing seamless integration with external systems. The response from these external tools is then passed back to the LLM, which uses this information to generate a final output.

- Our ultimate goal is to enable LLMs to **establish their own unique identities within the blockchain**, achieving Financial Autonomy as AI agents themselves. (We initially explored this concept in [junhoyeo/CryptoGPT](https://github.com/junhoyeo/CryptoGPT), 2023)

- We build these tools as a public good. For example, in Antikythera's Beta Version (not yet deployed to the main website due to production-not-ready private key signing), **if a user asks the AI to purchase an Aptos Name, the AI reasons through the process and executes transactions sequentially.** It checks the balance, swaps for more APT if necessary, verifies the name price, and automatically completes the registry process.

![Beta 1](https://github.com/0xinevitable/antikythera/raw/main/.github/assets/beta-1.jpg?v=2)

## Querying the Blockchain

Antikythera can perform various queries and present data in a user-friendly way:

*   **DEX Aggregation:** Kana Labs DEX aggregator integration for optimal pricing and swap routes.
*   **DeFi Data:** Integration with DeFiLlama for chain TVL and protocol/yield opportunity data on Aptos.

![Query USDC Instances](https://github.com/0xinevitable/antikythera/raw/main/.github/assets/usdc-instances.png)
*Caption: Token information using Hippo Labs (data corrected/reviewed with Nodit's Indexer API), including bridged tokens and their diversification benefits.*

![Nodit 1](https://github.com/0xinevitable/antikythera/raw/main/.github/assets/nodit-1.jpg)
*Caption: Token balances/portfolio of a given address.*

![Echelon 1](https://github.com/0xinevitable/antikythera/raw/main/.github/assets/echelon-1.jpg?v=2)
![Echelon 2](https://github.com/0xinevitable/antikythera/raw/main/.github/assets/echelon-2.jpg?v=2)
*Caption: Markets in Echelon (base asset, borrow/supply APRs, tracked price, etc.).*

## Future Work

- Roll out execution mode with safer key management and/or browser wallet integration.
- Aave integration after its mainnet launch on Aptos.
- **On-demand Tool Generation:**
  - Leverage Move's capability to extract package ABI through RPC (`getAccountModule`). This will enable the AI to evaluate and utilize new packages in real-time by analyzing Aptos Move Code. This approach is inspired by [ThalaLabs/surf](https://github.com/ThalaLabs/surf).
- **Universal Client:**
  - Aim to create a comprehensive client/frontend similar to Instadapp or DeFiLlama by combining AI agents with wallet connections, offering a more intuitive experience for newcomers.

---
