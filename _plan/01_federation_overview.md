---
layout: default
title: Federation Overview
permalink: plan/federationprocess/
collection: plan
pubDate: 
---
- Audience: Engineer/Architect
- Introduce Federation technology. Link to other pages (assertions, assurances and protocols) for more information. (this can be at the bottom)
- Layout the different actors in federation - CSP, AP, RP, end user. Relying Party doc Section 3.1 Federation Process.
- Include diagrams which may help in visualizing the flow of data between the actors. Example Relying Party Doc Fig 2 (Page 7).
- We're focusing on web based applications and mobile applications. 

==========================================

Planning to include federation for **your application** is great for privacy, security, interoperability and efficiency.  It also requires you to understand specialized terminology to understand what to plan for, research, build, or buy.    

- Your application is the **Service Provider (SP)**.  Your application is providing a **service** that the user wants or needs to access.
- You want to allow the user to reuse their identity and login from another application.  This _other_ application is the **Identity Provider (IdP)**.
- The User is at the center of the handshake that involves Federation.  

Each application performs only their functions for the User. 

<div style="text-align:center; width:70%"><img src="{{site.baseurl}}/img/federation.png"/></div>


|  Application | What the Application Does | What the Application Does Not Do |
| :------ | :------- | :------ |
| **Service Provider (SP)** <br/>(also known as _Relying Party_) |  - Provides the business service. <br/>- This could be managing email or reviewing and approving permits. | - Manage login process or any login _secrets_. <br/>- The service provider doesn't capture or store passwords or login data. <br/>- Manage identity information.  |
| **Identity Provider (IdP)** <br/>(also known as _Credential Service Provider_)	| - Establishes an individual’s identity by verifying who the user is. <br/>- Links the identity to a credential (e.g., login/password, ID Cards). <br/> - Validates the credential to facilitate the user to login to SP.| - Does not provide the service the user wants to access. <br/> - Does not keep track of what the user does in the SP application.		|
| **User**	| 	- Requests access to an SP after authenticating to an IdP by providing his/her credential for verification. | 		|

<!--Should we put in another column to also include "other" terms commonly used in govt docs?
Should we explain authentication and credentials or link to another primer?   -->

**Identity Provider (IdP)** can be:
- **Enterprise SSO**: Your agency's enterprise Single Sign-On (SSO) system verifies that you are one of the agency's user. It also provides you with credentials to login to your agencies network. This credenatial is also used to give you access to a Service Provider (SP) application such as email or approving procurement system.

- **Government Wide Provider**: A common identity service that serves multiple agencies. An example is OMB's _max.gov_ where you can create a credential with your agency provided email address to access applications in your agency or other agencies. 
  
- **External Service**: An external IdP that allows consumers to access services. An example will be an identity application that allows fire fighters and first responders to access the services from the Department of Homeland Security (DHS).

<!-- Explain a scenario where an IDP is your own agency's enterprise service focused on your agency users, a govt wide service focused on government users, a govt wide service focused on a community of interest (LEAP, NIH itrust), or a service focused on consumers. 

 Then add an example for each. Use something they can go see and look at. -->

<!-- **Service Provider (SP)** can be:

- **Enterprise Application**: Your agency's enterprise applications, such as the email software or the procurement system, are examples of a Service Provider application.

- **Government Wide Service**: A common service provided to users of multiple agencies such as pension benefits for government workers. 
  
- **External Service**: An external facing service that focusses on consumers. Users can create logins with their personal email address to access government services. An example is the HHS's _healthcare.gov_ where you can sign-up for healthcare, or the SSA.gov for Social Security.

-->
 
In order to understand how to plan for your Federation process, you will have to understand who your users are.



























