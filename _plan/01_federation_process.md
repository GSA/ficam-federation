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

Planning to include federation for **your application** is great for privacy, security, and efficiency.  It also requires you to understand specialized terminology to understand what to plan for, research, build, or buy.    

- Your application is the **Service Provider**.  Your application is providing a **service** that the user wants or needs to access. 
- You want to allow the user to reuse their identity and authenticate from another application.  This _other_ application is the **Identity Provider**.
- The User is at the center.  

Each (service?) performs only their functions for the User. 

|  Application | What the Application Does | What the Application Does Not Do |
| :------ | :------- | :------ |
| Service Provider 		|  Provides the business service. <br>This could be managing email or reviewing and approving permits.	| Manage authentication or any authentication _secrets_. The service provider doesn't capture or store passwords or ??. <<br> Manage identity information.  |
| Identity Provider 		| establishes an individual’s identity and links the identity to a credential | 		|
| User 		| 	requests access to an SP after authenticating to a CSP by providing his/her identity and token for verification. | 		|

Should we put in another column to also include "other" terms commonly used in govt docs?  
Should we explain authentication and credentials or link to another primer?   

Add some sentences that explain different types of Identity Providers.  Lead into Know Your Users.  

An Identity Provider might be your agency's enterprise single sign on system. 
An Identity provider might be...

Explain a scenario where an IDP is your own agency's enterprise service focused on your agency users, a govt wide service focused on government users, a govt wide service focused on a community of interest, or a service focused on consumers. 

Then add an example for each.  Use something they can go see and look at.  



<div style="text-align:center; width:70%"><img src="{{site.baseurl}}/img/federation.png"/></div>



[I think all of this below can be moved to design or other.] 

During a federation transaction - 

- **Login** - The user requests access to the SP application.
- **Redirection** - The service provider checks that the user is not authenticated and redirects the user to the Identity Provider application.
- **Authentication** - The user is challenged by the Identity Provider to present a valid credential such as a username and password, or their certificate. The CSP validates the identity of the individual using the credential.
- **Assertion** - The Identity Provider sends a ???, also known as _Assertion_, that the user 
- **Session** - Once the SP verifies the assertion, it will create a session for the user. The session will last for a period of time until the SP requires the user to authenticate with the CSP again.


- **Validation** - Once the SP verifies the assertion from the CSP, it may allow access to the user to its application. The SP may request additional identity information about the user from the CSP or AP.

The above example scenario is also known as _SP initiated federation_. In case of an _IdP initiated federation_, the user requests access to the SP application by accessing the CSP application first instead of being redirected from the SP.

This data sharing between the CSP and SP is made possible through the sharing of user's authentication information via common exchange protocols and agreed-upon open standards/specifications. This will enable your agency to allow a user from another organization or trust an authentication conducted outside of your agency. 

In a federated environment, these transactions occur between trusted Identity Providers that have
been approved through the Federal Trust Framework and relying parties. Given the nature of federated transactions and the electronic exchange of identity data across organizational boundaries, there is an increased focus on security and privacy to ensure users' sensitive identity data is appropriately safeguarded. 





























