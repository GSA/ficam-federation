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

If you want to understand how a Federation process works, you will have to know the actors involved. The first one, known as a **Service Provider (SP)**, is an application that wishes to allow access to the **User** using the credentials issued by another application, the **Credential Service Provider (CSP)**. A fourth application, the **Attribute Provider (AP)**, may be involved in a federation where additional information about the user is required.

- **Credential Service Provider (CSP)** establishes an individual’s identity and links the identity to a credential. CSPs create, maintain, and manage identity information and credentials for users, in accordance with the levels of assurance.

- **Service Provider (SP)**. Entity that requests and/or receives information about the identity of an individual or an authentication assertion from another party such as a CSP. The requestor is referred to as an RP, since the requestor relies upon information provided
from the external source to authenticate an identity.

- **User** requests access to an SP after authenticating to a CSP by providing his/her identity and token for verification. The user can provide more than one token for a higher level of assurance.

- **Attribute Provider (AP)** holds additional attributes about a user. The attribute provider can provide attributes to the CSP or the SP during a transaction. An attribute provider can either be an independent entity or be the same application as the CSP or the SP. Within the scope of this discussion, the CSP and AP are considered as the same entity.

<div style="text-align:center; width:70%"><img src="{{site.baseurl}}/img/federation.png"/></div>

During a Federation process, you will find these common steps:
- **Access Request** - The user requests access to the SP application.
- **Redirection** - The SP redirects the user to the IdP application.
- **Authentication** - The user is challenged by the CSP to present a valid credential such as a username and password, or their certificate. The CSP validates the identity of the individual using the credential.
- **Federation** - The CSP passes along the verification data, also known as _Assertion_, of the individual’s identity to the SP. 
- **Validation** - Once the SP verifies the assertion from the CSP, it may allow access to the user to its application. The SP may request additional identity information about the user from the CSP or AP.
- **Session** - Once the SP verifies the assertion, it will create a session for the user. The session will last for a period of time until the SP requires the user to authenticate with the CSP again.

The above example scenario is also known as SP initiated federation. In case of an IdP initiated federation, the user requests access to the SP application by accessing the CSP application first instead of being redirected from the SP.

This data sharing between the CSP and SP is made possible through the sharing of user's authentication information via common exchange protocols and agreed-upon open standards/specifications. This will enable your agency to allow a user from another organization or trust an authentication conducted outside of your agency. 

In a federated environment, these transactions occur between trusted Identity Providers that have
been approved through the Federal Trust Framework and relying parties. Given the nature of federated transactions and the electronic exchange of identity data across organizational boundaries, there is an increased focus on security and privacy to ensure users' sensitive identity data is appropriately safeguarded. 





























