---
layout: default
title: Federation Implementation
permalink: /build/
collection: build
pubDate: 
---

- Audience: Program Managers
- FICAM Roadmap section 12.4.4. Federated Access Implementation Considerations.

Enabling an agency‘s externally facing applications to trust external identity information and
third-party credentials is an undertaking that requires planning, support, and coordination from
various groups within an agency and with the agency‘s external partners. Specific planning and
coordination considerations include the following:

<i class="fa fa-check-square-o"></i> **Define access control requirements**. An agency should define specific access control
requirements related to granting access to users external to the Federal Government by
determining what levels of access are needed and employing robust access control
models to provide a more granular level of control over user access privileges.
Verifying the user‘s access need occurs in addition to the identity proofing process
performed by the Identity Provider.

<i class="fa fa-check-square-o"></i> **Determine an identity lifecycle management process for non-federal users**. In order
to establish a user account for a non-federal user, an identity record will need to be
created for them as part of the provisioning process. An agency has existing digital identity life cycle management processes in
place for its internal users; however, this process may need to be expanded or modified to
include a non-federal user population. Records for non-federal users may contain a
different set of identity attributes, but they must be managed in a way that is consistent
with existing agency requirements and processes.

<i class="fa fa-check-square-o"></i> **Protect privacy of personal data**. When granting users external to the Federal
Government access to an agency‘s resources in a federated environment, an agency
should involve representatives from their Privacy Office to ensure that all applicable
privacy policies and regulations are enforced. These policies and regulations help ensure
the privacy of personal information exchanged between a relying party application and
Identity Provider as well as data contained within the relying party application. See
Section 12.2.2.1 for a discussion on applying the TFPAP privacy principles in a federated
environment.

<i class="fa fa-check-square-o"></i> **Work with application owners to understand additional needs**. In addition to
leveraging the existing government-wide frameworks and standards provided through the
TFPAP and Identity Scheme Adoption Process, an agency should work with its
application and system owners to determine if additional profiles and schemes are
required to support specific mission or business needs and communicate those needs
through the appropriate review and approval channels.

<i class="fa fa-check-square-o"></i> **Focus on the user experience**. One of the core drivers behind accepting external users‘
third-party credentials for access to agency applications is improving the user experience.
An agency should keep this driver in mind when planning such a program and focus on
elements that will make the access process easier or better for non-federal users, such as
selecting credentials that users already have or can easily be obtained, provided security
requirements are met.

<i class="fa fa-check-square-o"></i> **Communicate changes to stakeholders and users**. Accepting externally issued
credentials for access to government resources signals a paradigm shift for agencies and
users that have traditionally relied on federally-issued credentials. The process and
technology changes required to support this transition must be communicated to a relying
party application‘s stakeholders as well as the target user population.

<i class="fa fa-check-square-o"></i> **Determine requirements for availability and incident response**. In the event that an
Identity Provider becomes unavailable due to a service outage or intrusion, the agency
application may require back-up support. Each application should determine these needs
independently as low availability applications can often sustain extended periods of down
time while high-availability applications have little or no tolerance for service outages.

<i class="fa fa-check-square-o"></i> **Incorporate into the IT change management process.** Accepting trusted nonfederally
issued credentials may require changes to an agency‘s IT application. When
planning to enable an application to federate with external parties an agency should
evaluate any necessary procedural or technical changes through their established change
management processes.














