---
layout: page_collection
title: Select and Develop the Optimal Solution Architecture
collection: design
permalink: design/2_solution-arch/
---
<script>
$(function() {
  $( "#accordion" ).accordion({
    heightStyle: "content",
    collapsible: "true",
    active: "false"
  });
});
</script>
---------------------------------------------------------

In order for an agency to select a solution architecture, it is important to understand which architecture is most applicable to its situation. It is recommended that an agency use the information collected from the assessments during the agency's planning period to determine its optimal solution architecture. 

The chart below provides guidance to the applicability of each architectural solution. Within the chart, the enterprise and federation broker architecture solutions share certain situations where either one may be appropriate. These approaches both support streamlined integration of multiple applications but differ in the amount of control the agency keeps in implementing and managing the federation solution. An agency should consider each of its requirements to determine the best architectural approach.

<br>

| <center> Recommended Approach </center> | <center> Situations </center> |
|:----------------------------------------:|------------------------------|
| **Stand-Alone** | • An agency has a small number of applications that require the acceptance of third-party credentials. <br><br> • An agency wishes to pilot the acceptance of third-party credentials on a small scale before deploying it for the entire agency. |
| **Enterprise** | • An agency wishes to maintain control of which Credential Service Providers (CSPs) are integrated and the connection to those CSPs. <br><br> • An agency has many applications that are required to accept third-party credentials. <br><br>• An agency has existing agency-wide infrastructure that can be modified/augmented to accept third-party credentials. |
| **Federation Broker** | •	An agency has many applications that are required to accept third-party credentials. <br><br> • An agency has existing agency-wide infrastructure that can be modified/augmented to accept third-party credentials. <br><br> •	An agency wishes to accept third-party credentials from a large user base that spans many CSPs. <br><br> • An agency with privacy requirements to accept externally-issued credentials without knowing to which CSP a user authenticated. |

<br>

Within this section, each of these solution architectures are discussed in further detail including a high-level overview, key considerations, and the requirements associated with each model.

<br>

### Stand-Alone Application Architecture

The stand-alone application architecture directly enables the application to receive identity assertions from a CSP. In this architecture, applications require integration effort on an individual basis. That is, if two applications require third-party credentials from the same CSP, the applications will need to integrate with that CSP separately. This architecture is illustrated in the figure below.

<br>

<div style="text-align:center"><img src="{{site.baseurl}}/img/stand-alone.png"/></div>

<br>

The stand-alone application architecture works by individually enabling federation support for each application, creating a many-to-many relationship between the CSPs and applications. The application will need to be modified so that it can communicate with the CSP and accept third-party credentials. This can be accomplished through application specific plug-ins or custom code. These plug-ins and custom code allow the application to parse the assertion sent by the CSP. Whenever a CSP is added, modified, or removed, the plug-ins and/or custom code of each application may need to be updated.

The chart below provides an overview of how the architecture requirements for a stand-alone federation approach are implemented. 

<br>

| **Architecture Requirement** | <center> Implementation Location </center> | <center> Number of Implementations </center> |
|:----------------------------:|---------------|---------|
| **CSP Discovery Page** | <center> Application </center> | <center> Once per application </center> |
| **CSP Integration** | <center> Application </center> | <center> Once per CSP/application combination </center> |
| **Assertion Parsing** | <center> Application </center> | <center> Once per CSP/application combination </center> |
| **Assertion Translation** | <center> N/A </center> | <center> N/A </center> |
| **Authorization Enforcement** | <center> Application </center> | <center> Once per application </center> |
| **Account Provisioning and Linking** | <center> Application </center> | <center> Once per application </center> |

<br>

This architecture approach does not provide scalability for agencies with many applications, as the effort required compounds with the addition of each application. The considerations for an RP implementing this architecture include:

* Requiring per application updates to support onboarding, modification, and off-boarding of CSPs;
<br>

* Requiring ongoing maintenance efforts to upkeep each application’s federation capability. Since the federation capability is a customization to the application, the agency will need to retain the knowledge and skillset to maintain the application;
<br>

* Customizing the application may affect future updates and patches released by the vendor of the application;
<br>

* Providing a low effort method to pilot the acceptance of third-party credentials before implementing a more robust solution; and
<br>

* Requiring minimal implementation effort when an agency has a limited number of applications.
<br>

	* Stand-Alone Application Deployment may not be the optimal solution if an agency has more than several applications it wishes to enable the acceptance of third-party credentials. The initial expenditure and maintenance cost of this approach increases in a linear fashion with each application that is federation enabled. For an agency that will enable more than three or four applications, another approach is recommended to reduce overall cost.

<br>

### Enterprise Federation Architecture

The enterprise federation architecture employs a centralized federation server for the agency. In this architecture, the centralized federation server establishes a connection with various CSPs. This integration enables applications within the agency to accept third-party credentials from those CSPs. The CSP integration is a one-time activity per CSP, as opposed to the stand-alone application architecture, where each application has to separately integrate with each CSP. This architecture is shown in the figure below.

