---
layout: default
title: Federation Design Patterns  
permalink: /design/
collection: design
pubDate: 
---

- Audience: Engineer/Architect
- Detail the different design patterns for federation.
- FICAM Roadmap section 12.1.2 Federation Trust Topologies

If you want to design a federation architecture, there are a number of different information sharing approaches that your agency might choose. These approaches, referred to as design patterns, will differ based on the type of relationship that exists with the external parties involved and the level of trust required for the transaction and are driven by your organization‘s business model. 

Here are the three common federation design patterns.

## Point-to-Point 

This pattern establishes a bi-lateral trust agreement between two parties to exchange data directly. 
- This approach will provide you with the flexibility in defining the data sharing model that only relates to the involved parties.
- The downside of this model is that it may be customized to data exchange agreements between the two entities and may not be flexible to expand the federation beyond the two entities in the future.

An example of this pattern is the Defense Support of Civil Authorities pilot program between DHS and DoD. 
It involved the exchange of data between the two agencies for the purpose of enabling DoD
personnel to access DHS resources. Because the Defense Support of Civil Authorities
pilot program involved only two organizations, the point-to-point model was deemed the
most appropriate.

## Hub-and-Spoke

This pattern is a typical federation scenario where a single entity acts as the identity provider for a number of service providers. 
- The service providers do not communicate with each other; all communication and information exchange occurs through the identity provider. 
- The benefits are simplification of the federation process for all SP since one IdP dictates the data
exchange. 
- The drawback of this approach is that the federation process is limited to the capability
of the IdP to provide the data requirement for all.

An example is OMB‘s **Max.gov**. It acts as a central identity provider that each agency can connect
to in order to communicate and share data with other agencies. The hub-and-spoke model was 
appropriate to consolidate data in a single location that could enforce strict access restrictions.

## Networked 

In this scenario, all entities are interconnected and can communicate and exchange data with all others. 
- Entities may choose one or more approved Identity Providers. 
- The ability to connect to multiple entities allows for interoperability and de-centralized data sharing. 
- The complexity of maintaining the federation agreement over time increases as changes to one entity starts to affect other entities. 
- A networked approach will require oversight and co-ordination between the entities involved.

An example is the **InCommon** Federation. Though InCommon does not provide
any of the services itself, it uses the networked model to manage a common trust and technology framework 
that enables Service Providers to quickly establish peer-to-peer connections to any of the Identity 
Providers in research and higher education.

When establishing a new federation, it is likely that your agency will be able select a trust model to
suit the specific needs of the involved parties. This decision is often affected by existing
infrastructure availability, business requirements, privacy considerations, and granular attribute
release needs. 

Your agency‘s existing ICAM investments, such as modernized logical access
control systems (LACS), may also provide additional capabilities that could impact the
federation topology that best meets the agency‘s needs. These additional factors may drive an
agency to adopt a hybrid approach that combines elements of multiple topologies, resulting in a
model that closely represents the agency‘s needs. 

Regardless of the federation trust topology selected, there are a number of resources that have 
been established within the Federal Government to provide agencies with a foundational level of 
trust. When entering into an established federation; however, it is likely that the existing 
federation members have already chosen a trust topology. Therefore it is important than an 
agency examine the factors previously discussed to select a federation that most closely meets 
its needs.




















