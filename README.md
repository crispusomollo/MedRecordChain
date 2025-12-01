# 🏥 MedRecordChain — Decentralized Health Records

## Overview
MedRecordChain is a blockchain solution for secure and transparent medical records management. Patients control access while all actions are immutably logged on-chain.

<img width="806" height="492" alt="image" src="https://github.com/user-attachments/assets/76e00f55-9f1e-4940-9bab-e70023468f67" />


**Key Features:**
- Patients create and own medical records
- Grant/revoke doctor access
- View records if authorized
- Immutable event logs (`RecordCreated`, `AccessGranted`, `AccessRevoked`)
- Minimal CLI interface
- ≥6 automated tests for success and revert scenarios

---

## Repository Structure
```
contracts/ Smart contracts (Solidity)
scripts/ Deployment and interaction scripts
test/ Automated tests
client/ Thin CLI client
reports/ PDF reports
README.md This file
hardhat.config.js Hardhat configuration
.env.example Environment variable template
```

---

## Setup

1. **Clone repository**
```bash
git clone <repo_url>
cd medrecordchain
```
2. **Install dependencies**

```bash
npm install
```
3. **Setup environment**

```bash
cp .env.example .env
# Fill in your PRIVATE_KEY and RPC_URL
```

## Deployment

```bash
npx hardhat run scripts/deploy.js --network sepolia
```
- Contract address and ABI will be saved in client/src/.

## CLI Usage
```bash
cd client
npm install
npm start
```

**Options:**

- Create Record

- Grant Access

- Revoke Access

- View Record

- Exit


## Testing

```bash
npx hardhat test
```

- Tests include both success and revert cases.

- Event verification included.


## Gas Report

```
| Function     | Gas Used |
| ------------ | -------- |
| createRecord | 85,000   |
| grantAccess  | 28,000   |
| revokeAccess | 27,000   |
| viewRecord   | 22,000   |
```

## Risks & Mitigations

```
| Risk                 | Mitigation                   |
| -------------------- | ---------------------------- |
| Private key exposure | Store `.env` securely        |
| Unauthorized access  | Modifiers and event checks   |
| Large data storage   | Use off-chain IPFS           |
| Gas costs            | Only store metadata on-chain |
```

## Limitations

- Full medical records stored off-chain

- CLI interface only (no web UI yet)

- Gas fees on mainnet

## Future Work

- React web UI / dashboard

- Emergency access for hospitals

- Layer-2 scaling for lower gas costs

- IPFS integration for full records

## Demo Video
```
Link: []
```

## Team Contributions

```
| Member      | Contributions                              |
| ----------- | ------------------------------------------ |
| Chris Origi | Smart contract design, deployment, testing |
| Member 2    | CLI client, scripts                        |
| Member 3    | Documentation, reports, demo recording     |
| Member 4    | Gas analysis, additional testing           |
```


## Team Process & Commit Highlights

The team followed a structured workflow with clear areas of responsibility:

**Commit Highlights:**

- ``Initialize repository with folder structure``

- ``Add MedRecordChain.sol and Migrations.sol``

- ``Write deployment script and config``

- ``Implement CLI client``

- ``Add automated tests``

- ``Add README.md and reports``

- ``Finalize .gitignore``


**Balance & Visibility:**

- Each member has a clear area of responsibility

- Commit history reflects contributions and collaborative workflow

- Documentation and reports ensure transparency and reproducibility

```
| Member          | Contributions                                                                                                                                                           |
| --------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Chris Origi** | Smart contract design and implementation (`MedRecordChain.sol`), deployment scripts (`deploy.js`), automated testing, and ensuring on-chain event logging.              |
| **Member 2**    | Developed the CLI client (`client/src/index.js`) for patient and doctor interactions, integrated contract ABI & address, and handled error checking.                    |
| **Member 3**    | Prepared documentation, README, short report, one-page summary, and recorded the demo video.                                                                            |
| **Member 4**    | Created gas measurement script (`gasReport.js`), added additional tests, optimized smart contract functions for gas efficiency, and verified role-based access control. |
```

## License

MIT License
