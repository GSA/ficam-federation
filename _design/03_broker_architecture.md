#---
layout: default
title: Federation Broker
permalink: design/federation_broker/
collection: design
pubDate: 
#---

- Audience: Engineer/Architect

The federation broker architecture provides infrastructure that is external to the agency and acts as a proxy between the RP and a CSP. The federation broker is a shared service model, an approach encouraged by the Federal IT Shared Services Strategy. This infrastructure handles the integration with individual CSPs and the translation of the protocols that the CSP uses to one standardized format for the RP. The federation broker architecture is shown in the figure below.

<br>

<div style="text-align:center"><img src="{{site.baseurl}}/img/fed-broker.png"/></div>

<br>

A federation broker architecture is similar to the enterprise federation architecture; however, this architecture employs a third party (i.e., the federation broker) that creates a bridge between the CSPs and an agency. The infrastructure at the agency needs to be able to receive and parse assertions; therefore, a federation server is recommended. When establishing the secure communications channel with the federation broker, part of the configuration will include the acceptable assurance level for each RP application and the attributes that are required by the RP. Applications within the agency that are integrated with the federation server will be able to use the CSPs that are offered by the federation broker.

The table below provides an overview of how the architecture requirements for a federation broker approach are implemented. The requirements assume the implementation of an access management server. If an access management server is not deployed, then each application will have to implement the requirements designated for the access management server.

<br>

| <center> Architecture Requirement </center> | <center> Implementation Location </center> | <center> Number of Implementations </center> | 
|:--------------------------:|:---------------------:|:--------------------:|
| **CSP Discovery Page** | Access Management Server | Once |
| **CSP Integration** | Cloud Provider| Once per CSP | 
| **Assertion Parsing** | Federation Server | Once | 
| **Assertion Translation** | Federation Server | Once |
| **Authorization Enforcement** | Access Management Server | Once | 
| **Account Provisioning and Linking** | Application | Once per application |

<br>

The federation broker provides a scalable architecture that enables the RP to outsource some of the functionality required to accept third-party credentials. The considerations for an RP implementing this architecture include: 

> * Removing the need for the RP to manage and configure CSP connections, including the onboarding, modification, and off-boarding; 

> * Providing the RP with a selection of CSPs that have been vetted by the TFPAP process, allowing the RP to choose a CSP that meets its requirements; 

> * Providing the ability to scale from a single application to many applications; 

> * Introducing security risks due to user information being passed through a third party before arriving at the RP. The RP should review the federation broker’s policies and make a determination if the trade off in security is worth the convenience of reduced integration effort; 

> * Limiting the selection of CSPs to those that the federation broker has available; and 

> * Requiring only one protocol to interact with the federation broker rather than the RP having to accommodate the protocol supported by each different CSP.
























