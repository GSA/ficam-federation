---
layout: default
title: Plan A Federation Project
permalink: /plan/
collection: plan
pubDate: 
---

- Audience: Program Managers
- Define the project management steps for planning a Federation project 
- Intro to the Plan section - review, modify and apply plain language principles including less words / more actionable items; focus on steps for a program manager to plan for a single sign on or federated sign on model for a federal enterprise or a federal mission application
- Relying Party Doc Section 5.1 (Page 21) has some materials for this planning.
- (2/5/2018) Possible Single Sign-on Referenced Document: _Federal Identity, Credential, and Access Management Trust Framework Solutions Functional Requirements for FICAM SAML 2.0 Web Browser SSO Profile v1.0.2_ (Version 1.0.0) (date: 3/11/2014?) (doc undated)

ORIG. INTRO PARAGRAPH:

A successful federation implementation is one that takes an agency’s mission and business needs into consideration and supports an agency’s processes for interfacing with its customers. 
When there are many externally facing applications, the cost savings are amplified, thereby increasing the benefits of accepting of third-party credentials. 
(ORIG) The agency, **Isn't an RP = an application? Is it really an agency for this document?** also known as the Relying Party (RP), can use this information to strengthen its business case and gain leadership approval. 
(ORIG) To build the business case, the RP **Isn't an RP = an application? Or is it really an agency for this document?** will need to document the costs and benefits of accepting third-party credentials. This can be accomplished by taking the following steps:

Breaks down into ideas like this (some thoughts)

**What are the benefits of Federation (i.e., Single Sign-on [SSO] or Federated Sign-on) for my agency? [Is this all covered in "What Is Federation?"]**
* ORIG: Cost savings [are amplified when an agency has many externally facing applications, which increases the benefits of accepting of third-party credentials.] 
* Cost savings from reduced infrastructure, reduced need for personnel(?), elimination of redundant applications at different agencies.
* Increased productivity -- your users could log into cross-agency websites and applications using their home agency credential.
* Increased productivity from easy access to other agency's applications that are needed by your agency but not supported.
* More collaboration and cooperation among agencies (e.g., what if we were all collaborated like we were "GOV.gov"?) = more contributors = more solutions.
* Lower cost of resetting user passwords (reduced tech support).

**How do I need to consider in planning for Federation?**
* ORIG:  Federation must consider an agency’s mission, business needs, and customer-interface processes.<!--Customer? interface? Examples would be helpful--> 
* ORIG: To build an agency's business case for Federation**?**, the RP (**application??**) will need to document the costs and benefits of accepting third-party credentials. **Explain third-party credentials**
* Which applications available from other agencies would your users benefit from if they had easy access to them?
* Which applications could your agency eliminate if users had access to the same/similar applications at another agency?


This can be accomplished by taking the following steps:

## <span style="color: #0C5C89">**Checklist**</span>

<i class="fa fa-check-square-o"></i> &nbsp;**Estimate upfront cost to design, build, implement, and maintain the solution architecture?** 
* Count our applications that need to accept third-party credentials --> feeds into Solution Architecture
* Determine what existing infrastructure can be reused **What does exsiting infrastructure consist of?**
* What new infrastructure needs to be put in place--design, build, implement?
* What will be the cost of operations and maintenance? **Goes where?**

<i class="fa fa-check-square-o"></i> &nbsp;**Estimate application integration costs.** **How much will this cost to plan, design, build/integrate, operate, and maintain?** 
* Calculate the cost based on the **integration?** effort per application.
* Assess how complex is the application
* Assess how easily can the application authentication method can be modified **Existing system or new system?**
* Assess how easy it is to link third-party credentials to RP accounts. **Is this Account Linking?**

<i class="fa fa-check-square-o"></i> &nbsp;**Estimate ongoing costs.** **How much will other life-cycle cost phases cost?**
* Plan 
* Design
* Build/Integrate
* Operate/Manage
* Governance?
* Maintain
* Service charges (Example:  If a shared service provider is used, such as a federation broker, then the RP should also account for ongoing service charges.) 

<i class="fa fa-check-square-o"></i> &nbsp;**Estimate/calculate cost benefit.** After the costs are known, calculate the costs and return on investment (ROI) can be calculated based on reducing the need for identity-proofing and managing credentials. Weigh the benefits? 

<i class="fa fa-check-square-o"></i> &nbsp;**Create a phased approach.** <!--There is always a phased approach. What is the phased approach? Everyone already knows this is needed. Do we really need to say this?-->A phased and prioritized approach should be used to split activities into achievable milestones, incremental build and test, etc. Demonstrate incremental benefits. 
* Phase A:  <!--Communicating is good but this text provides no value-->Communicate changes to stakeholders and users, since accepting externally issued credentials for access to government resources signals a paradigm shift for agencies and users that have traditionally relied on federally-issued credentials.
* Phase B: xxxx
* Phase C: xxx
* Phase D: xxx


