---
layout: page_collection
title: Account Management
collection: implement
permalink: implement/2_acct-mgmt/
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

Account management is the process of creating and managing accounts for both internal and external users. These accounts may exist within an application or, preferably, in an agency-wide identity management solution. Implementing a federation solution requires account management for external users (i.e., non-federal users that use third-party credentials), which entails the following sequential steps:

* **Provisioning** 
<br>

Provisioning is the process of creating an account for a user within an application or agency-wide identity management solution. This process takes place either as an out-of-band process where the creation of the user’s RP account occurs before the user visits the application, or as a just-in-time process that takes place when the user first visits the application. 
<br>

* **Account Linking**
<br>

Account Linking is the process of associating one or more identities to an RP account based on the identifiable data passed in the assertion or from other sources. In addition, some applications may allow a user to unlink his/her federated identity from his/her local identity. 
<br>

* **Account Maintenance**
<br>

Account maintenance is the periodic review, modification, and/or removal of accounts in an application or agency-wide identity management solution.
<br>

During this process, a new account is created for the user, which may take place either before or during the user’s initial visit to an application with a third-party credential. Provisioning is not a requirement for all applications; however, it is necessary if the application needs to maintain the state of a user across multiple visits. 

After provisioning, an RP performs account linking to associate one or more identities with an RP account based on the unique identifiers passed in the assertions. Identification of the user can be accomplished up front by the CSP or once the assertion is received by the RP. In the first case, an identity can be automatically linked to a user’s RP account if the required attributes are present in the assertion. If the required attributes are not present in the assertion, a manual linking process can be performed by the RP after the assertion is received. The manual linking process allows a user to link his/her identity to the appropriate RP account by confirming his/her identity to the RP. Regardless of the method used to perform account linking, the RP should only collect the minimum amount of PII necessary, consistent with the privacy-enhancing principle of data minimization. 

After the user has successfully confirmed his/her identity, the RP can link the assertion to the correct RP account by storing the unique identifier contained in the assertion. This unique identifier will be used during future attempts to correlate identities with the correct RP account. Offering more than one approach allows flexibility in the account linking process.

<br>

| <center> Terminology </center> |
|--------------------------------|
| **CSP-Performed Identity Binding –** The process by which a CSP provides all required information for the RP to bind the identity within the assertion to the RP account. <br><br> **RP-Performed Identity Binding –** After the RP receives the assertion from the CSP, the RP collects additional information or conducts additional identity proofing in order to successfully bind the assertion to the identity. |

<br>

### Account Management Scenarios and Patterns

Account management will vary depending on the relationship between the user and the RP. This relationship will define the extent to which the RP will have predetermined information about the user. Five provisioning scenarios that describe these relationships include:
<br>

* Business-Entity Relationship with a Known User Base;
<br>

* Business-Entity Relationship with Indeterminate User Base;
<br>

* Relationship with an Individual, Known User;
<br>

* Relationship with an Individual, Unknown User; and
<br>

* Temporary Access Session.
<br>

In the first two scenarios, where there is an existing relationship with a business entity, it is likely that the credential being leveraged for federation was issued by the business entity. Since these scenarios fall outside of accepting FICAM-approved third-party credentials, this playbook does not provide specific guidance on them. 

The remaining three scenarios involve an individual user, in this case a non-federal user, and his/her relationship with an RP. These scenarios are discussed further in the following sections.

<br>

### *Relationship with an Individual, Known User*

This type of account management scenario requires that the user have a pre-existing relationship with the RP application and/or agency. That is, the user has interacted with the agency and the agency has a record of the user and certain attributes about the user. An example of this scenario is an agency that provides grants to a user. When the user requests a grant, he/she will provide information about himself/herself to the agency. This could result in the creation of an account at the RP application or the storage of the user’s information in a repository within the agency. In either of these cases, the agency retains the information about the user requesting a grant. Later when the user attempts to access the RP with a third-party credential, the RP can use this information to assist in account linking.

Provisioning of the RP account will occur prior to the user’s initial visit to the application with his/her third-party credential. This provisioning may occur during an out-of-band process such as the creation of the record for the user when he/she requested the grant in the example above; or by having the user manually visit the application and create an RP account using local credentials (e.g., username and password). Account linking occurs when the user visits the application with his/her third-party credential. If the assertion passed to the RP does not contain the attributes required to link the user’s identity from the CSP to the RP account, the RP will need to identity proof the user. After the RP identity proofs the user, unique attributes from the assertion are associated with the RP account. This association, or linking, will be persistent at the RP, which allows future access attempts with the given credential to succeed without requiring the identity proofing step. 

