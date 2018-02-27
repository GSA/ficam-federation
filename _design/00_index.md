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
- FICAM TFS Relying Party Doc Section 3.1.2 - Direct Authentication with PKI Credentials. 

============================

You should consider these topics when designing your Agency's Federation.

## Federation Architecture

If you want to design a federation implementation, you will find a number of different approaches that your agency might find suitable. These approaches will differ based on:

- The number of Service Provider (SP) applications that you are planning to federate now and in the future.
- The different types of authenticator requirements for your users.
- The number of Identity Providers (IdPs) that you will have to integrate with.
- The type of relationship and the level of trust that exists with these IdPs. 
- The existing infrastructure for Enterprise Single Sign-on (SSO) and/or federation services.

Your existing ICAM investments, such as modernized Logical Access Control Systems (LACS), may also provide additional capabilities that could impact the federation architecture. These additional factors may drive an agency to adopt a hybrid approach that combines elements of multiple topologies, resulting in a model that closely represents the agency‘s needs. 

You should learn more about different [Federation Architectures](federationarch) before designing your solution.

## Federation Protocols

When you design your agency's federation process, you should use follow these principles.

- Use a common exchange protocol for exchanging assertions.
- Assertion protocols should be agreed-upon open standards/specifications to allow interoperability.
- Build a trust relation with the IdPs when federating outside of your agency. 

In a federated environment, these transactions occur between trusted Identity Providers that are deemed suitable for your user population. Given the nature of the federated transactions and the electronic exchange of identity data across organizational boundaries, there is an increased focus on security and privacy to ensure users' sensitive identity data is appropriately safeguarded. 

When establishing a new federation, you should select a [Federation Protocol](federation_protocols) that suits the specific needs of the involved applications. However, this decision is often affected by existing infrastructure availability, business requirements, privacy considerations, and granular attribute release needs.






















