---
layout: default
title: Plan a Federation Project
permalink: /plan/
collection: plan
pubDate: 
---

- Audience: Program Managers (single coordination points for managing operations)
- Define the project management steps for planning a Federation project 
- Intro to the Plan section - review, modify and apply plain language principles including less words / more actionable items; focus on steps for a program manager to plan for a single sign on or federated sign on model for a federal enterprise or a federal mission application
- Relying Party Doc Section 5.1 (Page 21) has some materials for this planning.
- (2/5/2018) Possible Single Sign-on Referenced Document: _Federal Identity, Credential, and Access Management Trust Framework Solutions Functional Requirements for FICAM SAML 2.0 Web Browser SSO Profile v1.0.2_ (Version 1.0.0) (date: 3/11/2014?) (doc undated)

(ORIG text) A successful federation implementation is one that takes an agency’s mission and business needs into consideration and supports an agency’s processes for interfacing with its customers. 
When there are many externally facing applications, the cost savings are amplified, thereby increasing the benefits of accepting of third-party credentials. 
(ORIG text) The agency, also known as the Relying Party (RP), can use this information to strengthen its business case and gain leadership approval. **Isn't RP = an application?  How can it be an agency?**
(ORIG text) To build the business case, the RP will need to document the costs and benefits of accepting third-party credentials. **How can an application do this, if RP is an application?** 

(ORIG text) This can be accomplished by taking the following steps:

For writing reference only:  (NIST SP 800-63-C) _Federation is a process that allows for the conveyance of authentication and subscriber attribute information across networked systems. In a federation scenario, the verifier or CSP is referred to as an identity provider, or IdP. The RP is the party that receives and uses the information provided by the IdP._ [more...]

**Breaks down into ideas like this -- from Federation pages in FICAM-Arch Playbook and other sources:**

## What are Single Sign-on (SSO) and Federated Sign-on?
To plan for an SSO or FSO model for a federal enterprise or a federal mission application...[add text or move this]
* Explain SSO
* Explain FSO
* Discuss planning below

## Benefits of Federation (i.e., SSO or FSO)
* Enables your agency to establish and manage trusted identities for all system users.
* Enables your agency to monitor user behavior and system security though diagnostics, analytics, and reporting.
* Only authorized users can access protected resources, so Federation strengthens the Federal Government’s information and physical security.
* Increases information-sharing and safeguarding
* Increases interoperability through information-sharing agreements and establishing a common ICAM data architecture across government.
* Secure delivery of mission services to customers, including access to information and resources.
* Increased productivity through employee use of SSO or Federated Sign-on.
* More collaboration and cooperation among agencies, and so new solutions (e.g., what if we were all collaborated like we were "GOV.gov"?)
* Cost savings from reduced infrastructure, e.g., reduced credential authentication and authorization services, redundant applications.
* Cost savings from centralized technical support teams.
-- your users could log into cross-agency websites and applications using their home agency credential.

* Foster trust by building protections for privacy and civil liberties into business processes and technical solutions
Goal 4: Support Federal Government efficiency in information technology.
4.1 - Streamline ICAM governance and program management within each agency or department
4.2 - Standardize and automate ICAM business processes across the Federal Government
4.3 - Establish shared service platforms and reuse or repurpose existing hardware and infrastructure when possible

## What Do I Need To Consider?
* Agency mission, business needs, and customer-interface processes. 
* What are the requirements for the Federation project?
* What federal policies and mandates apply to Federation projects? -- policies, OMB memoranda, FISMA requirements, NIST standards, initatives to ensure compliance
* Cost-benefit analysis for accepting third-party credentials [ORIG: business cases]
* Develop a business case(s)
* How to obtain funding and from where
* Identify stakeholders (program, agency, and government-wide)  [Does this apply: ICAM Segment government-wide and agency-level stakeholders in Roadmap, pgs. 168-175]
* How to set up agreements with other agencies
* How to evaluate and contract with Service Providers
* How to manage, mitigate, and report risks and issues -- internal agency, across-agency, cross-government?
* What federal reporting is required?
* Develop communications and outreach vehicles - foster communications and cooperation, consistent messaging, timely and accurate reporting [Roadmap, pg. 178)

Additional planning:
* Establish cross-agency, cross-government working group(s)?
* Define workstreams for project and administrative [Roadmap, pg. 177]


Future planning:
* Which applications available from other agencies would your users benefit from if they had easy access to them?
* Which applications could your agency eliminate if users had access to the same/similar applications at another agency?

## How Do We Plan for Federation?
You can begin achieving the benefits of Federation by taking the following steps:

## <span style="color: #0C5C89">**Checklist**</span>

<i class="fa fa-check-square-o"></i> &nbsp;**Estimate upfront cost to design, build, implement, and maintain the solution architecture?** 
* Count your agency's applications that need to accept third-party credentials --> feeds into Solution Architecture
* Determine what existing infrastructure can be reused **What does this mean? What might existing infrastructure consist of?**
* What new infrastructure needs to be put in place--design, build, implement?
* What will be the cost of design, build, implement, operations, and maintenance (phases)? **Goes where?**

<i class="fa fa-check-square-o"></i> &nbsp;**Estimate application integration costs.**
* Calculate the cost based on the **integration?** effort per application.
* Assess how complex is the application
* Assess how easily can the application authentication method can be modified **Existing system or new system?**
* Assess how easy it is to link third-party credentials to RP accounts. **Is this Account Linking?**

<i class="fa fa-check-square-o"></i> &nbsp;**Estimate ongoing, life-cycle costs.**
* Plan 
* Design
* Build/Integrate
* Operate/Manage/Overhead
* Governance
* Maintain
* Service charges (Example:  If a shared service provider is used, such as a federation broker, then the RP should also account for ongoing service charges.) 

<i class="fa fa-check-square-o"></i> &nbsp;**Estimate/calculate cost benefit.** After the costs are known, calculate the costs and return on investment (ROI) can be calculated based on reducing the need for identity-proofing and managing credentials. Weigh the benefits? 

<i class="fa fa-check-square-o"></i> &nbsp;**Create a phased approach.** <!--There is always a phased approach. What is the phased approach? Everyone already knows this is needed. Do we really need to say this?-->A phased and prioritized approach should be used to split activities into achievable milestones, incremental build and test, etc. Demonstrate incremental benefits. 
* Phase A:  <!--Communicating is good but this text provides no value-->Communicate changes to stakeholders and users, since accepting externally issued credentials for access to government resources signals a paradigm shift for agencies and users that have traditionally relied on federally-issued credentials.
* Phase B: xxxx
* Phase C: xxx
* Phase D: xxx

<i class="fa fa-check-square-o"></i> &nbsp;**Develop required program-management documents:**
* Program Management Plan
* Program Schedule and Milestones
* Risk Management Plan

<i class="fa fa-check-square-o"></i> &nbsp;**Determine what reporting is required**
* FISMA
* Privacy