The chart below provides a summary of the known user account management activities.

<br>

| <center> Activity </center> | <center> Description </center> |
|:---------------------------:|--------------------------------|
| **Provisioning** | Occurs prior to the user’s first attempt to access the application with a third-party credential. The Relying Party (RP) account is created, but no credential, or only a local credential, is associated with the account. |
| **Account Linking** | Upon the first attmept to access the application, the user’s credential is associated with his/her RP account. Additional credentials can be associated with an RP account at any time, if the application employs the *single account multiple credentials* pattern. |
| **Account Maintenance** | The implementation of these activities is at the discretion of the RP. |

<br>

### *Relationship with an Individual, Unknown User*


This type of account management scenario does not require the RP account to be provisioned before the user’s initial visit to the application with his/her third-party credential. An example of this scenario is a user that attempts to access the application without being known by the agency. The RP application will receive an assertion from a CSP about the user. At this time, the RP will create a “shadow account”, which is an RP account that is created for the purpose of maintaining a persistent association with an external user. The unique identifier within the assertion is linked to the shadow account. 

<br>

| <center> Lesson Learned </center> |
|-----------------------------------|
| Research.gov, National Science Foundation’s (NSF) grants management system, successfully allows first-time visitors to use an OpenID credential (e.g. Google) to access NSF visitor services. By provisioning the user’s account to the application, NSF allows the user to personalize his/her experience for future visits, including a personalized homepage, up-to-date Research.gov news, and information through Rich Site Summary (RSS) feeds and email alerts. |

<br>

In this scenario, if the RP received enough information from the assertion to uniquely identify the user, the RP will create a local RP account. Since this activity happens dynamically as the assertion is received, it is referred to as just-in-time provisioning. If the RP requires additional information to uniquely identify the user, then provisioning does not occur when the assertion is received. Instead, the RP will collect this information using either automatic collection, prompted collection, deferred collection, or a hybrid collection approach. The RP should only collect the minimum amount of information that is required for the user to perform a transaction with the RP. The RP will perform a level of identity proofing to vet the information obtained about the user. This can be achieved by leveraging a trusted third party or by conducting identity proofing in person. Upon completion of the identity proofing, the RP will provision an RP account for the user. This is referred to as deferred provisioning, since the provisioning activities occur at a time later than when the initial assertion is received.

Account linking takes place immediately after provisioning, associating unique attributes contained in the assertion from the CSP to the RP account that was just created. Similar to the known user scenario described earlier, the association of the CSP account to the RP account is persistent; allowing future access attempts with the given credential to succeed without requiring the identity proofing step. The chart below provides a summary of the known user account management activities.

<br>

| <center> Activity </center> | <center> Description </center> |
|:---------------------------:|--------------------------------|
| **Provisioning** | Occurs when the user first attempts to access the application. If the assertion contains all of the required information, the Relying Party (RP) uses that information to provision the RP account. This is referred to as just-in-time provisioning. If the assertion does not contain all of the required information, the RP can gather the missing components and provision the RP account later. This is referred to as deferred provisioning. |
| **Account Linking** | Immediately after provisioning occurs during the user’s first access attempt, the user’s credential is associated with his/her RP account. Additional credentials can be associated with an RP account at any time if the application employs the *single account multiple credentials pattern.* |
| **Account Maintenance** | The implementation of these activities is at the discretion of the RP. |

<br>

### *Temporary Access Station*

This type of account management scenario does not require provisioning of a permanent RP account. Some applications can provide access to the user without provisioning an account. Other applications, however, may need to provision a temporary account for the user, which will be removed when the user terminates his/her session with the application. The key difference between the temporary access scenario and other scenarios is that the user’s information does not persist from session to session for the user. 

<br>

| <center> Activity </center> | <center> Description </center> |
|:---------------------------:|--------------------------------|
| **Provisioning** | Depending on the application implementation, a temporary account may or may not be created. If it is created, the account only exists for the duration of the user’s session. |
| **Account Linking** | N/A |
| **Account Maintenance** | The implementation of these activities is at the discretion of the RP. |

<br>

### Account Linking

This section provides a more detailed discussion around account linking, including account linking patterns, methods, and issue resolution. Account linking applies to the known and unknown user scenarios described in the previous section. In those scenarios, the RP links the user’s CSP credential to the RP account. The user should be provided adequate notice that the RP is linking his/her account and the RP should provide the user with the option to opt out of linking the credential to the RP account. 

