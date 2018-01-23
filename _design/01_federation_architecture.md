---
layout: default
title: Federation Architecture  
permalink: /design/federationarch/
collection: design
pubDate: 
---

- Audience: Engineer/Architect
- Define the criteria for selecting design pattern.
- Specify the different design patterns.

To select a solution architecture, it’s important to understand which architecture is most applicable to your agency’s situation. It’s recommended that an agency use the information collected from the assessments during the agency’s planning period to determine its optimal solution architecture.

## <span style="color: #0C5C89">**Checklist**</span>

> <i class="fa fa-check-square-o"></i> &nbsp;**Review business requirements.** To choose which federal architecture to use, you will need to review your agency’s business requirements. During the review, should consider the following:

>> * Size of user population

>> * Number of applications using third-party credentials

>> * Ability to modify existing infrastructure to accept third-party credentials

>> * Privacy requirements

> <i class="fa fa-check-square-o"></i> &nbsp;**Select federation architecture.** Based on the review of your agency’s business requirements, select the federation architecture that best meets the agency’s needs.

The table below provides guidance to the applicability of each architectural solution. Within the table, the enterprise and federation broker architecture solutions share certain situations where either one may be appropriate. These approaches both support streamlined integration of multiple applications but differ in the amount of control the agency keeps in implementing and managing the federation solution. An agency should consider each of its requirements to determine the best architectural approach.

<br>

| <center> Recommended Approach </center> | <center> Situations </center> | 
|:---------------------------------------:|-------------------------------|
| **Stand-Alone** | • An agency has a small number of applications that require the acceptance of third-party credentials. <br><br> • An agency wishes to pilot the acceptance of third-party credentials on a small scale before deploying it for the entire agency. |
| **Enterprise** | • An agency wishes to maintain control of which Credential Service Providers (CSPs) are integrated and the connection to those CSPs. <br><br> • An agency has many applications that are required to accept third-party credentials. <br><br> • An agency has existing agency-wide infrastructure that can be modified/augmented to accept third-party credentials. |
| **Federation Broker** | • An agency has many applications that are required to accept third-party credentials. <br><br> • An agency has existing agency-wide infrastructure that can be modified/augmented to accept third-party credentials. <br><br> • An agency wishes to accept third-party credentials from a large user base that spans many CSPs. <br><br> • An agency with privacy requirements to accept externally-issued credentials without knowing to which CSP a user authenticated. |

<br>

Within this section, each of these solution architectures are discussed in further detail including a high-level overview, key considerations, and the requirements associated with each model.
























