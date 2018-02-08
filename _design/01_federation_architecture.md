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

You will find three commonly used federation architectures. Each of these architectures has a common set of functionalities - the ability to integrate with a CSP, parse an assertion, and link accounts. However, you will see variations to how those requirements are implemented. Each of these solution architectures are discussed in further detail including a high-level overview, key considerations, and the requirements associated with each model. 

- [Stand-Alone Application](#stand-alone-application)
- [Enterprise Federation](#enterprise-federation)
- [Federation Broker](#federation-broker)

To select a solution architecture, you should understand which architecture is most applicable to your agency’s situation. We recommended that your agency use the information collected from the assessments during the agency’s planning period to select the [solution architecture](#architecture-selection).

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



## Stand-Alone Application

The stand-alone application architecture receives identity assertions from an IdP. In this architecture, applications require integration effort on an individual basis. That is, if two applications require third-party credentials from the same CSP, the applications will need to integrate with that CSP separately. This architecture is illustrated in the figure below.

<div style="text-align:center"><img src="{{site.baseurl}}/img/stand-alone.png"/></div>

The stand-alone application architecture works by individually enabling federation support for each application, creating a many-to-many relationship between the CSPs and applications. The application will need to be modified so that it can communicate with the CSP and accept third-party credentials. This can be accomplished through application specific plug-ins or custom code. These plug-ins and custom code allow the application to parse the assertion sent by the CSP. Whenever a CSP is added, modified, or removed, the plug-ins and/or custom code of each application may need to be updated.

The table below provides an overview of how the architecture requirements for a stand-alone federation approach are implemented.

| <center> Architecture Requirement </center> | <center> Implementation Location </center> | <center> Number of Implementations </center> | 
|:--------------------------:|:---------------------:|:--------------------:|
| **CSP Discovery Page** | Application | Once per application |
| **CSP Integration** | Application | Once per CSP/application combination | 
| **Assertion Parsing** | Application | Once per CSP/application combination | 
| **Assertion Translation** | N/A | N/A |
| **Authorization Enforcement** | Application | Once per application | 
| **Account Provisioning and Linking** | Application | Once per application |

This architecture approach does not provide scalability for agencies with many applications, as the effort required compounds with the addition of each application. The considerations for an RP implementing this architecture include:

> * Requiring per application updates to support onboarding, modification, and off-boarding of CSPs; 

> * Requiring ongoing maintenance efforts to upkeep each application’s federation capability. Since the federation capability is a customization to the application, the agency will need to retain the knowledge and skillset to maintain the application; 

> * Customizing the application may affect future updates and patches released by the vendor of the application; 

> * Providing a low effort method to pilot the acceptance of third-party credentials before implementing a more robust solution; and 

> * Requiring minimal implementation effort when an agency has a limited number of applications. 

>> * Stand-Alone Application Deployment may not be the optimal solution if an agency has more than several applications it wishes to enable the acceptance of third-party credentials. The initial expenditure and maintenance cost of this approach increases in a linear fashion with each application that is federation enabled. For an agency that will enable more than three or four applications, another approach is recommended to reduce overall cost.

## Enterprise Federation

The enterprise federation architecture employs a centralized federation server for the agency. In this architecture, the centralized federation server establishes a connection with various CSPs. This integration enables applications within the agency to accept third-party credentials from those CSPs. The CSP integration is a one-time activity per CSP, as opposed to the stand-alone application architecture, where each application has to separately integrate with each CSP. This architecture is shown in the figure below.

<div style="text-align:center"><img src="{{site.baseurl}}/img/fed-arch.png"/></div>

The enterprise federation architecture works by connecting each CSP to a centralized federation server, thus creating a one-to-many relationship between the CSPs and agency. Internal to the agency, the federation server is integrated with an access management server and/or the applications. Integrating the federation server with the access manager enables the agency to enrich the existing authentication connection, between the access manager and the applications, with federation capabilities provided by the federation server. The integration between the federation server and access management server (or applications) is accomplished through connectors, which may require modification to the application. A connector is a small extension to a federation server, which contains the required code to perform the tasks required to establish a connection to an application. These connectors are supplied by the federation server vendor, a third party, or developed by the RP.

The table below provides an overview of how the architecture requirements for an enterprise federation approach are implemented.

| <center> Architecture Requirement </center> | <center> Implementation Location </center> | <center> Number of Implementations </center> | 
|:--------------------------:|:---------------------:|:--------------------:|
| **CSP Discovery Page** | Access Management Server | Once |
| **CSP Integration** | Federation Server | Once per CSP | 
| **Assertion Parsing** | Federation Server | Once | 
| **Assertion Translation** | Federation Server | Once |
| **Authorization Enforcement** | Access Management Server** | Once | 
| **Account Provisioning and Linking** | Federation Server*** | Once per application |

** *If the federation server directly integrates with an application, the application will have to accept the assertion for authentication.*

*** *Several federation server Commercial Off-The-Shelf (COTS) products are capable of lightweight account management activities such as local profile creation and linking of users. If the agency requires more provisioning functionality, an identity manager would be needed.*

Some agencies may have already established a centralized user directory, which allows application provisioning, linking, and other similar activities to occur once at the directory, rather than once per application.

The enterprise federation architecture is a scalable and robust architecture for enabling federation within an agency. The considerations for an RP implementing this architecture include: 

> * Requiring more initial effort and investment than other architectural options; 

> * Allowing an agency to add applications and CSPs through the use of connectors, which provide a reusable framework to integrate applications with the federation server, thereby reducing future life cycle cost associated with the system; 

> * Providing the ability to scale from a single application to many applications; and 

> * Enabling the agency to maintain control of the federation process, including selection and configuration of CSPs.

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
| **Stand-Alone** | • An agency has a small number of applications that require the acceptance of third-party credentials. <br><br> • An agency wishes to pilot the acceptance of third-party credentials on a small scale before deploying it for the entire agency. |
| **Enterprise** | • An agency wishes to maintain control of which Credential Service Providers (CSPs) are integrated and the connection to those CSPs. <br><br> • An agency has many applications that are required to accept third-party credentials. <br><br> • An agency has existing agency-wide infrastructure that can be modified/augmented to accept third-party credentials. |
| **Federation Broker** | • An agency has many applications that are required to accept third-party credentials. <br><br> • An agency has existing agency-wide infrastructure that can be modified/augmented to accept third-party credentials. <br><br> • An agency wishes to accept third-party credentials from a large user base that spans many CSPs. <br><br> • An agency with privacy requirements to accept externally-issued credentials without knowing to which CSP a user authenticated. |

























