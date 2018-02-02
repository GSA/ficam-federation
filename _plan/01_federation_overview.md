---
layout: default
title: Federation Overview
permalink: plan/federationoverview/
collection: plan
pubDate: 
---
- Audience: Engineer/Architect
- Introduce Federation technology. Link to other pages (assertions, assurances and protocols) for more information.
- Layout the different actors in federation - CSP, AP, RP, end user. Relying Party doc Section 3.1 Federation Process.
- Include diagrams which may help in visualizing the flow of data between the actors. Example Relying Party Doc Fig 2 (Page 7).

**Define a "transaction"? (CB)**
**Define "user attributes" (CB)
**What does "establishes a person's identity" mean? A person already has an identity. (CB)**

**Terms**
**Credential** - A credential is authoritative evidence of a person's identity. For the Federal Government, a credential is most often a Personal Identity Verification (PIV) or PIV-Interoperable (PIV-I) card or Common Access Card (CAC). (Essentially reduced and edited form from FICAM-Arch's Services Framework > Credential Management)
**Identity** - A set of characteristics (also called “attributes”) that describe a person within a given context. For example, a person who is both a government contractor and an Army Reservist will have two identities, one in each context. These identities are often called “personas.” (From FICAM-Arch's Services Framework > Identity Management, slightly edited.)

The four interdependent roles involved in Federation are:

**Note:**&nbsp;&nbspFor our discussion, the attribute provider and CSP are the same entity.<!--Can we then just combine them?--> 

- **Credential Service Provider (CSP)**. <!--What does establishes a person's identity mean?-->
* Issues credentials to application users (i.e., in industry terminology--"establishes a user identity")
* Authenticates the user's identity (via the user's PIV/PIV-I/CAC credential) for RPs 

- **Attribute Provider**. The attribute provider (i.e., the CSP) maintains user attributes and provides them to an RP during a transaction. (Transaction is a request to verify a user's identity...?)   

- **Relying Party (RP)** (application). Requests and/or receives user identity information and the CSP's (or other) verification of a user's identity. The requestor is referred to as an RP, since the requestor relies upon information provided
from the external source to authenticate an identity.  From above para:  RP has an application to which it wants to give others access.

- **User**. Entity that establishes an authenticated session with a CSP by providing his/her identity and token for verification. The user can provide more than one token for a higher level of assurance.  From above para: the user who needs access to the RP application.

Federation is made possible through the establishment and use of common exchange protocols and agreed-upon open standards/specifications that allow an agency to authenticate a user fromanother organization or trust an authentication conducted outside of the agency. The use of thesecommon rules enables an agency to place a level of trust in the federated identity and credential to which that identity is bound. Given the nature of federated transactions and the electronic exchange of identity data across organizational boundaries, there is an increased focus on security and privacy to ensure users‘ sensitive identity data is appropriately safeguarded.

In a federated environment, these transactions occur between trusted Identity Providers that have been approved through the Federal Trust Framework and relying parties. Identity Providers are service providers that create, maintain, and manage identity information and credentials for users, in accordance with one of the four levels of assurance. Relying parties are entities thatreceive and consume identity and credential data from Identity Providers and make access control decisions based on that data, in accordance with the Federal Trust Framework and established federation governance. Section 12.2 provides a more detailed overview of the Federal Trust Framework, which exists to provide a foundational level of trust between relying parties and approved Identity Providers. Additionally, Section 12.4.2 provides guidance to help agencies select Identity Providers and credentials that have been approved through the Federal Trust Framework.
