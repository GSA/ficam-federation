---
layout: default
title: Federation Assurance Levels
permalink: /assurance_levels/
---

One of the key requirements that an agency should look
to when determining which third-party credentials to accept is the application‘s level of
assurance. The work performed by the Identity Scheme Adoption Process and the requirements
contained in NIST SP 800-63 dictate which identity schemes and associated credentials are
acceptable based on the application‘s level of assurance. Additionally, the Federal PKI Common
Policy Framework (COMMON) and the Federal Bridge Certification Authority (FBCA)
Certificate Policy govern the PKI certificate types and their associated level of assurance. 

The table below provides a summary of the schemes adopted through the Identity Scheme Adoption Process
as well as the PKI certificate policies and maps them to the corresponding level of assurance for
each. This is not intended to be comprehensive; an agency should refer to
idmanagement.gov for additional information and an up-to-date list of adopted schemes.

|Identity Scheme|LOA 1|LOA 2|LOA 3|LOA 4|
|Security Assertion Markup Language (SAML) 2.0 Web Browser SSO| <i class="fa fa-check-square-o"> | <i class="fa fa-check-square-o"> | <i class="fa fa-check-square-o">| |
|ICAM OpenID 2.0 |<i class="fa fa-check-square-o">|||
|ICAM Identity Metasystem Interoperability (IMI) 1.0|<i class="fa fa-check-square-o">|<i class="fa fa-check-square-o">|<i class="fa fa-check-square-o">||
|PIV-Interoperable|<i class="fa fa-check-square-o">|<i class="fa fa-check-square-o">|<i class="fa fa-check-square-o">|<i class="fa fa-check-square-o">|
|COMMON PIV Authentication Certificate|<i class="fa fa-check-square-o">|<i class="fa fa-check-square-o">|<i class="fa fa-check-square-o">|<i class="fa fa-check-square-o">|
|COMMON Software Certificate|<i class="fa fa-check-square-o">|<i class="fa fa-check-square-o">|<i class="fa fa-check-square-o">||
|COMMON Hardware Certificate|<i class="fa fa-check-square-o">|<i class="fa fa-check-square-o">|<i class="fa fa-check-square-o">|<i class="fa fa-check-square-o">|
|COMMON High|<i class="fa fa-check-square-o">|<i class="fa fa-check-square-o">|<i class="fa fa-check-square-o">|<i class="fa fa-check-square-o">|
|Citizen and Commerce Class|<i class="fa fa-check-square-o">|<i class="fa fa-check-square-o">|||
|Basic|<i class="fa fa-check-square-o">|<i class="fa fa-check-square-o">|<i class="fa fa-check-square-o">||
|Medium|<i class="fa fa-check-square-o">|<i class="fa fa-check-square-o">|<i class="fa fa-check-square-o">||
|Medium Hardware|<i class="fa fa-check-square-o">|<i class="fa fa-check-square-o">|<i class="fa fa-check-square-o">|<i class="fa fa-check-square-o">|
|High|<i class="fa fa-check-square-o">|<i class="fa fa-check-square-o">|<i class="fa fa-check-square-o">|<i class="fa fa-check-square-o">|

This table presents different requirements for each FAL. Each successive level subsumes and fulfills all requirements of lower levels. Federations presented through a proxy SHALL be represented by the lowest level used during the proxied transaction.

| **Federation Assurance Level (FAL)** | **Requirement** |
| 1 | Bearer assertion, signed by IdP. |
| 2 | Bearer assertion, signed by IdP and encrypted to RP. |
| 3 | Holder of key assertion, signed by IdP and encrypted to RP. |

For example, FAL1 maps to the OpenID Connect Basic Client profile or Security Assertion Markup Language (SAML) Web SSO Artifact Binding profile with no additional features. FAL2 additionally requires that the assertion (e.g., the OpenID Connect ID Token or SAML Assertion) be encrypted to a public key representing the RP in question. FAL3 requires the subscriber to cryptographically prove possession of a key bound to the assertion (e.g., the use of a cryptographic authenticator) along with all requirements of FAL2. The additional key presented at FAL3 need not be the same key used by the subscriber to authenticate to the IdP.

Regardless of what the RP requests or what the protocol requires, the RP can easily detect the FAL in use by observing the nature of the assertion as it is presented as part of the federation protocol. Therefore, the RP is responsible for determining which FALs it is willing to accept for a given authentication transaction and ensuring that the transaction meets that FAL’s requirements.

In addition to identifying what credentials meet the application‘s level of assurance, an agency
should determine what credentials are appropriate for the target user population. An agency can
determine this by performing an analysis of the target user population. This analysis provides 
an agency with sufficient information about its external users
to narrow down the list of minimally acceptable credentials to those that are feasible for implementation.






































