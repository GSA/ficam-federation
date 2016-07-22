---
layout: page_collection
title: CSP Integration
collection: implement
permalink: implement/1_csp-integrate/
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
--------------------------------------------------------------

Integration with a Credential Service Provider (CSP) is critical to enabling an external user to access an agency with a third-party credential provided by the CSP. This integration enables a CSP to send an assertion to the Relying Party (RP), which describes a user and his/her attributes. To accomplish this, the agency should identify an acceptable CSP, determine what attributes are available from that CSP, establish a secure connection to the CSP, and modify its user interface to provide the ability for a user to authenticate with the CSP. 

<br>

### Select a Credential Service Provider

A key component in determining a suitable CSP is understanding the user population for a given RP application. The user population and CSP characteristics will have an impact on the CSP that is best for the RP to use. These characteristics include:
<br>

* **FICAM-approved CSPs.** An RP must select a FICAM-approved CSP. The use of a FICAM-approved CSP enables trust between the RP and CSP. If it is determined that a non-approved CSP meets the requirements of the RP, then the RP can recommend the CSP work with a TFP to become FICAM-approved. The RP should not use the CSP until the CSP has been successfully approved by a TFP.
<br>

* **Availability of existing credentials.** The RP should aim to select CSPs that already serve some or all of its user population. For example, if the RP’s target user population is the education community, it might seek to leverage a CSP under the InCommon federation, which is prevalent within the education community. This may increase user acceptance because it decreases the credentialing burden on the user.
<br>

* **CSP attribute availability.** If the RP requires attributes about a user, the RP can select a CSP that has the required attributes about the user. It is likely that a CSP may have only a partial set of attributes that an RP requires. In this case, the RP should determine if it can obtain the additional attributes it needs from another source or collect additional information from the user.
<br>

	* The RP should only collect the attributes that it needs to process the transaction; this concept is known as minimalism.
	<br>
	
	* The RP needs to gain consent from the user for any attributes it collects, including the intended use of those attributes, and the authority under which the RP is collecting the attributes.
	<br>

* **Level of assurance provided by the CSP.** The level of assurance at which a CSP has been approved should be equal to or greater than the level of assurance that the RP requires.

An RP can integrate with multiple CSPs, which enables a broader set of users to access the RP application and could increase user traffic. If the RP decides to integrate with multiple CSPs, the enterprise or federation broker architectures may be beneficial. These solution architectures enable the reuse of configurations and federal profiles for integrating with CSPs, thereby reducing the cost of integration with new CSPs.

<br>

### Establish Trust between Federation Partners

Trust between an RP and CSP is a mechanism to enable trusted communication between both parties. It consists of mutual authentication and the exchange of shared information (e.g., Uniform Resource Locator [URL] endpoints, allowed bindings, certificates). Mutual Authentication is the process of validating that the other party is who it claims to be and is approved to participate in the transaction in order to lessen the probability of an attack like “man in the middle” or “spoofing.” 

In the case of SAML, metadata provides the shared information used to achieve programmed trust. Metadata is structured information that describes, explains, locates, or otherwise makes it easier to retrieve, use, or manage an information resource. During the planning period, metadata is provided to the CSP and RP about the other participant. During run-time this metadata is used to validate that the CSP or RP is indeed who they claim to be and is approved to participate in the transaction. 

<br>

### Update User Interface

In order to enable the acceptance of third-party credentials, an agency will need to modify the RP application login or CSP discovery page to present the user with links to acceptable CSPs. The updates to the user interface can occur at the application, federation server, or federation broker depending on the federation architecture selected. When clicked, these links should redirect the user to the desired CSP with the correct parameters to assure he/she will be redirected back to the RP after authentication has taken place. 

The parameters that must be sent to the CSP vary depending on the protocol that is used. One common parameter is the RP’s application endpoint, which is the point to which the CSP sends the user and assertion after a successful authentication. When updating the user interface, the RP should ensure that it continues to meet user accessibility requirements. 

In accordance with the TFPAP, the CSP's user interface must be modified to capture user consent for collection of attributes about the user. Obtaining the user’s consent can be accomplished by posting an adequate notice, which includes:
<br>

* A general description of the authentication event;
<br>

* The intended use of the attributes;
<br>

* The authority under which the attributes are collected; and
<br>

* A description of any disclosure or transmission of PII. 
<br>

The adequate notice should be clearly displayed to the user and it should be made clear that the user is leaving the government site to authenticate at an external CSP. An adequate notice should not be a link on a page that leads to a complex privacy policy or general terms and conditions. Once user consent has been obtained, the RP can collect the requested attributes about the user. The RP should work with the CSP to identify what attributes the RP needs, per its Systems of Record Notice (SORN), and how it intends to use and manage the attributes. This will inform the consent notice presented to the user. 


An agency should focus on elements that will make the access process easier and better for non-federal users, such as selecting credentials that users already have or can easily be obtained, provided security requirements are met. The design and implementation of a user interface should be targeted at achieving a high level of user satisfaction, which will provide a high adoption rate.














