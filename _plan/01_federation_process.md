---
layout: default
title: Federation Process
permalink: plan/federationprocess/
collection: plan
pubDate: 
---
- Audience: Engineer/Architect
- Introduce Federation technology. Link to other pages (assertions, assurances and protocols) for more information.
- Layout the different actors in federation - CSP, AP, RP, end user. Relying Party doc Section 3.1 Federation Process.
- Include diagrams which may help in visualizing the flow of data between the actors. Example Relying Party Doc Fig 2 (Page 7).

If you want to understand how a Federation process works, you will have to know the actors involved. The first one, known as a Service Provider (SP), is an application which wishes to allow access to the user using the credentials issued by another application, the Credential Service Provider (CSP). A fourth application, the attribute provider (AP), may be involved in a federation where additional information about the user is required.

<div style="text-align:center; width:70%"><img src="{{site.baseurl}}/img/federation.png"/></div>

These parties are defined as follows:

- **Credential Service Provider (CSP)** establishes an individual’s identity and links the identity to a credential. CSPs validate the identity of the individual using the credential and pass along verification of the individual’s identity to an SP.

- **Service Provider (SP)**. Entity that requests and/or receives information about the identity of an individual or an authentication assertion from another party such as a CSP. The requestor is referred to as an RP, since the requestor relies upon information provided
from the external source to authenticate an identity.

- **User**. Entity that establishes an authenticated session with a CSP by providing his/her identity and token for verification. The user can provide more than one token for a higher level of assurance.

- **Attribute Provider (AP)** holds additional attributes about a user. The attribute provider can provide attributes to the CSP or the SP during a transaction. An attribute provider can either be an independent entity or be the same application as the CSP or the SP. Within the scope of this discussion, the CSP and AP are considered as the same entity.

Federation is made possible through the establishment and use of common exchange protocols
and agreed-upon open standards/specifications that will allow your agency to authenticate a user from
another organization or trust an authentication conducted outside of your agency. The use of these
common rules enables an agency to place a level of trust in the federated identity and credential
to which that identity is bound. Given the nature of federated transactions and the electronic
exchange of identity data across organizational boundaries, there is an increased focus on
security and privacy to ensure users' sensitive identity data is appropriately safeguarded.

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





