<br>

<div style="text-align:center"><img src="{{site.baseurl}}/img/fed-arch.png"/></div>

<br>

The enterprise federation architecture works by connecting each CSP to a centralized federation server, thus creating a one-to-many relationship between the CSPs and agency. Internal to the agency, the federation server is integrated with an access management server and/or the applications. Integrating the federation server with the access manager enables the agency to enrich the existing authentication connection, between the access manager and the applications, with federation capabilities provided by the federation server. The integration between the federation server and access management server (or applications) is accomplished through connectors, which may require modification to the application. A connector is a small extension to a federation server, which contains the required code to perform the tasks required to establish a connection to an application. These connectors are supplied by the federation server vendor, a third party, or developed by the RP. 

The chart below provides an overview of how the architecture requirements for an enterprise federation approach are implemented. 

<br>

| **Architecture Requirement** | <center> Implementation Location </center> | <center> Number of Implementations </center> |
|--------------------------------------------|
| **CSP Discovery Page** | <center> Access Management Server </center> | Once |
| **CSP Integration** | <center> Federation Server </center> | Once per CSP |
| **Assertion Parsing** | <center> Federation Server </center> | Once |
| **Assertion Translation** | <center> Federation Server </center> | Once |
| **Authorization Enforcement** | <center> Access Management Server** </center> | Once |
| **Account Provisioning and Linking** | <center> Federation Server*** </center> | Once per application |

** *If the federation server directly integrates with an application, the application will have to accept the assertion for authentication.*

*** *Several federation server Commercial Off-The-Shelf (COTS) products are capable of lightweight account management activities such as local profile creation and linking of users. If the agency requires more provisioning functionality, an identity manager would be needed.*

<br>

Some agencies may have already established a centralized user directory, which allows application provisioning, linking, and other similar activities to occur once at the directory, rather than once per application.

The enterprise federation architecture is a scalable and robust architecture for enabling federation within an agency. The considerations for an RP implementing this architecture include:
<br>

* Requiring more initial effort and investment than other architectural options;
<br>

* Allowing an agency to add applications and CSPs through the use of connectors, which provide a reusable framework to integrate applications with the federation server, thereby reducing future life cycle cost associated with the system;
<br>

* Providing the ability to scale from a single application to many applications; and
<br>

* Enabling the agency to maintain control of the federation process, including selection and configuration of CSPs.

<br>

### Federation Broker Architecture

The federation broker architecture provides infrastructure that is external to the agency that acts as a proxy between the RP and a CSP. The federation broker is a shared service model, an approach encouraged by the Federal IT Shared Services Strategy. This infrastructure handles the integration with individual CSPs and the translation of the protocols that the CSP uses to one standardized format for the RP. The federation broker architecture is shown in the figure below. 

<br>

<div style="text-align:center"><img src="{{site.baseurl}}/img/fed-broker.png"/></div>

<br>

A federation broker architecture is similar to the enterprise federation architecture; however, this architecture employs a third party (i.e., the federation broker) that creates a bridge between the CSPs and an agency. The infrastructure at the agency needs to be able to receive and parse assertions; therefore, a federation server is recommended. When establishing the secure communications channel with the federation broker, part of the configuration will include the acceptable assurance level for each RP application and the attributes that are required by the RP. Applications within the agency that are integrated with the federation server will be able to leverage the CSPs that are offered by the federation broker. 

The chart below provides an overview of how the architecture requirements for a federation broker approach are implemented. The requirements assume the implementation of an access management server. If an access management server is not deployed, then each application will have to implement the requirements designated for the access management server.

<br>

| **Architecture Requirement** | <center> Implementation Location </center> | <center> Number of Implementations </center> |
|--------------------------------------------|
| **CSP Discovery Page** | <center> Access Management Server </center> | Once |
| **CSP Integration** | <center> Cloud Provider </center> | Once per CSP |
| **Assertion Parsing** | <center> Federation Server </center> | Once |
| **Assertion Translation** | <center> Federation Server </center> | Once |
| **Authorization Enforcement** | <center> Access Management Server </center> | Once |
| **Account Provisioning and Linking** | <center> Application </center> | Once per application |

<br>

The federation broker provides a scalable architecture that enables the RP to outsource some of the functionality required to accept third-party credentials. The considerations for an RP implementing this architecture include:
<br>

* Removing the need for the RP to manage and configure CSP connections, including the onboarding, modification, and off-boarding;
<br>

* Providing the RP with a selection of CSPs that have been vetted by the TFPAP process, allowing the RP to choose a CSP that meets its requirements;
<br>

* Providing the ability to scale from a single application to many applications;
<br>

* Introducing security risks due to user information being passed through a third party before arriving at the RP. The RP should review the federation broker’s policies and make a determination if the trade off in security is worth the convenience of reduced integration effort;
<br>

* Limiting the selection of CSPs to those that the federation broker has available; and
<br>

* Requiring only one protocol to interact with the federation broker rather than the RP having to accommodate the protocol supported by each different CSP.











