---
rpip: 
title: Voted Operational Process Framework
description: 
author: LongForWisdom (@LongForWisdom)
discussions-to: 
status: Draft
type: Meta
created: 2023-10-02
---

## Abstract
Abstract is a multi-sentence (short paragraph) technical summary. This should be a very terse and human-readable version of the specification section. Someone should be able to read only the abstract to get the gist of what this specification does.

$TODO

## Motivation

The motivation for some VOP-like framework can be summarized as the desire for increased transparency and extensibility for DAO operational decision-making.

**Transparency**

A VOP-like framework allows participants in the Rocket Pool DAOs to more easily be able to understand the common processes that shape the DAOs. It does this in a few main ways:
* The types of process that exist can be listed, summarized and presented in such a way that is more-approachable to the average participant than reading through multiple full RPIPs. Participant attention is a key resource and should not be wasted on implementation details, if all that is desired is a high-level overview of 'how does process x work in Rocket Pool'.
* Votes and discussions can be labelled explicitly according to the process they are using. This makes it easier for participants to quickly slot items into the appropriate mental boxes. An RPIP is important, because it represents a change to the status quo. A GMC election is also important, but it doesn't represent a change to how Rocket Pool works. A grants appeal is potentially unimportant to a less-engaged participant, and can be more safely ignored. 
* The outcomes of processes can be recorded in a clear, consistent and accessible manner. Again, the goal is to minimize the attention and mental effort required by potential participants to find information they are looking for.

**Extensibility**

Adoption of a VOP-like framework helps to structure the processes of the Rocket Pool DAO in such a way that is easily extensible in future improvement proposals. The motivation here is to encourage organization, transparency and accessibility in such a way that it becomes self-sustaining. If there is a clear existing structure in use, then it encourages its use in future RPIPs.

## Specification
$TODO Remove
The key words “MUST”, “MUST NOT”, “REQUIRED”, “SHALL”, “SHALL NOT”, “SHOULD”, “SHOULD NOT”, “RECOMMENDED”, “MAY”, and “OPTIONAL” in this document are to be interpreted as described in RFC 2119.

### VOP Definition
* A Voted Operational Process (VOP) is a process involving a vote through which an operational decision is made.
  * Some operational decisions within the Rocket Pool DAOs MAY NOT require a vote, and therefore are not included in the VOP framework.
* A VOP MUST NOT be defined to cover decisions that are improvements to the Rocket Pool protocol, Rocket Pool DAOs, or anything that should otherwise require a new RPIP.

#### VOP Definition Core Elements

* Code - A short, unique, human-readable string identifier that can be used to identify this VOP and its type. Should take the rough form of VOP-SUBJECT-ACTION
* Name - A longer identifier in plain english. 
* Description - A description of this VOP.
* Purpose - Why does this VOP definition exist?
* Trigger(s) - What triggers this VOP to take place? Note, can have multiple triggers.
* Responsible Party - What party is responsible for ensuring this VOP takes place when it is triggered?
* Voting Group - Which group votes on the outcome of this VOP?
* Vote Type - What platform and format does this vote use?
* Other Requirements - Any other requirements that affect the execution of this VOP.

### VOP Usage in RPIPs

#### Framework
* The VOP framework SHOULD be used for anything that fits the definition of a voted operational process. 
  * If an RPIP specifies a process that could reasonably fit within the VOP framework, without adhering to the VOP framework, it MUST include detailed rationale as to why adhering to the VOP framework is not preferable.
* A VOP definition MUST be included in the RPIP in which the VOP is described.
  * VOP definitions MUST include the elements defined in the VOP Definition Core Elements section of this specification.
  * VOP definitions SHOULD follow the template defined in the VOP Definition Template section of this specification.

#### VOP Overview
* A VOP Overview MUST exist as a living, informational RPIP maintained by the RPIP Editors.
* Whenever an RPIP is ratified, the RPIP Editors MUST update the VOP Overview RPIP to include an entry for any newly ratified VOPs.
  * The VOP Overview entry SHOULD follow the template defined in the VOP Overview Entry Template section of this specification.

