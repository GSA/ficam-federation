#---
layout: default
title: Enterprise Federation
permalink: design/enterprise_federation/
collection: design
pubDate: 
#---

- Audience: Engineer/Architect

The enterprise federation architecture employs a centralized federation server for the agency. In this architecture, the centralized federation server establishes a connection with various CSPs. This integration enables applications within the agency to accept third-party credentials from those CSPs. The CSP integration is a one-time activity per CSP, as opposed to the stand-alone application architecture, where each application has to separately integrate with each CSP. This architecture is shown in the figure below.

<br>

<div style="text-align:center"><img src="{{site.baseurl}}/img/fed-arch.png"/></div>

<br>

The enterprise federation architecture works by connecting each CSP to a centralized federation server, thus creating a one-to-many relationship between the CSPs and agency. Internal to the agency, the federation server is integrated with an access management server and/or the applications. Integrating the federation server with the access manager enables the agency to enrich the existing authentication connection, between the access manager and the applications, with federation capabilities provided by the federation server. The integration between the federation server and access management server (or applications) is accomplished through connectors, which may require modification to the application. A connector is a small extension to a federation server, which contains the required code to perform the tasks required to establish a connection to an application. These connectors are supplied by the federation server vendor, a third party, or developed by the RP.

The table below provides an overview of how the architecture requirements for an enterprise federation approach are implemented.

<br>

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

























