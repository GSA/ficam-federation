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

You should know who _your users are_ before you can select the Identity Provider (IdP). Your users will generally fall into these three broad categories:

- **Government Users**: If your user base is your agency's employees, this category will be applicable to you.
- **Commercial Users**: When you have users who are not your agency employees, and include contractors from other commercial organization, these users will need to be identified by the IdP who holds their credentials.
- **Citizen Consumers**: When a consumer of your service is a citizen, the user base will be very broad. You will have to analyze how you will identify these users when they want to access your agency's service.

One of the first steps that your agency should take to enable the use of trusted third-party credentials is determining what types of credentials are acceptable for access. This is a multi-step process that involves careful consideration of a number of factors associated with the application’s business, security, infrastructure requirements, and the target user population.

## <span style="color: #0C5C89">**Checklist**</span>

> <i class="fa fa-check-square-o"></i> &nbsp;**Determine LOA and Security and Privacy Requirements.** Review the application’s level of assurance and analyze the specific security and technology requirements and infrastructure limitations.

> <i class="fa fa-check-square-o"></i> &nbsp;**Identify Credential Requirements.** Based on the application’s level of assurance, review the list of approved credential schemes that meet the security, privacy, and technology requirements. The application’s level of assurance dictates minimally acceptable credential types. Agencies should refer to guidance posted on the Federal Government’s Identity Management homepage for a current list of approved credentials

> <i class="fa fa-check-square-o"></i> &nbsp;**Analyze User Population.** Analyze the target user population to determine what credentials are available or can easily be obtained. When analyzing the user population, consider the following:

>> * Credentials that users external to the Federal Government already have 

>> * Total number of external users 

>> * User information requirements 

>> * Ability of user to complete credential enrollment/issuance steps

> <i class="fa fa-check-square-o"></i> &nbsp;**Select Acceptable Credentials.** An agency should select acceptable credentials that meet level of assurance, security, and privacy requirements and are available to the target user population.

When you are conducting a user population analysis, your agency should consider the following:

- **Credentials that users external to the Federal Government already have**
>Leverage a credential type that your user already commonly possesses such as email. 
>Rreduce redundant issuance of credentials while requiring the lowest
level of effort on the part of the user. 
>An agency should take steps to determine which
trusted credentials are available for the user population, based on the application‘s
security and level of assurance requirements.

- **Total number of external users** 
> Your agency should determine how many non-federal users its application has. The total population size could affect the total complexity and cost of integrating a potential credential type.

- **User information requirements**
> It is often necessary to collect additional information beyond what is provided as part of the authentication
transaction in order to provision user accounts. The availability of this information could
vary depending on the type of credential used; however, an agency should seek to collect
only the information that is minimally necessary to complete the provisioning process.

- **Ability of user to complete credential enrollment/issuance steps**
> Some types of credentials require an in-person enrollment and/or issuance interaction between the user
and Identity Provider. An agency should consider the ability of its user population to
participate in this type of interaction when determining the feasibility of implementing a
particular credential type.








































