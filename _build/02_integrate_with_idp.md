#---
layout: default
title: Integrate with Identity Provider
permalink: build/integrate_with_idp/
collection: build
pubDate: 
#---

- Audience: Engineer/Architect
- Discuss the integration process with CSP.


Integration with a Identity Provider (IdP) is critical to enabling an external user to access an agency with a third-party credential provided by the IdP. This integration enables a IdP to send an assertion to the Relying Party (RP), which describes a user and his/her attributes. To accomplish this, the agency should identify an acceptable CSP, determine what attributes are available from that CSP, establish a secure connection to the CSP, and modify its user interface to provide the ability for a user to authenticate with the CSP.

An RP can integrate with multiple CSPs, which enables a broader set of users to access the RP application and could increase user traffic. If the RP decides to integrate with multiple CSPs, the enterprise or federation broker architectures may be beneficial. These solution architectures enable the reuse of configurations and federal profiles for integrating with CSPs, thereby reducing the cost of integration with new CSPs.

> <i class="fa fa-check-square-o"></i> &nbsp;**Establish Trust between Federation Partners.** Trust between an RP and CSP is a mechanism to enable trusted communication between both parties. It consists of mutual authentication and the exchange of shared information (e.g., Uniform Resource Locator [URL] endpoints, allowed bindings, certificates). Mutual Authentication is the process of validating that the other party is who it claims to be and is approved to participate in the transaction in order to lessen the probability of an attack like “man in the middle” or “spoofing.”

> <i class="fa fa-check-square-o"></i> &nbsp;**Update User Interface.** In order to enable the acceptance of third-party credentials, an agency will need to modify the RP application login or CSP discovery page to present the user with links to acceptable CSPs. The updates to the user interface can occur at the application, federation server, or federation broker depending on the federation architecture selected. When clicked, these links should redirect the user to the desired CSP with the correct parameters to assure he/she will be redirected back to the RP after authentication has taken place.

> The parameters that must be sent to the CSP vary depending on the protocol that is used. When updating the user interface, the RP should ensure that it continues to meet user accessibility requirements.

> In accordance with the TFPAP, the CSP’s user interface must be modified to capture user consent for collection of attributes about the user. Obtaining the user’s consent can be accomplished by posting an adequate notice, which includes: 

>> * A general description of the authentication event; 

>> * The intended use of the attributes; 

>> * The authority under which the attributes are collected; and 

>> * A description of any disclosure or transmission of PII. 

> The adequate notice should be clearly displayed to the user and it should be made clear that the user is leaving the government site to authenticate at an external CSP. An adequate notice should not be a link on a page that leads to a complex privacy policy or general terms and conditions. Once user consent has been obtained, the RP can collect the requested attributes about the user. The RP should work with the CSP to identify what attributes the RP needs, per its Systems of Record Notice (SORN), and how it intends to use and manage the attributes. This will inform the consent notice presented to the user.

> An agency should focus on elements that will make the access process easier and better for non-federal users, such as selecting credentials that users already have or can easily be obtained, provided security requirements are met. The design and implementation of a user interface should be targeted at achieving a high level of user satisfaction, which will provide a high adoption rate.













