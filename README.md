# Veritas Vitae (Truth of Life) DApp

Welcome to the **Veritas Vitae** project repository! This decentralized application (DApp) leverages blockchain technology on the Solana network to maintain a **life ledger** of an individual’s educational and professional journey, from the moment they start schooling until retirement.

---

## Table of Contents

- [Architecture & Problem Statement](#architecture--problem-statement)
- [Features](#features)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
    - [Solana Program Deployment](#solana-program-deployment)
    - [Front-end Build](#front-end-build)
- [Usage](#usage)
- [Programs](#programs)
- [Testing](#testing)
- [Frontend](#frontend)
- [Contributing](#contributing)
- [License](#license)

---

## Architecture & Problem Statement

### Problem We Are Solving

Centralized systems for storing an individual’s academic and career records can be altered, lost, or tampered with. Moreover, verifying someone’s credentials (like education or employment history) often relies on inefficient, trust-based processes. **Veritas Vitae** addresses these challenges by creating an **immutable ledger** of a person's educational and professional milestones using Solana’s blockchain.

### High-Level Architecture

1. **Solana Program & Account (On-Chain)**

   - Government creates a **Program ID** or account for each individual.
   - Each institution (e.g., schools, universities, companies) sends verified updates to the ledger (new roles, promotions, salary changes, skills acquired, etc.).
   - Data is immutable—once recorded, it cannot be revoked or deleted.

2. **Frontend (Web Interface)**

   - Designed to allow government agencies and authorized institutions to log in, review, and add records.
   - Hiring companies receive **read-only** access to certain data fields (e.g., job roles, durations, skills), hiding sensitive information like salary details or personal descriptions.

3. **Selective Access & Governance**
   - **Government** can turn the DApp “on” for a particular individual when needed (e.g., verifying their readiness to start a company, analyzing potential tax obligations).
   - **Next institution** in the user’s journey updates the ledger with new details.
   - **Hiring Companies** can check basic authenticity without seeing personal or confidential data.

### Key Data Fields (Example)

- **From Institution**
- **To Institution**
- **From/To Country or State**
- **Date Started / Date Ended**
- **Skills Earned**
- **Salary (Ending, New, Currency Type)**
- **Description (Internal/Confidential)**
- **Rating**
- **Behavior**

Once an entry is added or updated (after government review), it can **never** be deleted, preserving authenticity and trust in the user’s life ledger.

---

## Features

- **Immutable Profile Tracking**: Create and update a permanent record of an individual’s educational and career steps.
- **Selective Read-Only Access**: Hiring companies view limited information to confirm authenticity without revealing private data (e.g., salary, personal notes).
- **Government-Managed Program IDs**: The government can enable or disable access to the ledger and analyze tax implications or other legal requirements.
- **Secure PDAs (Program Derived Addresses)**: Implements security validations and checks to prevent unauthorized writes or modifications.

---

## Getting Started

`/program` folder contains all the files needed to build and deploy our Solana program to the Solana Devnet.  
`/frontend` folder contains all the files and configurations for building and serving our frontend application.

### Prerequisites

1. **NPM**
2. **Program ID**: Given by the Solana Playground (or any Solana-compatible deployment tool) after deploying the program. You can also find it via the Solana Explorer using the wallet address that performed the deployment.

### Installation

#### Solana Program Deployment

1. Navigate to [Solana Playground](https://beta.solpg.io/) (or your preferred Solana dev environment).
2. Import the files in the `/program` folder to the playground compiler.
3. Ensure you are connected to **Devnet** with a wallet that has sufficient SOL balance (use a [faucet](https://faucet.solana.com/) for free SOL airdrops).
4. In the **Build & Deploy** tab, build and deploy your program.
5. After a successful deployment, **copy the Program ID** from the Build & Deploy page.

#### Front-end Build

1. **Clone the repository**:

   ```bash
   git clone https://github.com/shrprabh/Veritas-Vitae
   ```

2. **Navigate** to the frontend directory:

   ```bash
   cd veritas-vitae/frontend
   ```

3. **Install required npm packages**:

   ```bash
   npm install
   ```

---

## Usage

1. In `/frontend/src/pages/index.tsx`, **replace the Program ID** with the one obtained from the Solana Playground.
2. **Start** the development server:

   ```bash
   npm start
   ```

3. **Open** your browser and navigate to `http://localhost:3000` to access the DApp.
4. **Connect** your Solana wallet (e.g., Phantom, Backpack) to the DApp.
5. **Enter the relevant information** (e.g., new institution, skills earned, salary change, or rating).
6. **Submit** changes, which are then **verified** and recorded on the Solana blockchain.

---

## Programs

The files in the `./program/src` directory include:

- **`instruction.rs`**  
  Contains the logic to select and handle the correct instruction for creating or updating a record.

- **`state.rs`**  
  Manages data types and the state stored within Solana accounts (e.g., user transitions, salary info, skill sets).

- **`lib.rs`**  
  Configures the program entrypoint and processes the returned instructions.

---

## Testing

- For program-level tests, you can write unit and integration tests in Rust to verify each instruction behaves as intended.
- Frontend tests can be conducted using frameworks like Jest or Cypress to ensure the user interface and transactions work as expected.

---

## Frontend

- Developed with React and TypeScript for modular, maintainable code.
- Interacts with the on-chain program to read or write data based on user action and role (government, institution, or hiring company with limited access).

---

## Contributing

Contributions to this project are welcome! To contribute:

1. **Fork** the repository.
2. **Create** a new branch for your feature or bug fix.
3. **Make changes** and test them thoroughly.
4. **Commit** with clear and concise messages.
5. **Push** changes to your fork.
6. **Submit** a pull request describing your changes.

---

## License

This project is licensed under the [MIT License](LICENSE).

---

### Advantages

- **Immutable**: Once skills or records are added, they cannot be modified or removed.
- **Authenticity**: Hiring companies and the government get a verifiable snapshot of one’s career path—no more forged credentials.
- **Transparent Yet Private**: Institutions can update records, while sensitive data (like salaries or personal notes) can remain hidden from unauthorized viewers.
- **Blockchain Security**: The Solana chain ensures high throughput, quick finality, and robust security.

---

**Build a transparent, secure future for educational and professional records with Veritas Vitae!**

---

## Acknowledgements

We would like to express our sincere gratitude to the **Web 3 Acceleration Association (WAA)** and the **Solana Blockchain Community** for their invaluable support and resources in making this project possible.
---
### Contribution and Author
**Author**: [Shreyas Prabhakar](https://github.com/shrprabh)  
**Email**: [pshreyasgowda1997@gmail.com](mailto:pshreyasgowda1997@gmail.com)  
**LinkedIn**: [https://www.linkedin.com/in/shreyasprabhakar/](https://www.linkedin.com/in/shreyasprabhakar/)  
**GitHub**: [www.github.com/shrprabh](https://github.com/shrprabh)  
**X**: [@Shreyasprabhak1](https://twitter.com/Shreyasprabhak1)

**Repository Link**: [https://github.com/shrpabh/veritas-vitae.git](https://github.com/shrpabh/veritas-vitae.git)
