# Overview of Federation
---------------------

Identity federation, commonly referred to as federation, is a term used to describe the technology, standards, policies, and processes that allow an organization to trust digital identities, identity attributes, and credentials created and issued by another organization. Federation allows an agency to provide modernized logical access control services for users, by trusting and accepting credentials that those users already have. This can allow non-federal users to access an agency’s resources while minimizing and potentially eliminating the need to redundantly collect and manage identity information and credentials.

Within the Federal Government, the business need to federate with a non-federal partner is driven primarily by each agency‘s mission. The largest consumers of federated identity data will likely be agencies with missions that involve significant collaboration with non-federal organizations (e.g., state and local governments) or provide a large number of citizen-focused services. Each agency should evaluate its citizen-focused and cross-organizational collaboration and information sharing needs to determine the need for implementing federation capabilities. 

The vast majority of federation transactions that occur within the Federal Government can be grouped into two categories, interagency federation and federation with entities external to the Federal Government. This playbook will primarily focus on the latter category.  

Federation is made possible through the establishment and use of common exchange protocols and agreed-upon open standards/specifications that allow an agency to authenticate a user from another organization or trust an authentication conducted outside of the agency. The use of these common rules enables an agency to place a level of trust in the federated identity and credential to which that identity is bound. Given the nature of federated transactions and the electronic exchange of identity data across organizational boundaries, there is an increased focus on security and privacy to ensure users’ sensitive identity data is appropriately safeguarded. 

In a federated environment, these transactions occur between trusted Identity Providers that have been approved through the Federal Trust Framework and relying parties. Identity Providers are service providers that create, maintain, and manage identity information and credentials for users, in accordance with one of the four levels of assurance. Relying parties are entities that receive and consume identity and credential data from Identity Providers and make access control decisions based on that data, in accordance with the Federal Trust Framework and established federation governance. 
 
The FICAM architecture seeks to leverage trust mechanisms that exist under the Federal Trust Framework to enable agencies to reduce or eliminate the need to issue credentials to users that are external to the Federal Government and thus eliminate unnecessary data collection wherever possible. Agencies should leverage these mechanisms and move toward trusting and accepting third-party credentials that have been created and issued in accordance with the Federal Trust Framework. In doing so, an agency that has a mission or business need to federate with non-federal organizations and entities can achieve a number of benefits, including:

* Cost savings
* Enhanced privacy protections
* Increased confidence in user identity
* Streamlined revocation of access
* Increased security


