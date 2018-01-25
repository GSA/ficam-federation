---
layout: default
navtitle: Account Maintenance
title: Account Maintenance 
permalink: maintain/account_maintenance/
---
- Audience: Engineer/Architect
- Define all the aspects of account management and linking.
- Relying Party Section 7.2 - Account Management.

Account maintenance will vary depending on the relationship between the user and the RP. This relationship will define the extent to which the RP will have predetermined information about the user. Five provisioning scenarios that describe these relationships include: 

> <i class="fa fa-check-square-o"></i> &nbsp;**Account Maintenance.** Account maintenance is the periodic review, modification, and/or removal of accounts in an application or agency-wide identity management solution. Processes within account maintenance include:

> * **Performing Account Cleanup.** The implementation of account cleanup is highly dependent upon how often users access the application. For many applications, it’s normal to deactivate a user account after an extended period of inactivity. However, an application that users access on an infrequent basis will require an inactivity time that is of appropriate length. One method for handling this is to send a notification to the user in advance of deactivating his/her account to allow him/her ample time to log in and reset the inactivity timer. 

> * **Unlinking Federated Identities.** In addition to linking credentials to an RP account, the user should also be provided a method to unlink his/her credentials from the RP account. Unlinking can be initiated by a user or by the RP. From the user’s perspective, allowing unlinking provides the user with the ability to opt out of using his/her third-party credential for the RP application. From an RP perspective, it gives the RP the ability to unlink the account of a user if a given CSP is no longer trusted. The RP needs to determine if the user can unlink all third-party credentials from his/her RP account or if at least one credential must remain linked to the account at all times. If all credentials can be removed from the account, the RP may want to consider providing the user with a local credential to allow him/her to retain access to the application. 

> * **Updating RP Account Attributes.** Upon creation of the RP account, attributes about the user are stored with the RP account. These attributes may become outdated if the user does not access the application for a period of time; therefore, a mechanism should be in place to update these attributes on a periodic basis. The attributes that are stored and updated should only be the attributes that the RP has identified in its PIA and are required to process the transaction with the user. Mechanisms to update attributes at the RP can be found in the chart below.

<br>

| <center> Mechanism </center> | <center> Description </center> | 
|:----------------------------:|--------------------------------|
| **Assertion** | Can be used for attributes that are received through an assertion and allows a Relying Party (RP) to update attributes each time a user visits the application. |
| **Manually** | Allows the user to update his/her attributes using some type of self-service process. Depending on how these attributes are processed by the RP, the RP may need to conduct additional identity proofing to verify the information. | 
| **Out-of-Band Communication** | Uses an out-of-band communication to retrieve attribute updates for a specific user. When using this method there must be an attribute source that accepts an out-of-band attribute request (e.g., utilizing the Backend Attribute Exchange [BAE]). This process can be initiated from either the RP or Credential Service Provider (CSP). |



















