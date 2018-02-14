---
layout: default
title: Federation Architecture  
permalink: /design/federationarch/
collection: design
pubDate: 
---

- Audience: Engineer/Architect
- Define the criteria for selecting architecture. Detail the different types of architecture patterns.
- Relying Party document section 6.2 - Developing the Solution Architecture.
- FICAM Roadmap section 12.1.2 Federation Trust Topologies

============================

To select a solution architecture, you should understand which architecture is most applicable to you. 

Commonly used federation architectures have a common set of functionalities - the ability to integrate with an Identity Provider (IdP), parse an assertion, and link accounts. However, you will see variations in how they connect to each other. 

- [Point-to-Point](#point-to-point)
- [Hub-and-Spoke](#hub-and-spoke)
- [Networked](#networked)
- [Federation Broker](#federation-broker)

We recommended that you use the information collected from the assessments during the planning period to select the [solution architecture](#architecture-selection).

## Point-to-Point 

This pattern establishes a bi-lateral trust agreement between two parties to exchange data directly.

<div style="text-align:center"><img src="{{site.baseurl}}/img/point-to-point.png"/></div>

Point-to-Point deployment may not be the optimal solution if an agency has more than several applications it wishes to enable federation. The initial expenditure and maintenance cost of this approach increases in a linear fashion with each application that is federation enabled. 

**Advantages**:
- This approach provides you with the flexibility in defining the data sharing model that only relates to the two applications.
- Requiring minimal implementation effort when an agency has a limited number of applications. 
- Provides a low effort method to pilot the acceptance of third-party credentials before implementing a more robust solution.

**Disadvantages**:
- It may limit you to data exchange agreements between the IdP and SP and may not be flexible to expand the federation beyond the two entities in the future.
- This architecture approach does not provide scalability for agencies with many applications.
- Effort required compounds with the addition of each application; requiring per application updates to support onboarding, modification, and off-boarding of CSPs. 

An example of this pattern is the Defense Support of Civil Authorities pilot program between DHS and DoD. It involved the exchange of data between the two agencies for the purpose of enabling DoD personnel to access DHS resources. The Defense Support of Civil Authorities pilot program involved only two organizations and the point-to-point model was deemed the most appropriate.

## Hub-and-Spoke

You will find this pattern in a typical federation scenario where a single enterprise application acts as the identity provider for a number of service providers.

<div style="text-align:center"><img src="{{site.baseurl}}/img/hub-and-spoke.png"/></div>

**Advantages**:
- The IdP provides the federation services for all the SPs.
- If your user wants to switch between multiple SPs, it has to federate via the IdP.
- The IdP may be the Federation service of the Enterprise Single Sign-on application.
- Simplification of the Federation process for all SPs because the IdP is the same.

**Disadvantages**:
- The federation process is limited to the capability of the IdP.

An example is OMB‘s **Max.gov**. It acts as a central identity provider that each agency can connect
to in order to communicate and share data with other agencies. The hub-and-spoke model was 
appropriate to consolidate data in a single location that could enforce strict access restrictions.

## Networked 

In this scenario, the SPs may be connected to one or more IdPs. 

<div style="text-align:center"><img src="{{site.baseurl}}/img/networked.png"/></div>

**Advantages**:
- You will find more flexibility in integrating SPs with one or more IdPs. 
- Allows for interoperability and de-centralized data sharing.
- Allows a broader set of user population to federate since each IdP may have authentication services for different users.

**Disadvantages**:
- The complexity of maintaining the federation agreement over time increases as changes to one starts to affect others. 
- A networked approach will require oversight and co-ordination between the applications involved.

An example is the **InCommon** Federation. Although InCommon does not provide any of the services itself, it uses the networked model to manage a common trust and technology framework that enables Service Providers to quickly establish peer-to-peer connections to any of the Identity Providers in research and higher education.

## Federation Broker

The federation broker is a combination of the hub-and-spoke and networked architectures, where one IdP can act as a proxy to other IdPs. You can eliminate the requirement of SPs to connect to multiple IdP individually. 

<div style="text-align:center"><img src="{{site.baseurl}}/img/fed-broker.png"/></div>

The federation broker provides a scalable architecture that enables the SP to outsource some of the functionality required to accept third-party credentials.

**Advantages**:
- The Federation broker handles all interactions with the external IdPs.
- Provides the SP with a selection of IdPs that have federation capabilities for different users similar to a networked architecture. 
- Removes the need for the SP to manage and configure IdP connections, including the onboarding, modification, and off-boarding. 
- Providing the ability to scale from a single application to many applications. 

**Disadvantages**:
- This introduces security risks due to user information being passed through a third party before arriving at the SP. The SP should review the federation broker’s policies and make a determination if the trade off in security is worth the convenience of reduced integration effort; 
- It also will limit you to the selection of IdPs to those that the federation broker is connected to. 


## Architecture Selection

The table below provides guidance to the applicability of each architectural solution.

| <center> Architecture </center> | <center> Situations </center> | 
|:---------------------------------------:|-------------------------------|
| **Point-to-Point** | • An agency has a small number of applications that only caters to a small group of users. <br/><br/> • An agency wishes to pilot the acceptance of credentials on a small scale before deploying it for the entire agency. <br/><br/> •For an agency that will enable more than three or four applications, another approach is recommended to reduce overall cost.|
| **Hub-and-Spoke** | • You have or plan to have an Enterprise IdP. <br/><br> • You wish to maintain control of which IdPs are integrated. <br/><br> • You have many applications that are required to accept one set of credentials. <br/><br/> • You have flexibility in existing agency-wide infrastructure that can be modified/augmented to accept the credentials. |
| **Networked** | • You have many applications that are required to accept third-party credentials. <br/><br/> • You want to accept third-party credentials from a large user base that spans many IdPs. <br/><br/> • You have privacy requirements to accept externally-issued credentials without knowing which IdP a user authenticated to. |
| **Federation Broker** | • You want to simplify the integrations for the SPs. <br/><br/> • You want to accept third-party credentials from a large user base that spans many IdPs. <br/><br/> • You want the complexity of implementing a federation broker and establish the integrations with external IdPs. |

























