---
layout: default
title: Select Identity Provider
permalink: plan/identityprovider/
collection: plan
pubDate:
---

- Audience: Program Managers
- What are the steps involved in selecting the CSP.
- Relying Party doc section 7.1.1 - Selecting the CSP.

Agencies engaging in federation outside of the Federal Government should evaluate the need for added governance to solidify the foundational level of trust, provided by the Federal Trust Framework, and establish accountability and liability with the third parties involved.

In the context of federation, governance between Identity Providers and relying parties provides an extra layer of detail, needed to clearly define the roles and responsibilities and technical regulations, formally establish trust, ensure data quality, and establish guidelines for accountability. There are several governance mechanisms available to agencies that help achieve this, the most common being federation agreements. Federation agreements are enacted to help ensure that a relying party application receives the information necessary to make reliable access control decisions and that information is appropriately secured during transactions and at rest.

While federation agreements will vary based on agency requirements, laws, and policies, the Identity, Credential and Access Management Subcommittee (ICAMSC) has developed a Federation Agreement Checklist to serve as a starting point for agencies to use when developing federation agreements for information/attribute sharing. 

## <span style="color: #0C5C89">**Checklist**</span>

> <i class="fa fa-check-square-o"></i> &nbsp;**Select a Credential Service Provider.** A key component in determining a suitable CSP is understanding the user population for a given RP application. The user population and CSP characteristics will have an impact on the CSP that is best for the RP to use. These characteristics include: 

>> * **FICAM-approved CSPs.** An RP must select a FICAM-approved CSP. The use of a FICAM-approved CSP enables trust between the RP and CSP. If it’s determined that a non-approved CSP meets the requirements of the RP, then the RP can recommend the CSP work with a TFP to become FICAM-approved. The RP should not use the CSP until the CSP has been successfully approved by a TFP. 

>> * **Availability of existing credentials.** The RP should aim to select CSPs that already serve some or all of its user population. For example, if the RP’s target user population is the education community, it might seek to use a CSP under the InCommon federation, which is prevalent within the education community. This may increase user acceptance because it decreases the credentialing burden on the user. 

>> * **CSP attribute availability.** If the RP requires attributes about a user, the RP can select a CSP that has the required attributes about the user. It’s likely that a CSP may have only a partial set of attributes that an RP requires. In this case, the RP should determine if it can obtain the additional attributes it needs from another source or collect additional information from the user.
 
>>> * The RP should only collect the attributes that it needs to process the transaction; this concept is known as minimalism. 

>>> * The RP needs to gain consent from the user for any attributes it collects, including the intended use of those attributes, and the authority under which the RP is collecting the attributes. 

>> * **Level of assurance provided by the CSP.** The level of assurance at which a CSP has been approved should be equal to or greater than the level of assurance that the RP requires.


























