#---
layout: default
navtitle: Stand-Alone Application
title: Stand-Alone Application
permalink: design/standalonefederation/
collection: design
pubDate: 
#---

- Audience: Engineer/Architect

The stand-alone application architecture directly enables the application to receive identity assertions from a CSP. In this architecture, applications require integration effort on an individual basis. That is, if two applications require third-party credentials from the same CSP, the applications will need to integrate with that CSP separately. This architecture is illustrated in the figure below.

<br>

<div style="text-align:center"><img src="{{site.baseurl}}/img/stand-alone.png"/></div>

<br>

The stand-alone application architecture works by individually enabling federation support for each application, creating a many-to-many relationship between the CSPs and applications. The application will need to be modified so that it can communicate with the CSP and accept third-party credentials. This can be accomplished through application specific plug-ins or custom code. These plug-ins and custom code allow the application to parse the assertion sent by the CSP. Whenever a CSP is added, modified, or removed, the plug-ins and/or custom code of each application may need to be updated.

The table below provides an overview of how the architecture requirements for a stand-alone federation approach are implemented.

<br>

| <center> Architecture Requirement </center> | <center> Implementation Location </center> | <center> Number of Implementations </center> | 
|:--------------------------:|:---------------------:|:--------------------:|
| **CSP Discovery Page** | Application | Once per application |
| **CSP Integration** | Application | Once per CSP/application combination | 
| **Assertion Parsing** | Application | Once per CSP/application combination | 
| **Assertion Translation** | N/A | N/A |
| **Authorization Enforcement** | Application | Once per application | 
| **Account Provisioning and Linking** | Application | Once per application |

<br>

This architecture approach does not provide scalability for agencies with many applications, as the effort required compounds with the addition of each application. The considerations for an RP implementing this architecture include:

> * Requiring per application updates to support onboarding, modification, and off-boarding of CSPs; 

> * Requiring ongoing maintenance efforts to upkeep each application’s federation capability. Since the federation capability is a customization to the application, the agency will need to retain the knowledge and skillset to maintain the application; 

> * Customizing the application may affect future updates and patches released by the vendor of the application; 

> * Providing a low effort method to pilot the acceptance of third-party credentials before implementing a more robust solution; and 

> * Requiring minimal implementation effort when an agency has a limited number of applications. 

>> * Stand-Alone Application Deployment may not be the optimal solution if an agency has more than several applications it wishes to enable the acceptance of third-party credentials. The initial expenditure and maintenance cost of this approach increases in a linear fashion with each application that is federation enabled. For an agency that will enable more than three or four applications, another approach is recommended to reduce overall cost.
























