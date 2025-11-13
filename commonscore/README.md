### ARG25 Project Submission:
# commonscore

---

## Team
- ### _**Alex Soto**_
   - GitHub Handles: @alexsotodigital
   - Devfolio Handles: @alexsotodigital

- ### _**Navynox**_
   - GitHub Handles: @navy0110
   - Devfolio Handles: @navynox

## Project Description 
_commonscore is a minimal smart-contract framework for collective coordination.
It lets groups inside pop-up cities, residencies, or permanent hubs create and join economic agreements that distribute shared costs or benefits automatically; with transparency andfairness, and no spreadsheets._



## Tech Stack

- Smart contracts: Solidity (≥0.8.20)
- Framework: Hardhat / Foundry
- Libraries: OpenZeppelin (ReentrancyGuard, Ownable, MerkleProof)
- Network: Base / Sepolia
- Membership integration: EAS, Semaphore, Circles adapters (optional)

## Objectives
- Deploy Factory and Agreement contracts
- ETH and ERC20 support
- Participant or amount threshold
- Automatic execution and refunds
- Support + Commons fees

## Weekly Progress

### Week 1 (ends Oct 31)
**Goals:**
Define the idea and achieve alignment within the team. 🫶



**Progress Summary:**  

Communities like Invisible Garden, Edge City Patagonia, Funding The Commons, or any Pop Up City and Permanent Hub, often manage shared resources:
- meals and groceries,
- co-working passes,
- local transport,
- common maintenance funds.

commonscore formalizes these informal “community pools” as programmable agreements, deployed on-chain through a factory contract.
Each agreement is a small smart contract that:
- receives contributions (ETH or ERC20),
- enforces a quorum of participants or a funding goal,
- pays out automatically when the conditions are met,
- returns funds if not,
- and fairly rewards the coordinator who managed it.

Optionally, a portion of each successful agreement can be routed to a Commons Vault: a shared treasury for the hub.


### Week 2 (ends Nov 7)
**Goals:**  

#### Expected Outcome of the MVP
A technically functional and visually engaging prototype that demonstrates:
- Onboarding of a pop-up city as a hub.
- Participant registration with explicit informed consent and federated identity.
- Creation of milestone-based escrow contracts via commonscore.
- Issuance of attestations for milestone verification.
- Automatic fund release and commonvault contributions.
- Zero-knowledge analytics and sponsor dashboards for comparative insights.

----
 
**Progress Summary:**  

### Commonscore Hubs — Federated Coordination Platform for Pop-Up Cities and Residencies

#### 1. Overview
Covenant Hubs could be a decentralized coordination platform designed to empower pop-up cities, digital residencies, and federated communities to manage shared agreements and distribute sponsor resources transparently. It combines federated identity, smart-contract-based escrow, social attestations, and zero-knowledge analytics to build trust-driven micro-economies for temporary hubs and long-term cooperative networks.
The system operates across three composable layers:
- Federation Layer: registers hubs adhering to shared coordination principles.
- commonscore Layer: automates escrow-based collective agreements.
- Attestation & Privacy Layer: connects human judgment with programmatic fund disbursement, while protecting participant data through zero-knowledge proofs.

---

#### 2. Use Case: Pop-Up Cities and Residencies
Pop-up cities and residencies often rely on scarce sponsor funding and must coordinate efficiently between organizers and participants. Covenant Hubs provides a transparent mechanism to allocate and manage these limited resources.

**Scenario: Sponsor-Driven Fellowship Allocation**
- A pop-up city (e.g., Invisible Garden Residency) registers as a hub in the federation, signing the base Covenant that defines minimum transparency, non-discrimination, and accountability standards.
- Sponsors deposit funds into the hub’s federated escrow vault, managed by commonscore.
- Each resident or fellow accepted into the program receives an individual escrow smart contract, functioning as a conditional scholarship.
- Funds are locked until the hub (via multisig or authorized wallet) issues a completion attestation verifying milestone fulfillment.
- Once the attestation is recorded, the smart contract automatically releases the approved funds to the participant.
- Sponsors can later access an aggregated dashboard showing outcomes and impact metrics across hubs, protected by zero-knowledge proofs to preserve privacy.

---

#### 3. User Flows
**3.1 Hub Registration (Federation Covenant)**
- Hubs connect their wallet and sign the Federation Covenant Smart Contract, encoding shared governance principles (decentralization, transparency, care, accountability).
- Metadata (location, focus, ENS, duration, periodicity) is stored on-chain and indexed in the Federation Map.
- Each hub receives a Hub Credential NFT, symbolizing federation membership.

