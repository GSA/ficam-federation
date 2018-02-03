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
**What does "establishes a person's identity" mean? Create credential? (CB)**

**Terms**
**Credential** - A credential is authoritative evidence of a person's identity. For the Federal Government, a credential is most often a Personal Identity Verification (PIV) or PIV-Interoperable (PIV-I) card or Common Access Card (CAC). (Essentially reduced and edited form from FICAM-Arch's Services Framework > Credential Management)
**Identity** - A set of characteristics (also called “attributes”) that describe a person within a given context. For example, a person who is both a government contractor and an Army Reservist will have two identities, one in each context. These identities are often called “personas.” (From FICAM-Arch's Services Framework > Identity Management, slightly edited.)

The four interdependent roles involved in Federation are:

**Note:**&nbsp;&nbsp;For our discussion, the attribute provider and CSP are the same entity.<!--Can we then just combine them?--> 

- **Credential Service Provider (CSP)**. <!--What does establishes a person's identity mean?-->
* CSPs/Identity Providers create, maintain, and manage identity information and credentials for users, according to the four levels of assurance.
* Issues credentials to application users (i.e., in industry terminology--"establishes a user identity")
* Authenticates the user's identity (via the user's PIV/PIV-I/CAC credential) for RPs 

- **Attribute Provider**. The attribute provider (i.e., the CSP) maintains user attributes and during transactions provides them to an RP. (Transaction is a request to verify a user's identity...?)   

- **Relying Party (RP)** (application). An RP has an application to which it wants to give others access. RPs receive and store identity and credential data from CSPs/Identity Providers and to authenticate identities and make access control decisions based on that data, in accordance with the Federal Trust Framework. Requests and/or receives user identity information and the CSP's (or other) verification of a user's identity.  

- **User**. A person<!--???--> that establishes a session with a CSP by providing his/her identity and token<!--credential?--> for verification. The user may provide an additional token(s) for a higher level of assurance.  From above para: the user who needs access to the RP application.

Federation requires agencies to:
* Establish common exchange protocols
* Agreed-upon open standards/specifications that allow an agency to authenticate a user from another agency or trust a user who has been authenticated outside the agency. 
* Use common rules<!--Explain "rules"--> to ensure trust in the federated identity and credential to which an identity is bound. 
* Safeguard and ensure the privacy of users' sensitive identity data.<!--Do we mean PII?-->  

In a federated environment, these transactions occur between trusted CSP/Identity Providers that have been approved through the Federal Trust Framework and RPs<!--approved by RPs??-->. 

**Section 12.2?** provides a detailed overview of the Federal Trust Framework, which provides a foundation of trust between RPs and CSPs/Identity Providers. 

**Section 12.4.2?** gives guidance to help agencies select approved CSPs/Identity Providers and credentials.
