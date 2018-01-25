---
layout: default
title: Federation Design Patterns  
permalink: /design/
collection: design
pubDate: 
---

- Audience: Engineer/Architect

In order to accommodate the wide range of mission and business reasons behind federation, there
are a number of different information exchange approaches that an agency might choose. These
approaches, referred to as topologies, differ based on the type of relationship that exists with the
external parties involved and the level of trust required for the transaction and are driven by the
organization‘s business model. Three common federation trust topologies are:

- **Point-to-Point**. Refers to a model in which an organization establishes a bi-lateral trust
agreement with another organization directly and uses federation protocols to exchange
data. An example of the Point-to-Point topology within the Federal Government is the
Defense Support of Civil Authorities pilot program between DHS and DoD, which
involved the exchange of data between the two agencies for the purpose of enabling DoD
personnel to access DHS resources. Because the Defense Support of Civil Authorities
pilot program involved only two organizations, the point-to-point model was deemed the
most appropriate.

- **Hub-and-Spoke**. Refers to a model in which a single entity acts as a central point of
communication and exchange for a number of relying parties. In this model, the relying
parties do not communicate with each other; all communication and information
exchange occurs through the central hub. An example of a Hub-and-Spoke topology is
OMB‘s Max.gov knowledge sharing and collaboration portal. Max.gov acts as a central
broker that each agency connects to in order to communicate and share data with other
agencies. The hub-and-spoke model was selected due to the number of parties involved
and the desire to consolidate data in a single location that could enforce strict access
restrictions.

- **Networked**. Refers to a peer-to-peer model in which all entities are interconnected and
can communicate and exchange data with all others. Entities in this model may be
leveraging one or more approved Identity Providers. An example of a Networked
topology is InCommon Federation, which provides a common framework for trustworthy
shared management of access to online resources in support of education and research.
InCommon uses the networked model because it provides a common trust and technology
fabric that enables relying parties to quickly establish peer-to-peer connections as the
need arises.

When establishing a new federation, it is likely that an agency will be able select a trust model to
suit the specific needs of the involved parties. This decision is often affected by existing
infrastructure availability, business requirements, privacy considerations, and granular attribute
release needs. An agency‘s existing ICAM investments, such as modernized logical access
control systems (LACS), may also provide additional capabilities that could impact the
federation topology that best meets the agency‘s needs. These additional factors may drive an
agency to adopt a hybrid approach that combines elements of multiple topologies, resulting in a
model that closely represents the agency‘s needs. Regardless of the federation trust topology
selected, there are a number of resources that have been established within the Federal
Government to provide agencies with a foundational level of trust. When entering into an
established federation; however, it is likely that the existing federation members have already
chosen a trust topology. Therefore it is important than an agency examine the factors previously
discussed to select a federation that most closely meets its needs.




