#### VOP Record-keeping
* A VOP record section MUST be included in the RPIP in which the VOP is defined.
  * The VOP record section SHOULD follow the template defined in the VOP Record Template section of this specification.
* When a VOP instance is triggered, it SHALL be assigned the next free ID number by the responsible party.
  * ID numbers are unique per VOP definition, start at 1, and increment by 1. 
  * VOP ID's MUST be appended to the VOP code with a hyphen.
* When a VOP instance concludes, successfully or otherwise, its outcome MUST be recorded in the appropriate VOP record section by the RPIP Editors. 
  * A VOP Record MUST include the date the VOP concluded.
  * A VOP Record MUST include an appropriate URL link indicating the outcome of the VOP.
  * A VOP Record MUST include a brief, human-readable summary of the outcome.


### VOP Definition Template
```
### <VOP CODE>
This is a voted operational process (VOP) definition, see RPIP-vop for more information.

* **Name:** 
* **Description:** 
* **Purpose:** 
* **Responsible Party:** 
* **Voting Group:** 
* **Vote Type:** 
* **Trigger(s):** 
  * 
  * 
  * 
* **Other Requirements:**   
  * 
  *
  *
```

#### VOP-EXAMPLE-EXAMPLE
This is a voted operational process (VOP) definition, see RPIP-vop for more information.

* **Name:** Voted Operational Process Example  
* **Description:** An example Voted Operational Process  
* **Purpose:** Demonstrate Voted Operational Process templates.  
* **Responsible Party:** RPIP Author  
* **Voting Group:** RPIP Author  
* **Vote Type:** Majority (Show of hands)  
* **Trigger(s):**   
  * Modification of RIP-vop structure.
  * When bored.
* **Other Requirements:** No other requirements


### VOP Record Section Template

```
| Code                   | Date       | Reference           | Outcome                                     |
|------------------------|------------|---------------------|---------------------------------------------|
| VOP-CODE-1             | YYYY-MM-DD | [Link](outcome link)| Brief description of VOP outcome for record |
| VOP-CODE-2             | YYYY-MM-DD | [Link](outcome link)| Brief description of VOP outcome for record |

Note, table generators exist: https://www.tablesgenerator.com/markdown_tables#

```

| Code                   | Date       | Reference           | Outcome                                   |
|------------------------|------------|---------------------|-------------------------------------------|
| VOP-EXAMPLE-EXAMPLE-1  | 2023-10-03 | [Link](example.com) | The example was ratified to wide acclaim. |


### VOP Overview Entry Template

```
#### VOP-EXAMPLE-EXAMPLE - <CONTAINING RPIP>
<VOP Extended Description>
```

#### VOP-EXAMPLE-EXAMPLE - [RPIP-VOP](RPIP-VOP.md)
This VOP is an example voter operational process that is intended to demonstrate how to define VOPs, describe VOPs, and record VOP instance outcomes. This VOP is just an example, so there's not really very much to say in this  overview! 

The intention is for overviews such as this to exist in a single informational RPIP that lists all defined VOPs that exist in the Rocket Pool DAOs. These descriptors will allow newcomers to the Rocket Pool community to easily identify common processes that take place at a high-level, and learn more about any they are interested in.


## Rationale
$TODO

The rationale fleshes out the specification by describing what motivated the design and why particular design decisions were made. It should describe alternate designs that were considered and related work, e.g. how the feature is supported in other languages.

## Backwards Compatibility

If this RPIP is ratified, existing ratified RPIPs containing processes that would fall under the VOP framework will be modified to use the VOP framework. The explicit intention is to maintain the logic and rules of existing processes, and just change their presentation such that they integrate with the VOP framework.

In case of unintentional changes to the logic of existing processes, or ambiguity introduces by the changes, RPIP Editors MAY modify the relevant RPIPs to _restore logical parity only_ without requiring a pDAO vote.  