**3.2 Participant Registration (Identity & Trust Layer)**
- Participants connect their wallet and review:
   - The Federation’s Covenant (federated principles and baseline commitments).
   - The Hub’s Covenant (specific values and governance norms of the residency they’re applying to).
   - Their Participant Role Agreement, outlining rights, responsibilities, and accountabilities.
- The participant provides explicit, signed consent to these agreements.
- A minimal social verification (two attestations from members or coordinators) confirms the participant’s trust level.
- Once verified, they receive a Federated Identity NFT enabling participation in agreements and conditional funding programs.

**3.3 Funding Distribution (commonscore Escrow Contracts)**
- The hub deploys a commonscore Escrow Agreement with the following parameters:
   - amount (total grant or fellowship amount)
   - milestones (criteria for fund release)
   - deadline (completion date)
   - attestationAuthority (authorized wallet to confirm milestones)
   - rewardPercentage (portion allocated to the commonvault for incentive distribution)

- Sponsors or hub treasuries deposit funds into the contract.
- Upon milestone validation (via EAS attestation), releaseFunds() transfers the corresponding payment to the participant.
- A percentage (configurable, e.g. 2–5%) automatically goes to the hub’s commonvault and federation commonvault, supporting incentive models that reward positive contributions and retroactive impact.


**3.4 Sponsor Dashboard and Analytics**
- Sponsors access a Federation Results Dashboard, aggregating anonymized data about milestone completion, participation rates, and project outcomes.
- Using zero-knowledge proofs (ZKPs), sponsors can verify impact metrics (e.g., milestone success rate, average payout, number of fellows) without revealing private participant identities.

- Dashboards display:
   - Comparative performance between hubs.
   - Funding distribution ratios.
   - Verified milestones achieved per program.
   - This enables sponsors to identify which hubs align with their funding priorities and subscribe to their operations.
   - The system supports modular integrations (e.g., Karma Gap, EAS, or other DAO tooling) for milestone tracking, reputation, and impact scoring.

----

#### **4. Technical Architecture**
- Smart Contracts:
   - HubRegistry — maintains a registry of federated hubs.
   - commonscore — factory contract for deploying EscrowAgreement instances.
   - EscrowAgreement — milestone-based escrow logic with attestation-triggered disbursements and a configurable rewardPercentage redirected to commonvaults.
   - CommonVault — pooled treasury for each hub and federation-level fund.
   - FederationAttestor — verification contract for EAS attestations.

- Data Persistence:
   - On-chain: core agreements, attestations, and escrow operations.
   - Off-chain: metadata, documentation, and ZK-verified analytics (via Supabase, Ceramic, or Filecoin).

- Modularity and Integration:
   - Compatible with existing coordination tools (e.g., Karma Gap, EAS, Dework, or Coordinape).
   - Open API structure allows third-party plugins for reporting, milestone management, or gamified reward systems.

- Frontend Stack:
   - Next.js + Wagmi + Viem for Web3 interfaces.
   - Three.js for interactive 3D map visualizations.
   - TailwindCSS for clean, modular pixel-art styling.
 
---

#### **5. Visual and Interaction Design**
**Aesthetic Direction:**
 Minimalist 3D pixel-art world with hubs as glowing cylinders connected by light pathways — representing living cooperative ecosystems.
- Color Palette:
   - Background: #EDEAE4
   - Highlights: #EAD7BF
   - Contrast: #9F9A8A
      - Soft gradients and minimal shadows create a calm, elegant interface.

**Core Visual Metaphors:**
- Cylinders: hubs or residencies.
- Concentric circles: active agreements.
- Orbits: escrow contracts in progress.

**Animations:**
- Hover → subtle pulse and expansion.
- Signature or attestation → circular sealing animation.
- Successful milestone → golden light burst over the hub.

---

#### 6. Governance and Participant Protection
Governance occurs at multiple levels:
- Federation-level: Covenant principles and shared ethical norms.
- Hub-level: Localized covenants, funding criteria, and operational agreements.
- Participant-level: Explicit consent and access to clear, transparent terms.


This structure not only ensures inclusion but also enhances participant protection, each participant knows exactly what agreement they are joining, what milestones are expected, and how funds are managed.

---

#### **7. Strategic Vision**
Covenant Hubs redefines funding and accountability within temporary Web3 ecosystems by embedding transparency and conditionality into resource allocation.
- Key outcomes:
   - Reduces free riders, ensuring that subsidies (e.g., food, merch, travel) reach those contributing value.
   - Encourages economic sustainability by helping hubs attract and retain sponsors through auditable transparency.
   - Provides retroactive rewards via commonvaults for members who contribute to community wellbeing.
   - Strengthens trust and reputation within federated creative and civic ecosystems.

In essence, this system merges cooperative governance, programmable funding, and privacy-preserving analytics to establish a reproducible infrastructure for federated, transparent, and sustainable coordination economies.




