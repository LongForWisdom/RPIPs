---
rpip: <to be assigned>
title: Voted Operational Process Framework
description: <Description is one full (short) sentence>
author: LongForWisdom (@LongForWisdom)
discussions-to: <URL>
status: Draft
type: Meta
created: 2023-10-02
---

## Abstract
Abstract is a multi-sentence (short paragraph) technical summary. This should be a very terse and human-readable version of the specification section. Someone should be able to read only the abstract to get the gist of what this specification does.

## Motivation
The motivation section should describe the "why" of this RPIP. What problem does it solve? Why should someone want to implement this standard? What benefit does it provide to the Ethereum ecosystem? What use cases does this RPIP address?


Planned Support
* oDAO membership votes - RPIP-24
* pDAO oDAO membership suggestions - RPIP-24
* GMC elections - RPIP-10 + RPIP-26
* IMC elections - RPIP-10 + RPIP-20
* GMC Adminstrator election - RPIP-26
* Grants Appeals - RPIP-26

Future Support
* Core developer funding.



GMC Selections
* Code: VOP-GMC-MEMBERSELECT
* Name: Grants Management Committee Full Selection
* Description: An election to fill the membership of the GMC.
* Purpose: Ensure that the pDAO has the opportunity to periodically vote on GMC membership.
* Trigger(s): 10-14 months periodic / More than half of the GMC is membership has not been elected via vote / Vacant seats on the GMC that cannot be filled without a vote
* Triggering Parties: GMC Administrator > GMC Members > RPIP Editors
* Vote Type: Weighted (Snapshot)
* Voting Group: pDAO
* Other Requirements: As described by RPIP-10 and RPIP-26

GMC Administrator Selection
* Code: VOP-GMC-ADMINSELECT
* Name: Grants Management Committee Administrator Selection
* Description: Selection of a GMC Administrator by the GMC members.
* Purpose: Ensure that the GMC has an administrator.
* Trigger: 12 months periodic / No GMC Administrator
* Responsible Party: GMC Members > RPIP Editors
* Voting Group: Current GMC Members
* Vote Type: Single Choice Plurality (Committee Internal)
* Other Requirements: As described by RPIP-26

IMC Selection
* Code: VOP-IMC-MEMBERSELECT
* Name: Incentives Management Committee Selection
* Description: An election to fill the membership of the IMC.
* Purpose: Ensure that the pDAO has the opportunity to periodically vote on IMC membership.
* Trigger(s): 10-14 months periodic / More than half of the IMC is membership has not been elected via vote / Vacant seats on the IMC that cannot be filled without a vote
* Triggering Parties: IMC Members > RPIP Editors
* Voting Group: pDAO
* Vote Type: Weighted (Snapshot)
* Other Requirements: As described by RPIP-10 and RPIP-20

oDAO Member Suggestion
* Code: VOP-ODAO-MEMBERSUGGEST
* Name: oDAO Membership Suggestion
* Description: A vote by the pDAO to suggest the addition or removal of a node to or from the oDAO.
* Purpose: To give the pDAO non-binding input into the oDAO member set.
* Trigger: At will
* Responsible Party: Rocket Pool Community
* Voting Group: pDAO
* Vote Type: Single Choice Plurality (Snapshot)
* Other Requirements: None

oDAO Membership Change
* Code: VOP-ODAO-MEMBERCHANGE
* Name: oDAO Membership Change
* Description: A vote by the oDAO to add or remove a node to or from the oDAO.
* Purpose: To structure and record oDAO membership votes.
* Trigger: At will
* Responsible Party: oDAO Members
* Voting Group: oDAO
* Vote Type: Single Choice Plurality (On-chain)
* Other Requirements: None

Grant Appeal
* Code: VOP-GMC-DISPUTE
* Name: Grant Decision Appeal
* Description: A vote triggered by a member of the community to appeal a grant decision by the GMC.
* Purpose: To allow the pDAO to override the GMC if and when it disagrees with its grant decisions.
* Trigger: Grant Announcement (within 2 weeks of announcement)
* Responsible Party: Rocket Pool Community
* Voting Group: pDAO
* Vote Type: Single Choice Plurality (Snapshot)
* Other Requirements: As described by RPIP-26


