---
layout: default
navtitle: What is Federation
title: What is Federation?
permalink: /
---

- Audience: Program Managers
- Describe in a very high level what federation of identities means in a Federal space.
- Inform user what information is in this playbook.
- Provide guidance on why federation is needed.
- Who needs Federation?

-- FICAM Roadmap Section 12.1 - Federation Overview Page 365 --

Identity federation, commonly referred to as federation, is a term used to describe the technology, standards, policies, and processes that allow an organization to trust digital identities, identity attributes, and credentials created and issued by another organization. Federation allows an agency to provide modernized logical access control services for users, by trusting and accepting credentials that those users already have. This can allow non-federal users to access an agency’s resources while minimizing and potentially eliminating the need to redundantly collect and manage identity information and credentials.

This playbook is intended for ICAM Program Managers and other business owners who may be looking to understand the topic of Federation better and various planning and design items they should consider before beginning solution design and implementation. This playbook also contains guidance for implementers and engineers who are looking for guidance around the technical implementation of federation at their agencies.

The information presented in this playbook is intended to assist agencies in providing answers to
several common questions, including:

1. Why should my agency trust identity data and credentials that we did not create and
issue?
2. What benefits can my agency expect to see from trusting and accepting another
organization‘s credentials?
3. How can my agency connect with our external business partners and are there common
approaches that can be used?

This playbook was created using updated and migrated content that previously was found in the FICAM Roadmap and Implementation Guidance v2.0. We hope that the new format encourages you and your agency to contribute to additional content to support the access control management across the Federal government.

The FICAM Architecture provides a high-level overview of identity management and a description of the services that deliver access management capabilities. We recommend that you visit the <a href="https://arch.idmanagement.gov/" target="_blank"> FICAM Architecture</a> site to gain a basic understanding of access management and its role in broader federal Identity, Credential, and Access Management (ICAM).

We look forward to your use and contribution to this playbook. Please visit our <a href="/ficam-federation/contribute/" target =" _blank"> Contribute page </a> to learn how to post questions and contribute content.

# Why Federate?

-- FICAM Roadmap Section 12.1.1 - Why Federate --

The Federal Government has established a number of resources to provide a common basis for
trust and interoperability and enable agencies to streamline the manner in which access is
provided. In many cases, providing access for a non-federal user has often meant that an agency
collects identity information about that individual and issues them a credential. The ICAM target
state seeks to leverage trust mechanisms that exist under the Federal Trust Framework, discussed
in Section 12.2, to enable agencies to reduce or eliminate the need to issue credentials to users
that are external to the Federal Government and thus eliminate unnecessary data collection
wherever possible. Agencies should leverage these mechanisms and move toward trusting and
accepting third-party credentials that have been created and issued in accordance with the
Federal Trust Framework. In doing so, an agency that has a mission or business need to federate
with non-federal organizations and entities can achieve a number of benefits, including:

1. **Cost savings**. An agency can achieve significant cost savings by leveraging digital
identities that are created and managed by trusted third-parties and meet appropriate
requirements for use within the Federal Trust Framework. Federation allows an agency to
avoid incurring costs associated with identity proofing, credential issuance and
management, and management of digital identity repositories for users outside of the
organization because these services are being provided by a trusted third-party.

2. **Enhanced privacy protections**. By trusting digital identities that are created and
managed by trusted third-parties and complying with applicable privacy requirements,
rooted in the FIPPs (see Section 6.3), an agency can significantly minimize the need to
collect and manage identity information for those users, thereby reducing the likelihood
of unintentional disclosure of PII.

3. **Increased confidence in user identity**. In many cases, external Identity Providers have a
closer relationship with remote users than is possible for most agencies. This increased
proximity enables the third-party Identity Provider to issue stronger credentials by
performing required in-person identity validation. These stronger credentials allow an
agency‘s IT applications to use more robust authentication mechanisms.

4. **Streamlined revocation of access**. The close relationship that external Identity Providers
often have with their users means, in many cases, that they are aware of status changes
within the user‘s record more quickly than a relying party. As such, the external Identity
Provider has the ability to immediately revoke the user‘s credential upon the end of the
relationship. Revocation of access through this process often allows an agency to more
quickly and efficiently meet its obligation to remove an individual‘s access to an
application when it is no longer required.

5. **Increased security**. Federation reduces the number of accounts and credentials that an
agency must manage and maintain, which could become the target for a potential
attacker. When properly implemented, this can reduce instances of inappropriate access.


# Who Needs Federation?

-- FICAM Roadmap Section 12.1 - Federation Overview Page 366 --

Within the Federal Government, the business need to federate with a non-federal partner is
driven primarily by each agency‘s mission. The largest consumers of federated identity data will
likely be agencies with missions that involve significant collaboration with non-federal
organizations (e.g., state and local governments) or provide a large number of citizen-focused
services. Each agency should evaluate its citizen-focused and cross-organizational collaboration
and information sharing needs to determine the need for implementing federation capabilities.
The vast majority of federation transactions that occur within the Federal Government can be
grouped into two categories, namely:

1. **Interagency federation** - Includes federation that occurs between two or more federal
agencies based upon authentication of the PIV card. Interagency federation may include
the passing of identity assertions between agencies. This topic is discussed in greater
detail in Chapter 8.

2. **Federation with entities external** - Includes federation that
occurs between a federal agency and any other non-federal organization or entity (e.g.,
state, local, or tribal governments, commercial entities, and citizens); this type of
federation is the primary focus of this chapter.







