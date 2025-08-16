# AnnotateX 🪙📊  
*A Decentralized Data Labeling Protocol on Solana*  

This project is a **decentralized data labeling platform** built on Solana using **Anchor & Rust**.  
It enables **task creators** to post labeling jobs with escrowed rewards, **contributors** to submit annotations, and **reviewers** to stake SOL and vote on submissions.  
Rewards are released automatically when the required consensus threshold is reached.  

---

## Features
-  **Escrow Vaults** – Rewards are locked in PDAs until tasks are successfully completed.  
-  **Worker Submissions** – Contributors submit data labels stored on-chain with metadata URIs.  
-  **Reviewer Staking & Voting** – Reviewers must stake SOL to vote; prevents spam and ensures accountability.  
-  **Consensus-Based Approval** – Contributions require majority approval (e.g., ≥60%) before payouts.  
-  **Automatic Rewards** – Payouts proportional to approved work units.  

---

##  Architecture
- **TaskAccount** – Stores task details, reward pool, and progress.  
- **ContributionAccount** – Tracks worker submissions & work units.  
- **ReviewAccount** – Created per reviewer; stores stake value and status. 
- **Reviewer_stake_vault** - stores staked SOL of reviewer
- **VoteAccount** – Tracks votes per contribution (approve/reject, voters).  
- **Escrow Vault PDA** – Holds locked rewards, only program logic can release funds.  

---

##  Instructions (On-chain)
- `create_task` – Initialize a new task with reward escrow.  
- `submit_contribution` – Worker submits labeled data + work units.  
- `reviewer_init` – Reviewer stakes SOL and activates review rights.  
- `submit_vote` – Reviewer casts approve/reject vote on a contribution.  
- `finalize_contribution` – Distributes rewards when approval threshold is met.  

---


### References
- [Rust](https://www.rust-lang.org/tools/install) + Cargo  
- [Solana CLI](https://docs.solana.com/cli/install-solana-cli-tools)  
- [Anchor](https://www.anchor-lang.com/docs/installation)  