## Specification
The key words “MUST”, “MUST NOT”, “REQUIRED”, “SHALL”, “SHALL NOT”, “SHOULD”, “SHOULD NOT”, “RECOMMENDED”, “MAY”, and “OPTIONAL” in this document are to be interpreted as described in RFC 2119.

The technical specification should describe the syntax and semantics of any new feature.

### VOP Definition
* A Voted Operational Process (VOP) is a process involving a vote through which an operational decision is made.
  * Some operational decisions within the Rocket Pool DAOs MAY NOT require a vote.
* A VOP MUST NOT be defined to cover processes that are improvements to the Rocket Pool protocol, Rocket Pool DAOs, or anything that should otherwise be covered by an RPIP.

### VOP Definition Core Elements

* Code - A short, unique, human-readable string identifier that can be used to identify this VOP and its type. Should take the rough form of VOP-SUBJECT-ACTION
* Name - A longer identifier in plain english. 
* Description - A description of this VOP.
* Purpose - Why does this VOP definition exist?
* Trigger(s) - What triggers this VOP to take place? Note, can have multiple triggers.
* Responsible Party - What party is responsible for ensuring this VOP takes place when it is triggered?
* Voting Group - Which group votes on the outcome of this VOP?
* Vote Type - What platform and format does this vote take place on?
* Other Requirements - Any other requirements that affect the execution of this VOP.

### VOP Usage in RPIPs

#### Framework
* The VOP framework SHOULD be used for anything that fits the definition of a voted operational process. 
  * If an RPIP defines a voted operational process without using the VOP framework, it MUST include detailed rationale as to why adhering to the VOP framework is not preferable.
* A VOP definition MUST be included in the RPIP in which the VOP is defined.
  * VOP definitions MUST include the elements defined in the VOP Core Elements section of this specification.
  * VOP definitions SHOULD follow the template defined in the VOP Definition Template section of this specification.

#### VOP Overview
* A VOP Overview MUST exist as a living, informational RPIP maintained by the RPIP Editors.
* Whenever an RPIP is ratified, the RPIP Editors MUST update the VOP Overview RPIP to include an entry for any newly ratified VOPs.
  * The VOP Overview entry SHOULD follow the template defined in the VOP Overview Entry Template section of this specification.

#### Record-keeping
* A VOP record section MUST be included in the RPIP in which the VOP is defined.
  * The VOP record section SHOULD follow the template defined in the VOP Record Template section of this specification.
* When a VOP instance is triggered, it SHALL be assigned the next free ID number by the responsible party.
  * ID numbers start at 1, and increment by 1. 
  * VOP ID's should be appended to the VOP code with a hyphen.
* When a VOP instance concludes, successfully or otherwise, its outcome MUST be recorded in the appropriate VOP record section by the RPIP Editors. 
  * A VOP Record MUST include the date the VOP concluded.
  * A VOP Record MUST include an appropriate URL link indicating the outcome of the VOP.
  * A VOP Record MUST include a brief, human-readable summary of the outcome.


### VOP Definition Template
* Code
* Name
* Description
* Purpose
* Trigger
* Responsible Party
* Voting Group
* Vote Type: 
* Other Requirements

### VOP Record Section Template

#### VOP-SUBJECT-ACTION-ID
* Date
* URL
* Outcome

### VOP Overview Entry

#### VOP-SUBJECT-ACTION
* VOP Name
* VOP Extended Description
* Link to VOP Definition


## Rationale
The rationale fleshes out the specification by describing what motivated the design and why particular design decisions were made. It should describe alternate designs that were considered and related work, e.g. how the feature is supported in other languages.

## Backwards Compatibility
All RPIPs that introduce backwards incompatibilities must include a section describing these incompatibilities and their severity. The RPIP must explain how the author proposes to deal with these incompatibilities. RPIP submissions without a sufficient backwards compatibility treatise may be rejected outright.

## Security Considerations
All RPIPs must contain a section that discusses the security implications/considerations relevant to the proposed change. Include information that might be important for security discussions, surfaces risks and can be used throughout the life cycle of the proposal. E.g. include security-relevant design decisions, concerns, important discussions, implementation-specific guidance and pitfalls, an outline of threats and risks and how they are being addressed. RPIP submissions missing the "Security Considerations" section will be rejected. An RPIP cannot proceed to status "Final" without a Security Considerations discussion deemed sufficient by the reviewers.

## Copyright
Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
