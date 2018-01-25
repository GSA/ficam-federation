---
layout: default
title: Account Management
permalink: build/account_management/
collection: build
pubDate: 
---

- Audience: Engineer/Architect
- Define all the aspects of account management and linking.
- Relying Party Section 7.2 - Account Management.
- Can break this down into multiple playbook items
>- Account Identification
>- Account Linking Patterns
>- Resolving Account Linking Issues.

Account management is the process of creating and managing accounts for both internal and external users. These accounts may exist within an application or, preferably, in an agency-wide identity management solution. Implementing a federation solution requires account management for external users (i.e., non-federal users that use third-party credentials).

During this process, a new account is created for the user, which may take place either before or during the user’s initial visit to an application with a third-party credential. Provisioning is not a requirement for all applications; however, it’s necessary if the application needs to maintain the state of a user across multiple visits.

After provisioning, an RP performs account linking to associate one or more identities with an RP account based on the unique identifiers passed in the assertions. Identification of the user can be accomplished up front by the CSP or once the assertion is received by the RP. In the first case, an identity can be automatically linked to a user’s RP account if the required attributes are present in the assertion. If the required attributes are not present in the assertion, a manual linking process can be performed by the RP after the assertion is received. The manual linking process allows a user to link his/her identity to the appropriate RP account by confirming his/her identity to the RP. Regardless of the method used to perform account linking, the RP should only collect the minimum amount of PII necessary, consistent with the privacy-enhancing principle of data minimization.

After the user has successfully confirmed his/her identity, the RP can link the assertion to the correct RP account by storing the unique identifier contained in the assertion. This unique identifier will be used during future attempts to correlate identities with the correct RP account. Offering more than one approach allows flexibility in the account linking process.

<br>

<div style="background-color: #edf1f3;color: black;margin: 10px;padding: 10px">

<h3><span>Terminology</span></h3>
<p><strong>CSP-Performed Identity Binding </strong> - The process by which a CSP provides all required information for the RP to bind the identity within the assertion to the RP account
<p><strong>RP-Performed Identity Binding </strong> – After the RP receives the assertion from the CSP, the RP collects additional information or conducts additional identity proofing in order to successfully bind the assertion to the identity. </p></p>

</div>

<br>

## <span style="color: #0C5C89">**Checklist**</span>

> <i class="fa fa-check-square-o"></i> &nbsp;**Provisioning.** Provisioning is the process of creating an account for a user within an application or agency-wide identity management solution. This process takes place either as an out-of-band process where the creation of the user’s RP account occurs before the user visits the application, or as a just-in-time process that takes place when the user first visits the application. 

> <i class="fa fa-check-square-o"></i> &nbsp;**Account Linking.** Account Linking is the process of associating one or more identities to an RP account based on the identifiable data passed in the assertion or from other sources. In addition, some applications may allow a user to unlink his/her federated identity from his/her local identity. 

<div id="accordion" markdown="1">

### Account Linking Patterns 
<div markdown="1">

As part of provisioning and account linking, an RP will link one or multiple external credentials to an internal user account. There are several patterns that an agency could potentially use to handle such a situation, including:

> * **One account per user/credential combination.** The user has the ability to create a new RP account with each credential. This is a one-to-one linking of credentials to RP accounts and leads to several credential/RP account combinations for a single user. The credential/RP account combinations are not linked in any form.
 
> * **One account per user regardless of the number of credentials.** The user has an RP account that is linked to one or more credentials. This is a many-to-one linking of credentials to RP accounts and allows a user to have a consistent experience regardless of the credential used to access the application. The application will need to have logic in place to associate multiple credential identifiers to a single RP account. 

In addition to these two patterns, there are several other patterns that are not relevant to the acceptance of third-party credentials and therefore were not included in this playbook.

</div>

### Performing Account Linking
<div markdown="1">

Account linking is the one time process for matching incoming credentials with the correct RP account. The linking process is accomplished by storing a unique identifier from the credential with the RP account. This allows the RP to use the unique identifier presented by the credential to identify the user’s RP account. Once account linking is performed, the correlation between the CSP account and the RP account is persistent, and for each subsequent log in the RP maintains the correlation of the CSP account to the RP account. An RP can use the following types of unique identifiers to perform account linking: 

> * **Single Attribute.** This type of identifier represents a single piece of information about a user. An example of this type of identifier is an email address.
 
> * **Attribute Combinations.** This type of identifier consists of several pieces of information about a user, that when combined will uniquely identify the user. An example of this type of identifier can be first name, last name, date of birth, and the last four digits of your social security number. RPs should consider whether new privacy risks arise when attributes are combined together. 

