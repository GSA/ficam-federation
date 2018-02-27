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

You should select a federation architecture that is most applicable to you.

Federation architectures have a common set of functionalities - the ability to integrate with an Identity Provider (IdP), parse an assertion, and link accounts. However, you will see variations in how they connect to each other. 

- [Stand-Alone Application](#stand-alone-application)
- [Enterprise Federation](#enterprise-federation)
- [Federation Broker](#federation-broker)

We recommended that you use the information collected from the assessments during the planning period to select the solution architecture.

## Stand-Alone Application

The IdP and SP establishes a direct connection with each other based on the trust relationship between them. You will find this as the simplest solution for establishing federation. 

<div style="text-align:center"><img src="{{site.baseurl}}/img/stand-alone.png"/></div>

**Advantages**:
- This approach provides you with the flexibility in defining the data sharing model that only relates to the two applications.
- Requiring minimal implementation effort when an agency has a limited number of applications. 
- Requires the lowest effort to pilot the federation of identity before implementing a more robust solution.

**Disadvantages**:
- You may limit yourself to data exchange agreements between the IdP and SP.
- It may not be flexible enough to expand the federation beyond the two entities in the future.
- This approach does not provide scalability for agencies with many applications.
- Effort required to integrate additional applications increases, requiring per application updates to support onboarding, modification, and off-boarding of CSPs.

An example of this pattern is the Defense Support of Civil Authorities pilot program between DHS and DoD. It involved the exchange of data between the two agencies for the purpose of enabling DoD personnel to access DHS resources. The Defense Support of Civil Authorities pilot program involved only two organizations and the point-to-point model was deemed the most appropriate.

## Enterprise Federation

You will find this architecture in a typical federation scenario where a single enterprise application acts as the federation server for a number of SPs within your agency. The federation server integrates with each of the Identity Providers (IdPs) instead of the SPs directly.

<div style="text-align:center"><img src="{{site.baseurl}}/img/fed-arch.png"/></div>

**Advantages**:
- The federation server provides the federation services for all the SPs.
- Simplification of the federation process for all SPs because the integration is with one federation server application.
- Provides scalability to add more applications in the future since the integration is simpler.
- You will control the IdPs that the SP applications can accept third-party credentials from.

**Disadvantages**:
- The federation process is limited to the capability of the federation server.
- The effort and investment needed to stand up an enterprise federation service is higher than the stand-alone option.

An example is GSA's federation server setup for all the GSA wide applications that integrate with it. All GSA users who have an account can use this service to access the applications.

## Federation Broker

The federation broker provides a proxy service between the IdPs and your agency's federation server. Often the federation broker is provided as a service to all agencies. An example is OMB‘s **Max.gov**. It acts as a central federation broker that each agency can connect to and share data with other agencies. The broker model was appropriate to consolidate data in a single location that could enforce strict access restrictions.

<div style="text-align:center"><img src="{{site.baseurl}}/img/fed-broker.png"/></div>

**Advantages**:
- The Federation broker handles all interactions with the external IdPs.
- Provides the SP with a selection of IdPs that have federation capabilities for different users similar to a networked architecture. 
- Removes the need for the SP to manage and configure individual IdP connections, including the onboarding, modification, and off-boarding. 
- Provides the ability to scale from a single application to many applications. 

**Disadvantages**:
- Introduces security risks due to user information being passed through a third party before arriving at the SP. The SP should review the federation broker’s policies and make a determination if the trade off in security is worth the convenience of reduced integration effort; 
- It limits you to the selection of IdPs to those that the federation broker is connected to.
- You may not have control over which third-party credentials are allowed since that is decided by the broker.


























