---
layout: default
title: Federation Process
permalink: plan/federationprocess/
collection: plan
pubDate: 
---
- Audience: Engineer/Architect
- Introduce Federation technology. Link to other pages (assertions, assurances and protocols) for more information. (this can be at the bottom)
- Layout the different actors in federation - CSP, AP, RP, end user. Relying Party doc Section 3.1 Federation Process.
- Include diagrams which may help in visualizing the flow of data between the actors. Example Relying Party Doc Fig 2 (Page 7).
- We're focusing on web based applications and mobile applications. 

Planning to include federation for **your application** is great for privacy, security, interoperability and efficiency.  It also requires you to understand specialized terminology to understand what to plan for, research, build, or buy.    

- Your application is the **Service Provider (SP)**.  Your application is providing a **service** that the user wants or needs to access.
- You want to allow the user to reuse their identity and login from another application.  This _other_ application is the **Identity Provider (IdP)**.
- The User is at the center of the handshake that involves Federation.  

Each application performs only their functions for the User. 

<div style="text-align:center; width:70%"><img src="{{site.baseurl}}/img/federation.png"/></div>


|  Application | What the Application Does | What the Application Does Not Do |
| :------ | :------- | :------ |
| **Service Provider** (also known as Relying Party) |  Provides the business service. <br>This could be managing email or reviewing and approving permits.	| Manage authentication or any authentication _secrets_. The service provider doesn't capture or store passwords or ??. <<br> Manage identity information.  |
| **Identity Provider** (also known as Credential Service Provider)		| establishes an individual’s identity and links the identity to a credential | 		|
| **User**	| 	requests access to an SP after authenticating to a CSP by providing his/her identity and token for verification. | 		|

<!--Should we put in another column to also include "other" terms commonly used in govt docs?
Should we explain authentication and credentials or link to another primer?   -->

Add some sentences that explain different types of Identity Providers.  Lead into Know Your Users.  

An Identity Provider might be your agency's enterprise single sign on system. 
An Identity provider might be...

Explain a scenario where an IDP is your own agency's enterprise service focused on your agency users, a govt wide service focused on government users, a govt wide service focused on a community of interest, or a service focused on consumers. 

Then add an example for each. Use something they can go see and look at.






























