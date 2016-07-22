---
layout: page_collection
title: Federation Models
collection: overview
permalink: overview/1_fed-models/
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
---------------------------------------

Federation requires at least three parties: the Relying Party (RP) that has an application which it wishes to allow access to, the Credential Service Provider (CSP) that has issued credentials to the target users of the application, and the user who needs access to the RP application. 

A fourth party, the attribute provider, may be involved in a federation where additional information about a user is required. The attribute provider acts as an independent entity that maintains a set of attributes about the user. For a particular transaction, the attribute provider and the CSP can be the same entity.

Federation typically involves externalizing authentication of the credential to the CSP and leveraging assertions to communicate between the CSP and RP. However, in the case of Public Key Infrastructure (PKI) credentials, the RP will commonly perform the authentication action and validate the PKI credential itself due to the path discovery and validation process for PKI. This is referred to as direct-PKI authentication. Both situations are expressed in more detail below.

<br>

### Federated Authentication by a Credential Service Provider

In federated authentication, the RP will route the user to an external CSP to validate his/her credentials. Once the CSP authenticates the user, the CSP will send a confirmation or an assertion to the RP indicating that the user has successfully been authenticated. The figure below illustrates the process associated with a basic federated authentication transaction between the RP and CSP.

<br>

<div style="text-align:center"><img src="{{site.baseurl}}/img/rp-csp.png"/></div>

<br>

As illustrated in the figure above, the RP to CSP federated authentication process includes the following steps:

1.	The user initiates the flow of events by navigating directly to the RP application site. 
2.	The RP application presents a list of acceptable CSPs, and the user selects to log into the RP application with a CSP credential he/she possesses. The RP application then redirects the user to the selected CSP. 
3.	The CSP prompts the user to enter his/her credential.
4.	The user enters his/her credential and is successfully authenticated with the CSP. 
5.	The CSP then redirects the user back to the RP application and sends an assertion to the application verifying the user’s identity. 
6.	The RP application validates and parses the assertion to verify and grant access to the user.

In step 5 of the federated authentication process, the CSP sends an assertion to the RP. In the assertion, the CSP can also provide attributes about the user who authenticated. In this way, the CSP also acts as an attribute provider. In some federation scenarios, there may be an independent attribute provider who can provide additional attributes to the CSP or the RP. In step 6 of the federated authentication process, as part of granting access to the user, the RP is responsible for determining the specific privileges assigned to the user and enforcing the access control policies for the application (i.e., authorization). 
In addition to the approach shown in the figure above, a user can also navigate directly to the CSP to initiate the federated authentication process. In this method, the CSP authenticates the user and then redirects him/her to the RP application to complete the process.

<br>

### Direct Authentication with a PKI Credential

Direct authentication involves a user that presents a credential directly to an RP for validation. In terms of externally-issued credentials, this authentication model is used for PKI credentials issued by a certificate authority (CA) that is cross-certified with the Federal Bridge Certification Authority (FBCA). A user may possess an externally-issued PKI credential issued by a federal agency (e.g., PIV card) or by an external CSP (e.g., PIV-I card). This process is shown in the figure below.

<br>

<div style="text-align:center"><img src="{{site.baseurl}}/img/direct-auth.png"/></div>

<br>

As illustrated in the figure above, direct authentication to an RP includes the following steps:

1.	The user initiates the flow of events by navigating directly to the RP application site and presenting their PKI credential for authentication. 
2.	The RP validates the certificate path from the PKI credential to the root CA.
3.	The RP validates that the certificate is not expired or revoked by leveraging either an Online Certificate Status Protocol (OCSP) responder or a Certificate Revocation List (CRL).
4.	The RP application grants access to the user.

As part of granting access to the user in step 4, the RP is responsible for determining the specific privileges assigned to the user and enforcing the access control policies for the application (i.e., authorization). 

A PKI credential that is issued by a CA that is cross-certified by the FBCA is a valid externally-issued credential, and should be accepted by an RP. However, this playbook focuses on the brokered authentication model where the authentication event is externalized to a CSP. For more information on PKI validation and the FBCA, please reference the [Federal PKI webpage](https://www.idmanagement.gov/IDM/s/article_content_old?tag=a0Gt0000000SfwP).

















