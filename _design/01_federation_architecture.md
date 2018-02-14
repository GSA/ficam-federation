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

You will find three commonly used federation architectures. Each of them have a common set of functionalities - the ability to integrate with a IdP, parse an assertion, and link accounts. However, you will see variations to how those requirements are implemented. 

- [Point-to-Point](#point-to-point)
- [Hub-and-Spoke](#hub-and-spoke)
- [Networked](#networked)

To select a solution architecture, you should understand which architecture is most applicable to you. We recommended that you use the information collected from the assessments during the planning period to select the [solution architecture](#architecture-selection).

## Point-to-Point 

This pattern establishes a bi-lateral trust agreement between two parties to exchange data directly.

<div style="text-align:center"><img src="{{site.baseurl}}/img/point-to-point.png"/></div>

- This approach provides you with the flexibility in defining the data sharing model that only relates to the two applications.
- The downside of this model is that it may be limited to data exchange agreements between the two and may not be flexible to expand the federation beyond the two entities in the future.

An example of this pattern is the Defense Support of Civil Authorities pilot program between DHS and DoD. It involved the exchange of data between the two agencies for the purpose of enabling DoD personnel to access DHS resources. The Defense Support of Civil Authorities pilot program involved only two organizations and the point-to-point model was deemed the most appropriate.

This architecture approach does not provide scalability for agencies with many applications, as the effort required compounds with the addition of each application. The considerations for an RP implementing this architecture include:

> * Requiring per application updates to support onboarding, modification, and off-boarding of CSPs; 

> * Requiring ongoing maintenance efforts to upkeep each application’s federation capability. Since the federation capability is a customization to the application, the agency will need to retain the knowledge and skillset to maintain the application; 

> * Customizing the application may affect future updates and patches released by the vendor of the application; 

> * Providing a low effort method to pilot the acceptance of third-party credentials before implementing a more robust solution; and 

> * Requiring minimal implementation effort when an agency has a limited number of applications. 

>> * Stand-Alone Application Deployment may not be the optimal solution if an agency has more than several applications it wishes to enable the acceptance of third-party credentials. The initial expenditure and maintenance cost of this approach increases in a linear fashion with each application that is federation enabled. For an agency that will enable more than three or four applications, another approach is recommended to reduce overall cost.

## Hub-and-Spoke

You will find this pattern in a typical federation scenario where a single enterprise application acts as the identity provider for a number of service providers.

<div style="text-align:center"><img src="{{site.baseurl}}/img/hub-and-spoke.png"/></div>

- The identity provider do not communicate with each other; all communication and information exchange occurs through the identity provider. 
- The benefits are simplification of the federation process for all SP since one IdP dictates the data exchange. 
- The drawback of this approach is that the federation process is limited to the capability of the IdP to provide the data requirement for all.

An example is OMB‘s **Max.gov**. It acts as a central identity provider that each agency can connect
to in order to communicate and share data with other agencies. The hub-and-spoke model was 
appropriate to consolidate data in a single location that could enforce strict access restrictions.

*** *Several federation server Commercial Off-The-Shelf (COTS) products are capable of lightweight account management activities such as local profile creation and linking of users. If the agency requires more provisioning functionality, an identity manager would be needed.*

Some agencies may have already established a centralized user directory, which allows application provisioning, linking, and other similar activities to occur once at the directory, rather than once per application.

The enterprise federation architecture is a scalable and robust architecture for enabling federation within an agency. The considerations for an RP implementing this architecture include: 

> * Requiring more initial effort and investment than other architectural options; 

> * Allowing an agency to add applications and CSPs through the use of connectors, which provide a reusable framework to integrate applications with the federation server, thereby reducing future life cycle cost associated with the system; 

> * Providing the ability to scale from a single application to many applications; and 

> * Enabling the agency to maintain control of the federation process, including selection and configuration of CSPs.


## Networked 

In this scenario, the Service Providers may be connected to one or more Identity Providers.

<div style="text-align:center"><img src="{{site.baseurl}}/img/networked.png"/></div>

- More flexibility in integrating Service Providers with one or more approved Identity Providers. 
- Allows for interoperability and de-centralized data sharing while allowing a broader set of user population to federate.
- The complexity of maintaining the federation agreement over time increases as changes to one starts to affect others. 
- A networked approach will require oversight and co-ordination between the entities involved.

An example is the **InCommon** Federation. Though InCommon does not provide any of the services itself, it uses the networked model to manage a common trust and technology framework that enables Service Providers to quickly establish peer-to-peer connections to any of the Identity Providers in research and higher education.



## Federation Broker

The federation broker architecture provides infrastructure that is external to the agency and acts as a proxy between the RP and a CSP. The federation broker is a shared service model, an approach encouraged by the Federal IT Shared Services Strategy. This infrastructure handles the integration with individual CSPs and the translation of the protocols that the CSP uses to one standardized format for the RP. The federation broker architecture is shown in the figure below.

<div style="text-align:center"><img src="{{site.baseurl}}/img/fed-broker.png"/></div>

A federation broker architecture is similar to the enterprise federation architecture; however, this architecture employs a third party (i.e., the federation broker) that creates a bridge between the CSPs and an agency. The infrastructure at the agency needs to be able to receive and parse assertions; therefore, a federation server is recommended. When establishing the secure communications channel with the federation broker, part of the configuration will include the acceptable assurance level for each RP application and the attributes that are required by the RP. Applications within the agency that are integrated with the federation server will be able to use the CSPs that are offered by the federation broker.

The table below provides an overview of how the architecture requirements for a federation broker approach are implemented. The requirements assume the implementation of an access management server. If an access management server is not deployed, then each application will have to implement the requirements designated for the access management server.

| <center> Architecture Requirement </center> | <center> Implementation Location </center> | <center> Number of Implementations </center> | 
|:--------------------------:|:---------------------:|:--------------------:|
| **CSP Discovery Page** | Access Management Server | Once |
| **CSP Integration** | Cloud Provider| Once per CSP | 
| **Assertion Parsing** | Federation Server | Once | 
| **Assertion Translation** | Federation Server | Once |
| **Authorization Enforcement** | Access Management Server | Once | 
| **Account Provisioning and Linking** | Application | Once per application |

The federation broker provides a scalable architecture that enables the RP to outsource some of the functionality required to accept third-party credentials. The considerations for an RP implementing this architecture include: 

> * Removing the need for the RP to manage and configure CSP connections, including the onboarding, modification, and off-boarding; 

> * Providing the RP with a selection of CSPs that have been vetted by the TFPAP process, allowing the RP to choose a CSP that meets its requirements; 

> * Providing the ability to scale from a single application to many applications; 

> * Introducing security risks due to user information being passed through a third party before arriving at the RP. The RP should review the federation broker’s policies and make a determination if the trade off in security is worth the convenience of reduced integration effort; 

> * Limiting the selection of CSPs to those that the federation broker has available; and 

> * Requiring only one protocol to interact with the federation broker rather than the RP having to accommodate the protocol supported by each different CSP.

## Architecture Selection

The table below provides guidance to the applicability of each architectural solution. Within the table, the enterprise and federation broker architecture solutions share certain situations where either one may be appropriate. These approaches both support streamlined integration of multiple applications but differ in the amount of control the agency keeps in implementing and managing the federation solution. An agency should consider each of its requirements to determine the best architectural approach.

| <center> Recommended Approach </center> | <center> Situations </center> | 
|:---------------------------------------:|-------------------------------|
| **Point-to-Point** | • An agency has a small number of applications that require the acceptance of third-party credentials. <br><br> • An agency wishes to pilot the acceptance of third-party credentials on a small scale before deploying it for the entire agency. |
| **Hub-and-Spoke** | • An agency wishes to maintain control of which Credential Service Providers (CSPs) are integrated and the connection to those CSPs. <br><br> • An agency has many applications that are required to accept third-party credentials. <br><br> • An agency has existing agency-wide infrastructure that can be modified/augmented to accept third-party credentials. |
| **Networked** | • An agency has many applications that are required to accept third-party credentials. <br><br> • An agency has existing agency-wide infrastructure that can be modified/augmented to accept third-party credentials. <br><br> • An agency wishes to accept third-party credentials from a large user base that spans many CSPs. <br><br> • An agency with privacy requirements to accept externally-issued credentials without knowing to which CSP a user authenticated. |

























