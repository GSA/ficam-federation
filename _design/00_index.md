---
layout: default
title: Federation Design
permalink: /design/
collection: design
pubDate: 
---

- Audience: Engineer/Architect
- Provide an introduction to federation transaction and lead them to design patterns and protocols.
- FICAM Roadmap section 12.1.2 Federation Trust Topologies
- FICAM TFS Relying Party Doc Section 3.1.1 - Federated Authentication by a credential provider. 

============================

You will see these common steps during a federation transaction: 

- **Login** - The user requests access to the SP application.
- **Redirection** - The service provider checks that the user is not authenticated and redirects the user to the Identity Provider (IdP) application.
- **Authentication** - The user is challenged by the Identity Provider to prove who he/she is via a valid credential such as a username and password. The IdP validates the identity of the individual using the credential.
- **Data Sharing** - The IdP shares the information, also known as _Assertion_, with the SP that the user was successfully vetted.
- **Validation** - Once the SP verifies the assertion from the CSP, it may allow access to the user to its application. The SP may request additional identity information about the user from the CSP or AP.

The above example scenario is also known as _SP initiated federation_. In case of an _IdP initiated federation_, the user requests access to the SP application by accessing the CSP application first instead of being redirected from the SP.

## Design Patterns

If you want to design a federation implementation, you will find a number of different information sharing approaches that your agency might choose. These approaches, referred to as **design patterns**, will differ based on the type of relationship that exists with the external parties involved and the level of trust required for the transaction. 

Your agency‘s existing ICAM investments, such as modernized logical access
control systems (LACS), may also provide additional capabilities that could impact the
federation architecture that best meets the agency‘s needs. These additional factors may drive an
agency to adopt a hybrid approach that combines elements of multiple topologies, resulting in a
model that closely represents the agency‘s needs. 

Regardless of the federation trust topology selected, there are a number of resources that have 
been established within the Federal Government to provide agencies with a foundational level of 
trust. When entering into an established federation; however, it is likely that the existing 
federation members have already chosen a trust topology. Therefore it is important than an 
agency examine the factors previously discussed to select a federation that most closely meets 
its needs.

## Federation Protocols

This data sharing between the CSP and SP is made possible through the sharing of user's authentication information via common exchange protocols and agreed-upon open standards/specifications. This will enable your agency to allow a user from another organization or trust an authentication conducted outside of your agency. 

In a federated environment, these transactions occur between trusted Identity Providers that have
been approved through the Federal Trust Framework and relying parties. Given the nature of federated transactions and the electronic exchange of identity data across organizational boundaries, there is an increased focus on security and privacy to ensure users' sensitive identity data is appropriately safeguarded. 

When establishing a new federation, it is likely that your agency will be able select a trust model to
suit the specific needs of the involved parties. This decision is often affected by existing
infrastructure availability, business requirements, privacy considerations, and granular attribute
release needs. 






