Account linking relies on the presence of an RP account to bind the credential. A user may already have an RP account, may register for an RP account when attempting to link a credential, or an RP account may be created automatically when the user presents his/her externally-issued credential for linking. 

<br>

| <center> Implementation Tip </center> |
|---------------------------------------|
| A Relying Party (RP) should provide an option for a user to create a local credential, even when its application accepts third-party credentials. This provides the RP with a means of provisioning an account for a user that does not have the required third-party credential. The use of local credentials may require the RP to perform additional identity proofing for users that create such a credential. |

<br>

### Account Linking Patterns

As part of provisioning and account linking, an RP will link one or multiple external credentials to an internal user account. There are several patterns that an agency could potentially use to handle such a situation, including:

* **One account per user/credential combination.** The user has the ability to create a new RP account with each credential. This is a one-to-one linking of credentials to RP accounts and leads to several credential/RP account combinations for a single user. The credential/RP account combinations are not linked in any form. 
<br>

* **One account per user regardless of the number of credentials.** The user has an RP account that is linked to one or more credentials. This is a many-to-one linking of credentials to RP accounts and allows a user to have a consistent experience regardless of the credential used to access the application. The application will need to have logic in place to associate multiple credential identifiers to a single RP account.
<br>

In addition to these two patterns, there are several other patterns that are not relevant to the acceptance of third-party credentials and therefore were not included in this playbook. 

<br>

### Performing Account Linking

Account linking is the one time process for matching incoming credentials with the correct RP account. The linking process is accomplished by storing a unique identifier from the credential with the RP account. This allows the RP to use the unique identifier presented by the credential to identify the user’s RP account. Once account linking is performed, the correlation between the CSP account and the RP account is persistent, and for each subsequent log in the RP maintains the correlation of the CSP account to the RP account. An RP can leverage the following types of unique identifiers to perform account linking:
<br>

* **Single Attribute.** This type of identifier represents a single piece of information about a user. An example of this type of identifier is an email address.
<br>

* **Attribute Combinations.** This type of identifier consists of several pieces of information about a user, that when combined will uniquely identify the user. An example of this type of identifier can be first name, last name, date of birth, and the last four digits of your social security number. RPs should consider whether new privacy risks arise when attributes are combined together.
<br>

* **Pseudonyms.** This type of identifier is a name or alias that has been assigned to a user that is different than the user’s real name. The pseudonym can be self-generated by the user or it can be generated by the CSP. The linking of the pseudonym to the RP account will occur in the same fashion as the single attribute.
<br>

* **Random Unique Identifier.** This type of identifier is a single attribute that is random and has no meaning. Each individual user is assigned a random identifier by the CSP that the RP associates with the user’s RP account. The PPID is a random unique identifier that is different for each RP/user combination. It allows a user to access various government applications without being tracked across those applications. A user’s PPID will be different between RPs, however, it will be persistent for a single RP, serving as the correlation key between the CSP account and the RP account for all future authentication events. 

The attributes used to link a user’s account may be available from the CSP and provided in the assertion or the RP may determine the attributes from another source. 

In the case of single attribute or attribute combination, the CSP provides attributes that have meaning to the RP and can be used by the RP to identify a user. When the attribute is passed through an assertion, the RP will have the corresponding information to link the CSP account to the RP account. In the case of the random unique identifier, or PPID, if the RP has predetermined knowledge of the PPID, then it can use the PPID to link the CSP account to the RP account. Typically the RP will not know the PPID ahead of time and will have to use other means to perform the initial account linking. This is shown in the figure below.

<br>

<div style="text-align:center"><img src="{{site.baseurl}}/img/acct-link.png"/></div>

<br>

The figure above illustrates using the single attribute method to perform the initial account linking and the PPID for future correlation between the CSP account and RP account. In this method, the first time the RP receives an assertion for a given user, the RP will match the email, as an example, in the assertion to the user’s local RP account and link the CSP account to the RP account. At this point, the RP will store the PPID that was sent in the assertion and associate it with the RP account. In future iterations where the RP receives an assertion about the same user, it can then use the PPID to lookup the RP account. In this example, the single attribute account linking method was used for the initial account linking; however, other methods such as the multiple attribute or pseudonym can be used as well.

<br>