The included processes are listed below, along with their VOP definitions. A PR has been prepared that will implement these changes. It will be merged by the RPIP Editors if this RPIP is ratified.

$TODO Do these definitions properly. 

### GMC Selections
* Code: VOP-GMC-MEMBERSELECT
* Name: Grants Management Committee Full Selection
* Description: An election to fill the membership of the GMC.
* Purpose: Ensure that the pDAO has the opportunity to periodically vote on GMC membership.
* Trigger(s): 10-14 months periodic / More than half of the GMC is membership has not been elected via vote / Vacant seats on the GMC that cannot be filled without a vote
* Triggering Parties: GMC Administrator > GMC Members > RPIP Editors
* Vote Type: Weighted (Snapshot)
* Voting Group: pDAO
* Other Requirements: As described by RPIP-10 and RPIP-26

### GMC Administrator Selection
* Code: VOP-GMC-ADMINSELECT
* Name: Grants Management Committee Administrator Selection
* Description: Selection of a GMC Administrator by the GMC members.
* Purpose: Ensure that the GMC has an administrator.
* Trigger: 12 months periodic / No GMC Administrator
* Responsible Party: GMC Members > RPIP Editors
* Voting Group: GMC Members
* Vote Type: Single Choice Plurality (Committee Internal)
* Other Requirements: As described by RPIP-26

### IMC Selection
* Code: VOP-IMC-MEMBERSELECT
* Name: Incentives Management Committee Selection
* Description: An election to fill the membership of the IMC.
* Purpose: Ensure that the pDAO has the opportunity to periodically vote on IMC membership.
* Trigger(s): 10-14 months periodic / More than half of the IMC is membership has not been elected via vote / Vacant seats on the IMC that cannot be filled without a vote
* Triggering Parties: IMC Members > RPIP Editors
* Voting Group: pDAO
* Vote Type: Weighted (Snapshot)
* Other Requirements: As described by RPIP-10 and RPIP-20

### oDAO Member Suggestion
* Code: VOP-ODAO-MEMBERSUGGEST
* Name: oDAO Membership Suggestion
* Description: A vote by the pDAO to suggest the addition or removal of a node to or from the oDAO.
* Purpose: To give the pDAO non-binding input into the oDAO member set.
* Trigger: At will
* Responsible Party: Rocket Pool Community
* Voting Group: pDAO
* Vote Type: Single Choice Plurality (Snapshot)
* Other Requirements: None

### oDAO Membership Change
* Code: VOP-ODAO-MEMBERCHANGE
* Name: oDAO Membership Change
* Description: A vote by the oDAO to add or remove a node to or from the oDAO.
* Purpose: To structure and record oDAO membership votes.
* Trigger: At will
* Responsible Party: oDAO Members
* Voting Group: oDAO
* Vote Type: Single Choice Plurality (On-chain)
* Other Requirements: None

### Grant Appeal
* Code: VOP-GMC-DISPUTE
* Name: Grant Decision Appeal
* Description: A vote triggered by a member of the community to appeal a grant decision by the GMC.
* Purpose: To allow the pDAO to override the GMC if and when it disagrees with its grant decisions.
* Trigger: Grant Announcement (within 2 weeks of announcement)
* Responsible Party: Rocket Pool Community
* Voting Group: pDAO
* Vote Type: Single Choice Plurality (Snapshot)
* Other Requirements: As described by RPIP-26

## Security Considerations

There are few security considerations to this RPIP, as it is non-technical. Modifications to the logic of any existing processes are limited to separating those processes from the main RPIPs framework. 

The possibility exists that the attached PR and modifications to existing RPIPs may unintentionally modify the logic or rules governing existing processes. This is mitigated by explicitly giving RPIP Editors the power to restore the intended logic or rules without a further vote.

The ratification of an extensible framework can be argued to imply the desire and intention to extend within that framework. This may run counter to any desire in the Rocket Pool community for a governance-minimized protocol.

## Copyright
Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
