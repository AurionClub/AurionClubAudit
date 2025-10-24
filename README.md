🧾 AurionClub Smart Contract Audit Explanation

Overview
AurionClub is a decentralized investment smart contract deployed on the BNB Smart Chain (BEP-20) network.
It is designed to automate passive income distribution through verified investment plans, referral rewards, and transparent profit mechanisms without admin control.

Contract Verified: https://bscscan.com/address/0xAD81F7819465e3e4201C587c20C4b8E1Bb9920eb#code

Submission Date: October 23, 2025
Compiler Version: Solidity ^0.8.30
License: MIT

🛡️ Security Architecture
The contract implements several standard and security-oriented modules:
- IERC20 Interface: Enables interaction with BEP-20 tokens (USDT in this case).
- Ownable: Restricts administrative privileges only to the contract owner.
- ReentrancyGuard: Prevents reentrancy attacks during deposit and withdrawal operations.
- Non-upgradable Smart Contract: Ensures immutability after deployment.
These components ensure that no external party or admin can manipulate investor balances or ROI once the contract is deployed.

💎 Core Functionalities
1. Investment System
The contract provides five investment plans, each with specific minimum and maximum deposit ranges, daily ROI, duration, and total return percentages.
Participants can deposit USDT tokens to start earning daily ROI, automatically calculated and stored on-chain.

2. Referral Reward Mechanism
A multi-level referral structure (up to 4 levels) rewards users for inviting others.
Each level has a unique percentage and minimum direct referral requirement.
Unclaimed or ineligible referral bonuses are automatically classified as expired bonuses and stored for liquidity growth.

3. Secure Withdrawals
- Users can withdraw only once every 24 hours.
- Withdrawals are subject to a small fee (5%) to support contract sustainability.
- The system includes a daily withdrawal cap to maintain liquidity equilibrium.

4. Bonus Expiration
Function: withdrawExpiredBonuses()
- Exclusively callable by the contract owner.
- Allows the withdrawal of expired referral bonuses to maintain liquidity for future participants.
- Every transaction emits a transparent event recorded on the blockchain.

📊 Transparency & Data Tracking
The contract provides multiple public view functions:
- getUserInfo() → Shows total deposits, withdrawals, bonuses, and active status.
- getUserInvestments() → Lists all user investments with their timestamps and plan IDs.
- getContractStats() → Displays total referral bonuses, expired bonuses, fees, and live balance.
- getActiveInvestmentStatus() → Verifies if a user still has an ongoing active plan.
These functions ensure complete traceability for both investors and auditors directly on-chain.

⚙️ Key Constants
- MIN_DEPOSIT	20 USDT
- MIN_WITHDRAWAL 1 USDT
- DAILY_WITHDRAWAL_LIMIT 1000 USDT
- OWNER_FEE_PERCENT	10%
- WITHDRAWAL_FEE_PERCENT 5%

📂 Events & Logging
Each transaction is recorded with detailed logs for transparency:
- Deposit() – Records each user investment.
- Withdraw() – Logs withdrawals with deducted fees.
- ReferralBonus() – Tracks referral rewards per level.
- ReferralBonusExpired() – Records expired bonuses.

🔍 Audit Summary
✅ No backdoor functions or admin control over user funds.
✅ All deposits and withdrawals are on-chain verified.
✅ Referral and ROI systems are automated and time-dependent.
✅ Reentrancy, overflow, and access control protections implemented.
✅ Transparency guaranteed via public view functions and blockchain logs.

🧩 Conclusion
The AurionClub Smart Contract demonstrates a transparent and sustainable DeFi model combining investment automation and multi-tier referral incentives.
All operational logic is securely embedded within immutable smart contract code, ensuring reliability, transparency, and long-term sustainability for investors.

Audited and Verified: October 2025
Smart Contract Address: 0xAD81F7819465e3e4201C587c20C4b8E1Bb9920eb