| <center> FAQ </center> |
|------------------------|
| **What are examples of attributes that uniquely identify a person?** <br><br> Common attributes used for identification include first name, last name, full address, date of birth (DOB), and Social Security Number (SSN). The Relying Party (RP) can also use variations of these attributes such as the last four digits of the SSN, city, and state. Combinations of these attributes can provide a high level of confidence for uniquely identifying a user. |

<br>

When choosing a unique identifier, it is imperative that the value will not change over time. If the value of the unique identifier does change, the users will lose access to his/her RP account, thus forcing the user to call the help desk to resolve the problem. 

Linking can either be an automated or manual process. An automated process compares unique identifiers in the assertion to unique identifiers in the RP accounts; if a match is found, the credential is automatically correlated to the account. The manual process allows the user to link credentials to an RP account through login verification or by providing a shared secret known only by the user and the RP. With login verification, the user will initially log in with his/her local RP account and then with the desired CSP credential he/she wishes to link. When the assertion from this new credential is returned, the unique identifier from the credential can be linked to the user’s RP account. 

Alternatively, the user can link his/her account to the RP based on a known shared secret. The user logs into the application with his/her third-party credential. The application then prompts the user to enter the shared secret (e.g., unique information provided to the user in an out-of-band manner), which the user provides. The application will perform a lookup within the RP application to determine the RP account that matches the shared secret. If that match is found, the user credential used to log in is linked to the RP account. RPs should strive to provide both automated and manual linking processes. This provides a backup mechanism for linking credentials to RP accounts when the automated process does not succeed.

### Resolving Account Linking Issues

If initial account linking is not successful, the RP should have additional mechanisms in place to assist the user in linking his/her account. These mechanisms should allow the RP to uniquely identify the user, thus allowing the application to link the credential to the correct identity (if the correct identity exists). Methods that an RP can use to resolve account linking issues include:

* **In-person identity verification.** This method requires the user to visit an in-person location to provide additional information about his/her identity. In-person identity verification enables an RP to gather other identity information to link the user’s identity to his/her RP account.
<br>

* **Trusted third party.** This method redirects a user to a third-party site (e.g., Experian) where he/she is prompted with several questions to verify his/her identity.
* **Help desk/call center.** This method requires the user to call the help desk to resolve linking issues. The help desk can ask a series of questions to verify his/her identity.

<br>

### Account Maintenance

Once the previous account management processes, such as provisioning, have been carried out successfully, account maintenance processes begin. Processes within account maintenance include:

* **Performing Account Cleanup.** The implementation of account cleanup is highly dependent upon how often users access the application. For many applications, it is normal to deactivate a user account after an extended period of inactivity. However, an application that users access on an infrequent basis will require an inactivity time that is of appropriate length. One method for handling this is to send a notification to the user in advance of deactivating his/her account to allow him/her ample time to log in and reset the inactivity timer. 
<br>

* **Unlinking Federated Identities.** In addition to linking credentials to an RP account, the user should also be provided a method to unlink his/her credentials from the RP account. Unlinking can be initiated by a user or by the RP. From the user’s perspective, allowing unlinking provides the user with the ability to opt out of using his/her third-party credential for the RP application. From an RP perspective, it gives the RP the ability to unlink the account of a user if a given CSP is no longer trusted. The RP needs to determine if the user can unlink all third-party credentials from his/her RP account or if at least one credential must remain linked to the account at all times. If all credentials can be removed from the account, the RP may want to consider providing the user with a local credential to allow him/her to retain access to the application.
<br>

* **Updating RP Account Attributes.** Upon creation of the RP account, attributes about the user are stored with the RP account. These attributes may become outdated if the user does not access the application for a period of time; therefore, a mechanism should be in place to update these attributes on a periodic basis. The attributes that are stored and updated should only be the attributes that the RP has identified in its PIA and are required to process the transaction with the user. Mechanisms to update attributes at the RP can be found in the chart below.

<br>

| <center> Mechanism </center> | <center> Description </center> |
|:----------------------------:|--------------------------------|
| **Assertion** | Can be used for attributes that are received through an assertion and allows a Relying Party (RP) to update attributes each time a user visits the application. |
| **Manually** | Allows the user to update his/her attributes using some type of self-service process. Depending on how these attributes are processed by the RP, the RP may need to conduct additional identity proofing to verify the information. |
| **Out-of-Band Communication** | Uses an out-of-band communication to retrieve attribute updates for a specific user. When using this method there must be an attribute source that accepts an out-of-band attribute request (e.g., utilizing the Backend Attribute Exchange [BAE]). This process can be initiated from either the RP or Credential Service Provider (CSP). |