> * **Pseudonyms.** This type of identifier is a name or alias that has been assigned to a user that is different than the user’s real name. The pseudonym can be self-generated by the user or it can be generated by the CSP. The linking of the pseudonym to the RP account will occur in the same fashion as the single attribute. 

> * **Random Unique Identifier.** This type of identifier is a single attribute that is random and has no meaning. Each individual user is assigned a random identifier by the CSP that the RP associates with the user’s RP account. The PPID is a random unique identifier that is different for each RP/user combination. It allows a user to access various government applications without being tracked across those applications. A user’s PPID will be different between RPs, however, it will be persistent for a single RP, serving as the correlation key between the CSP account and the RP account for all future authentication events.

The attributes used to link a user’s account may be available from the CSP and provided in the assertion or the RP may determine the attributes from another source.

In the case of single attribute or attribute combination, the CSP provides attributes that have meaning to the RP and can be used by the RP to identify a user. When the attribute is passed through an assertion, the RP will have the corresponding information to link the CSP account to the RP account. In the case of the random unique identifier, or PPID, if the RP has predetermined knowledge of the PPID, then it can use the PPID to link the CSP account to the RP account. Typically the RP will not know the PPID ahead of time and will have to use other means to perform the initial account linking. This is shown in the figure below.

The figure below illustrates using the single attribute method to perform the initial account linking and the PPID for future correlation between the CSP account and RP account.

<br>

<div style="text-align:center"><img src="{{site.baseurl}}/img/acct-link.png"/></div>

<br>

In this method, the first time the RP receives an assertion for a given user, the RP will match the email, as an example, in the assertion to the user’s local RP account and link the CSP account to the RP account. At this point, the RP will store the PPID that was sent in the assertion and associate it with the RP account. In future iterations where the RP receives an assertion about the same user, it can then use the PPID to lookup the RP account. In this example, the single attribute account linking method was used for the initial account linking; however, other methods such as the multiple attribute or pseudonym can be used as well.

<br>

<div style="background-color: #edf1f3;color: black;margin: 10px;padding: 10px">

<h3><span>FAQ</span></h3>
<p><strong>What are examples of attributes that uniquely identify a person?</strong></p>
<p><span>Sometimes identifying an authoritative source can lead to other efficiencies. Treasury identified HRConnect as its authoritative source of core identity data for employees and contractors. As a result, Treasury was able to establish HRConnect as the originator of the Treasury Unique Identifier (TrUID), which is used to link users in USAccess, Treasury Enterprise Director, and bureau Identity Management Systems (IDMS) through the user’s lifecycle. As a result, data quality is dramatically improved, while reducing redundant data collection.</span></p>

</div>

<br>

When choosing a unique identifier, it’s important to make sure the value will not change over time. If the value of the unique identifier does change, the users will lose access to his/her RP account, thus forcing the user to call the help desk to resolve the problem.

Linking can either be an automated or manual process. An automated process compares unique identifiers in the assertion to unique identifiers in the RP accounts; if a match is found, the credential is automatically correlated to the account. The manual process allows the user to link credentials to an RP account through login verification or by providing a shared secret known only by the user and the RP. With login verification, the user will initially log in with his/her local RP account and then with the desired CSP credential he/she wishes to link. When the assertion from this new credential is returned, the unique identifier from the credential can be linked to the user’s RP account.

Alternatively, the user can link his/her account to the RP based on a known shared secret. The user logs into the application with his/her third-party credential. The application then prompts the user to enter the shared secret (e.g., unique information provided to the user in an out-of-band manner), which the user provides. The application will perform a lookup within the RP application to determine the RP account that matches the shared secret. If that match is found, the user credential used to log in is linked to the RP account. RPs should strive to provide both automated and manual linking processes. This provides a backup mechanism for linking credentials to RP accounts when the automated process does not succeed.

</div>

### Resolving Account Linking Issues
<div markdown="1">

If initial account linking is not successful, the RP should have additional mechanisms in place to assist the user in linking his/her account. These mechanisms should allow the RP to uniquely identify the user, thus allowing the application to link the credential to the correct identity (if the correct identity exists). Methods that an RP can use to resolve account linking issues include:

> * **In-person identity verification.** This method requires the user to visit an in-person location to provide additional information about his/her identity. In-person identity verification enables an RP to gather other identity information to link the user’s identity to his/her RP account. 

> * **Trusted third party.** This method redirects a user to a third-party site (e.g., Experian) where he/she is prompted with several questions to verify his/her identity.

> * **Help desk/call center.** This method requires the user to call the help desk to resolve linking issues. The help desk can ask a series of questions to verify his/her identity.

</div>
</div>




















