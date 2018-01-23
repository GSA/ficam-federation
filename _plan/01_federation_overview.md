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

Federation requires at least three parties, one party that has an application which it wishes to allow access to (i.e., the RP), another party that has issued credentials to the target users of the application (i.e., the CSP), and the user who needs access to the RP application. A fourth party, the attribute provider, may be involved in a federation where additional information about a user is required. The attribute provider acts as an independent entity that maintains a set of attributes about the user. For a particular transaction, the attribute provider and the CSP can be the same entity. These parties are defined as follows:

- **Credential Service Provider (CSP)**. Entity that establishes an individual’s identity and links the identity to a credential. CSPs validate the identity of the individual using the credential and pass along verification of the individual’s identity to an RP.

- **Attribute Provider**. Entity that holds additional attributes about a user. The attribute provider can provide attributes to the CSP or the RP during a transaction. An attribute provider can either be an independent entity or be the CSP itself. Within the scope of this section, the CSP and attribute provider are shown as the same entity.

- **Relying Party (RP)**. Entity that requests and/or receives information about the identity of an individual or an authentication assertion from another party such as a CSP. The requestor is referred to as an RP, since the requestor relies upon information provided
from the external source to authenticate an identity.

- **User**. Entity that establishes an authenticated session with a CSP by providing his/her identity and token for verification. The user can provide more than one token for a higher level of assurance.

Federation is made possible through the establishment and use of common exchange protocols
and agreed-upon open standards/specifications that allow an agency to authenticate a user from
another organization or trust an authentication conducted outside of the agency. The use of these
common rules enables an agency to place a level of trust in the federated identity and credential
to which that identity is bound. Given the nature of federated transactions and the electronic
exchange of identity data across organizational boundaries, there is an increased focus on
security and privacy to ensure users‘ sensitive identity data is appropriately safeguarded.

In a federated environment, these transactions occur between trusted Identity Providers that have
been approved through the Federal Trust Framework and relying parties. Identity Providers are
service providers that create, maintain, and manage identity information and credentials for
users, in accordance with one of the four levels of assurance. Relying parties are entities that
receive and consume identity and credential data from Identity Providers and make access
control decisions based on that data, in accordance with the Federal Trust Framework and
established federation governance. Section 12.2 provides a more detailed overview of the Federal
Trust Framework, which exists to provide a foundational level of trust between relying parties
and approved Identity Providers. Additionally, Section 12.4.2 provides guidance to help agencies
select Identity Providers and credentials that have been approved through the Federal Trust
Framework.





























