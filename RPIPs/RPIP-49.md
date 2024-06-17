---
rpip: 49
title: 2024 Tokenomics Rework Info
description: Provides an introduction and overview of the 2024 community tokenomics rework, its likely contents, and its current status.
author: Valdorff (@Valdorff), LongForWisdom (@LongForWisdom)
discussions-to: https://dao.rocketpool.net/tag/tokenomics-rework
status: Living
type: Informational
created: 2024-03-08
tags: tokenomics-2024
---

## Abstract
This informational RPIP provides an introduction and overview of the 2024 community tokenomics rework, its likely contents, and its current status. It exists to explain the overall tokenomics proposal as it's currently envisioned by contributing community members. This RPIP lists and briefly describes the rework's components, and links out to the RPIPs that specify those components in greater detail.

The tokenomics rework will likely be split into two protocol upgrades, Saturn 1 and Saturn 2. This RPIP describes the components that are expected to be included within each.

This Informational RPIP and the tokenomics rework represent the best efforts of the Rocket Pool community contributors involved. Information within this RPIP should not be considered official word from the Rocket Pool core development team. 

## Explainers

The following explainers are being maintained by the community to help make the rework as accessible as possible.

* [Part 1 - Why Rework Rocket Pool's Tokenomics?](/tokenomics-explainers/001-why-rework)
* [Part 2 - Introduction to the Tokenomics Rework](/tokenomics-explainers/002-rework-intro)
* [Part 3 - Foundation of the Tokenomics Rework](/tokenomics-explainers/003-rework-foundation)
* [Part 4 - Supporting Components of the Tokenomics Rework](/tokenomics-explainers/004-rework-support)
* [Part 5 - Glossary of Terms](/tokenomics-explainers/005-glossary)

## Contents

### [RPIP-43: Megapools](RPIP-43.md)

A Megapool is a single contract that can be used as an Ethereum withdrawal address for multiple validators.
* This allows for much more gas-efficient usage of the Rocket Pool protocol for Node Operators.
* This allows for the application of node-level penalties. 
* Importantly, this RPIP specifies that node operation no longer requires RPL staking (ETH-only node operation). 

Additionally, Megapools are required to facilitate the bond curve changes described in RPIP-42.

### [RPIP-42: Bond curves](RPIP-42.md)

The changes to bond curves allow Node Operators to provide smaller ETH bonds while maintaining the security of the Rocket Pool protocol. 
* This gives Node Operators the option of dramatically increasing their capital efficiency.
* This allows the Rocket Pool Protocol to support a greater amount of rETH. 

For bonds to be lowered securely for the protocol, an initial set of bonds for a node must be larger than the minimum bond. 

### [RPIP-46: Universal Adjustable Revenue Split](RPIP-46.md)

This change allows the ETH revenue income from borrowed ETH (aka, rETH commission) to be split between various targets. The four targets are:
1. The Node Operator responsible for the validator with the borrowed ETH.
2. Vote-eligible Node Operators, proportional to their share of vote-eligible RPL.
3. The surplus share, used to capture value to the RPL token.
4. The rETH share, going to rETH holders. 

Aspects of the split are managed by the pDAO, the security council, and automatically by a heuristic function. For full details of 'who can do what', please see the full RPIP. 

This RPIP also includes the reduction of RPL issuance from 5% to 1.5%, as RPL rewards to Node Operators have been replaced by UARS.

### RPL Value Capture

Some form of value capture method will be included in the tokenomics rework package. Three options are being actively debated:
* [RPL Burn](RPIP-45.md) - Use the surplus share to buy and burn RPL.
* [RPL Buy & LP](RPIP-50.md) - Use the surplus share to buy RPL and deposit it in a liquidity pool. 
* Direct the surplus share to vote-eligible Node Operators, proportional to their share of vote-eligible RPL.

### [RPIP-44: Forced exits](RPIP-44.md)

This change allows the Rocket Pool protocol to force-exit Node Operators under certain circumstances. It relies on the adoption of [EIP-7002](https://eips.ethereum.org/EIPS/eip-7002) by the Ethereum protocol. 
* This allows Node Operators to exit their validators easily.
* This allows the Rocket Pool protocol to exit malicious validators.

The ability to force-exit misbehaving validators is a requirement for RPIP-42. 

### [RPIP-47: Forced delegate upgrades](RPIP-47.md)

This change allows the Rocket Pool protocol to force-upgrade Node Operators minipool delegate contracts after a grace period has expired. 
* This reduces the compatibility debt incurred by the protocol as it is upgraded because it does not need to support all prior iterations. 
* This means that protocol governance can make changes that benefit the protocol as a whole even if the changes do not benefit each individual Node Operator. 

### [RPIP-59: Deposit Mechanics](RPIP-59.md)

Here we desribe the mechanics of Node Operator deposits and validator creation, including standard and express queues.
* This provides a faster queue to help small node operators get started.
* This provides a faster queue for existing node operators to migrate their minipools to megapools.
* This allows node operators to optionally exit the queue up until they point their validator is created.

### [RPIP-60: Protocol Upgrade Guardrails](RPIP-60.md)

This RPIP introduces a delay after protocol upgrades have been confirmed but prior to them coming into effect.
* This helps protect participants in Rocket Pool from malicious upgrades.
* This allows the security council to react quickly in limited circumstances.

## Deployment Plan

The tokenomics rework package will likely be split between two protocol upgrades: Saturn 1 and Saturn 2.

### Saturn 1

* [RPIP-43: Megapools](RPIP-43.md)
  * Including ETH-only validators.
* [RPIP-42: Bond curves](RPIP-42.md)
  * Framework
  * 4ETH minimum bond
* [RPIP-59: Deposit Mechanics](RPIP-59.md)
  * Standard and express queues.
* [RPIP-46: Universal Adjustable Revenue Split](RPIP-46.md)
  * All but heuristic adjustments.
* RPL Value Capture - [RPL Burn](RPIP-45.md) / [RPL Buy & LP](RPIP-50.md) / Increased share to voting Node Operators.
* [RPIP-47: Forced delegate upgrades](RPIP-47.md)
* [RPIP-60: Protocol Upgrade Guardrails](RPIP-60.md)

### Saturn 2

* [RPIP-42: Bond curves](RPIP-42.md)
  * 1.5ETH minimum bond. 
* [RPIP-44: Forced exits](RPIP-44.md)
* [RPIP-46: Universal Adjustable Revenue Split](RPIP-46.md)
  * Heuristic adjustments.

## Current Status
Last Updated: June 10th

Current efforts are primarily focused on two areas.
1. Polishing the explainer document contents and format in response to feedback from the community.
2. Seeking and reacting to feedback from all parts of the Rocket Pool community and updating the RPIP specifications. 

A maintained list of open tasks is available via google sheet [here](https://docs.google.com/spreadsheets/d/1KDTeFnNl3XLFO37upti6NbT2p2GDYJ4GKH4aJ51gQZA/edit?pli=1#gid=725857744). 

### Estimated Process

The below is generally agreed to be the steps to be completed before we can consider this 'decided'.

1. **Done** - Complete the first draft of the full proposal specifications. 
2. **Active** - Seek feedback from technically skilled or highly engaged community members on the draft specifications. 
3. **Done** - Create high-level explanations and informational material for the full proposal for consumption by the wider community.
4. **Active** - Make a concerted effort to gather feedback via the forum from the wider community.
5. **Active** - Update the proposal and specifications as needed taking into account wider community feedback.
6. Run a forum temperature check vote on the full proposal (bar value capture mechanism).
7. Run a snapshot vote on the full proposal (bar value capture mechanism).
8. Run a snapshot vote on the value capture mechanism once outstanding blockers are cleared.
9. Update the proposal to incorporate the value capture mechanism vote result.

## Excluded Components
The below components have been discussed, but are not currently considered high enough priority to be included in the tokenomics rework plan.
* MEV penalty improvements
* rETH restitution from underperforming Node Operators
* Adjusting the DAO's portion of RPL inflation

## Further Links
* This proposal was presented at Rocket Pool's "Denver Lift Off" event by Valdorff and Samus - [Presentation](https://docs.google.com/presentation/d/12WRXuZktEtViwBWxFwm8OHpwpgoOpAF01859o0jGkiw), [Powerpoint Backup](../assets/rpip-49/On%20The%20Horizon%20(backup%20version).pptx), [Recorded Presentation](https://www.youtube.com/watch?v=nyqrilFtlrc&list=PLKzACASsJiuXc0v6kZambks4cPaSVbekf&index=4)
* Samus is maintaining a Google sheet containing notes, feedback, and TODOs which can be found [here](https://docs.google.com/spreadsheets/d/1qmGBCPAX-IqcFFjUzBib2Z_NKo_Yh5U00zKnGpyNak4). 

## Acknowledgements
The tokenomics package is based on the [early-March proposal from Valdorff](../assets/rpip-49/readme.md). The initial drafts have seen a significant improvement as a result of discussions with many people (thanks to 🏆samus🏆, 🏆sckuzzle, 🏆epineph, 🏆LongForWisdom, knoshua, uisce, langers, NonFungibleYokem, MountainB, luominx, ArtDemocrat, and many others). 

## Copyright
Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
