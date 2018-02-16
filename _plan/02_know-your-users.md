---
layout: default
title: Know Your Users
permalink: plan/knowyourusers/
collection: plan
pubDate:
---

- Audience: Program Managers
- This topic should detail the different types of users involved - Govt - Govt, Govt - Commerical, Govt - Citizen.
- What are the items to consider when user analysis is performed. Roadmap doc Section 12.4.1 - Page 392 has some items to include.
- Include materials from Ficam Architecture.

=================================

You should understand who **your users** are before you can select the **Identity Provider(s) (IdPs)**. Your users will generally fall into these broad categories:

<div><img src="{{site.baseurl}}/img/fed-users.png"/></div>

<br/>

## User Analysis

When you are conducting a user population analysis, you should consider the following:

><i class="fa fa-check-square-o"></i> **User Population.** Analyze your target user population to determine what credentials are available or can easily be obtained. You should consider the following:

>> * **User Type**: Determine how many different types of users your application will cater to based on the categories presented above. You may have to further split-up the users into smaller categories based on the credentials that they may possess. An example will be the Federal employees that have PIV credentials vs. those that do not.

>> * **User Identity**: How will you identify each category of users based on their ability to provide an identifying attribute? Some of your users may have agency issued email addresses vs. those that do not. Your public users may have a personal email address, or possess a mobile device. Others may not have any computer access and solely rely on a broker agent or assister to register themselves for government services.

>> * **Number of Users**: Determine the population size for each category of users. It could affect the total complexity and cost of integrating a potential credential type.

>> * **User Information**: You may have to collect additional information beyond what is provided as part of the authentication transaction in order to create and link user accounts. The availability of this information could vary depending on the type of credential used; however, you should seek to collect only the minimum necessary data.

> <i class="fa fa-check-square-o"></i> **Risk Assessment:** Follow some of the guidelines below to assess the risks and analyze any specific security and privacy requirements. 

>> * What is the data and information that your users will have access to? Does it include any sensitive Personally Identifiable Information (**PII**) or covered by **HIPAA** regulations on data security and privacy? 

>> * What are the transactions that they can perform in your application? Can they alter any credential data or tamper with any audit logs?

>> * Are there any risks associated with those accesses and transactions?

>> * Consult the NIST 800-63 documents to understand what the applicable risk assessment profiles are.

> <i class="fa fa-check-square-o"></i> **Identity Assurance.** Based on the application’s risk assessment, you should find out the credentials that will meet the security, privacy, and technology requirements for different types of access. 

>> * Stronger credentials that users already have such as a PIV for government users are better than just using email and password. As an example, you can introduce stronger authentication methods, such as multi-factor authentication, to enforce higher security. 

>> * Reduce redundant issuance of credentials while requiring the lowest level of effort on the part of the user. If the user already has a PIV issued by another agency, you can setup to accept that credential instead of issuing a new PIV.

>> * Consult the NIST 800-63C document to learn about the different Identity, Federation and Authentication Assurance Levels.

> <i class="fa fa-check-square-o"></i> **Credential Issuance & Enrollment**: Determine how the credentials are issued by the Identity Provider and how they can linked to your application user.

>> * A commercial entity will possess a different credential issuance policy than a public user. You will have to plan for differences in the credential types.

>> * Some types of credentials require an in-person enrollment and/or issuance interaction between the user and Identity Provider. You should consider the ability of your users to participate in this type of interaction when determining the feasibility of implementing a particular credential type.

Once you have analyzed your user population, you should be able to select one or more Identity Provider(s) that will provide you with the authentication and federation services.









