### 🗓️ Week 3 (ends Nov 14)
**Goals:**  
Exploratory Validation of Problem and Solution with Sponsors.

**Progress Summary:**  

The primary goal for this week was to contact and initiate exploratory interviews with key potential sponsors (funders)

These interviews focused on three critical areas:

**Problem Validation:** Deepening our understanding of their current pain points and frustrations regarding the transparency and traceability of their funds' impact.

**Solution Feedback:** Gathering direct feedback on the proposed Covenant Escrow / Social Oracle solution to ensure it addresses their needs for trust and verification.

**Insights for Final Solution:** Identifying new insights and unarticulated requirements to refine the execution logic and the final design of the solution.

**Commonscore Escrow: The Social Oracle for Trust-Based Funding**

**1. The Problem: Trust Leakage in Community Funding**
In creative hubs, residencies, and communities (like Invisible Garden), most funding comes from a few trusted sponsors. Yet, these sponsors lack verifiable transparency and executable assurance over how their money is actually used. In the Web3 context, this problem is amplified: event and grant budgets often leak into low-impact activities (logistics, merch, parties) that don't always directly benefit the intended participants or meet the grant's goals.
Our Hypothesis:
If sponsors had a verifiable and programmable assurance that funds would be used according to agreements and milestones, trust would increase, and with it, the volume of capital available for high-impact initiatives.
Technical Implication:
We need a programmable Escrow mechanism that securely holds funds on-chain and only releases them when Attestations (verifiable digital proofs of completion) are provided by designated stakeholders. This implies: On-chain fund custody, off-chain human validation, and automated state transitions (Locked → Released → Refunded).

**2. Proposed Solution: Escrow with Integrated Social Oracle**
Commonscore Escrow introduces the concept of the Social Oracle: a human-driven validation layer that bridges social perception and programmable finance.
Funds are deposited into an Escrow smart contract and can only be released once the community or designated parties confirm that commitments were met through attestations. Instead of relying on reports or promises, money moves only when people agree that the promised reality has occurred.

**3. Technical Implications (The Core Stack):**
**Escrow Contract:** Securely holds ETH or stablecoins on-chain.
**Attestation Layer (EAS):** Collects signed proofs from designated participants, ensuring immutability and verifiability.
**Execution Logic:** Automatically releases funds once the attestation quorum is reached.
**Fallback Logic:** Allows sponsors to reclaim funds if conditions are not met within a defined deadline.

**4.  The Social Oracle (Core Concept and Validation)**
The Social Oracle is the human mechanism that verifies reality before the smart contract moves money. It formalizes collective confirmation as an executable precondition for fund disbursement.

**Key Technical Implication:**
All attestations must conform to a predefined EAS Schema (AgreementValidation) containing: subject, agreementId, attestor, decision (completed/not completed), and timestamp.

**5.  Pitch Summary**
"Commonscore Escrow is a social oracle for impact funding. Sponsors keep their money safe until people—not paperwork—confirm that promises have been kept."

**6.  Technical Stack Summary (MVP Scope)**

**Layer**                                **Component**                      **Description**
Smart Contracts                       EscrowAgreement.sol                    Minimal contract for fund custody and attestation-based release logic.

Attestation                        EAS (Ethereum Attestation Service)        Infrastructure for issuing and verifying cryptographic proofs of agreement completion.

Frontend                            React/Next.js (TBD)                      Interface for sponsor fund deposit and for emitting/viewing attestations.

Backend/Indexing                   The Graph / Supabase                      Indexing contract events and storing agreement metadata for the dashboard.



## Final Wrap-Up
_After Week 3, summarize your final state: deliverables, repo links, and outcomes._

- **Main Repository Link:**  
- **Demo / Deployment Link (if any):**  
- **Slides / Presentation (if any):**



## 🧾 Learnings
_What did you learn or improve during ARG25?_

During our stay at Invisible Garden, we learned about:

- The emerging landscape of pop-up cities and the rise of permanent hubs to promote the implementation of Web3 technology in face-to-face meetings.

- The different pain points that pop-up city organizers, such as Invisible Garden, encounter when organizing a residency, like the one we are experiencing firsthand.

- The existing technological components for creating potential solutions to these pain points, as well as the projects that are experimenting with them.


## Next Steps
_If you plan to continue development beyond ARG25, what’s next?_
The outcome of our work is intended to help Invisible Garden continue exploring ways to collectively improve its economic arrangements. We are happy to continue the conversation and seek other necessary contributors to make this happen.


_This template is part of the [ARG25 Projects Repository](https://github.com/invisible-garden/arg25-projects)._  
_Update this file weekly by committing and pushing to your fork, then raising a PR at the end of each week._
