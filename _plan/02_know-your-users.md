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

You should understand who _your users are_ before you can select the Identity Provider (IdP). Your users will generally fall into these three broad categories:

| **Government Users** | - Your agency's employees. <br/>- Another agency's employees.<br/> - State & Local, Tribal or Territorial Govenment Users<br/> - **Example**: A Department of Homeland Security (DHS) user who is on detail to USCIS. She may want to access your agency's immigration system. She will possess a government issued PIV card verifying her identity.|
| **Commercial Users** | - Commercial organization such as banks and brokerage businesses.<br/>- They will need to be identified by their business license or similar artifacts.<br/> - **Example**: Brokerage firm buying treasury bills and notes from the U.S. Treasury Department will provide business license as identity.|
| **Consumers** | - Consumer of your service may be a citizen. <br/>- The user base will be very broad.<br/>- May or may not possess identity issued by Federal government.<br/> - **Example**: A citizen applying for Social Security benefits will require a social security number to access the benefits. |

## User Analysis

When you are conducting a user population analysis, your agency should consider the following:

> <i class="fa fa-check-square-o"></i> **Risk Assessment:** Review the application’s risk assessment guidelines and analyze the specific security and technology requirements and infrastructure limitations. 

>> * What is the data and information that your users will have access to? 

>> * What are the transactions that they can perform in your application?

>> * What are the risks associated with those accesses and transactions?

>> * Consult the NIST 800-63 documents to understand what are the applicable risk assessment profiles.

> <i class="fa fa-check-square-o"></i> **Identify Credential Requirements.** Based on the application’s risk assessment, you should review the list of approved credentials that meet the security, privacy, and technology requirements. 

>> * Credentials that users already have such as a PIV card for government users, or a driver's license issued by a State or Local government. 

>> * Reduce redundant issuance of credentials while requiring the lowest level of effort on the part of the user. 

>> * Refer to guidance posted on the Federal Government’s [Identity Management](https://idmanagement.gov) website for a current list of approved credentials.

> <i class="fa fa-check-square-o"></i> **Analyze User Population.** Analyze the target user population to determine what credentials are available or can easily be obtained. When analyzing the user population, consider the following:

>> * **Number of Users**: Your agency should determine how many different types of users its application will cater to. The total population size could affect the total complexity and cost of integrating a potential credential type.

>> * **User Information**: It is often necessary to collect additional information beyond what is provided as part of the authentication transaction in order to provision user accounts. The availability of this information could vary depending on the type of credential used; however, an agency should seek to collect only the information that is minimally necessary to complete the provisioning process.

> <i class="fa fa-check-square-o"></i> **Credential Enrollment & Issuance**: Some types of credentials require an in-person enrollment and/or issuance interaction between the user and Identity Provider. An agency should consider the ability of its user population to participate in this type of interaction when determining the feasibility of implementing a particular credential type.









































