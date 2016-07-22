---
layout: page_collection
title: Federation Governance and Topologies
collection: overview
permalink: overview/3_governance/
---
<script>
$(function() {
  $( "#accordion" ).accordion({
    heightStyle: "content",
    collapsible: "true",
    active: "false"
  });
});
</script>
---------------------------------------------

The components of the Federal Trust Framework provide the foundation for establishing trust with parties that are external to the Federal Government and help ensure that trusted third-party credentials meet minimal acceptance and interoperability criteria. However, agencies engaging in federation outside of the Federal Government should evaluate the need for added governance to solidify the foundational level of trust, provided by the Federal Trust Framework, and establish accountability and liability with the third parties involved. 

In the context of federation, governance between Identity Providers and relying parties provides an extra layer of detail, needed to clearly define the roles and responsibilities and technical regulations, formally establish trust, ensure data quality, and establish guidelines for accountability. There are several governance mechanisms available to agencies that help achieve this, the most common being federation agreements. Federation agreements are enacted to help ensure that a relying party application receives the information necessary to make reliable access control decisions and that information is appropriately secured during transactions and at rest. 

While federation agreements will vary based on agency requirements, laws, and policies, the Identity, Credential and Access Management Subcommittee (ICAMSC) has developed a Federation Agreement Checklist to serve as a starting point for agencies to use when developing federation agreements for information/attribute sharing. This section provides considerations that an agency should take into account when developing federation governance, including: 
<br>

* **Member Responsibilities.** Federation governance should detail the procedural process participants must follow in order to become and remain members in the federation. Some examples of what should be covered in regards to membership responsibilities include the application and approval process, how suspensions and revocations are handled, the fees and costs for being a federation member, how disputes will be resolved, and proactively taking steps to raise risks as they appear. 
<br>

* **Governance Board.** Federation governance should define the membership and roles and responsibilities of the Governance Board. This is the executive-level body with representation from primary stakeholders that guides the federation and is the final body to make decisions for the federation. This group is typically responsible for approval of any modifications and/or recommendations to guidelines, standards, or documents of the federation, as well as management and resolution of risks.
<br>

* **Federation Management.** Federation governance should define the membership and roles and responsibilities of the Federation Management. This body manages the day-to-day operations of the federation. Some responsibilities may include developing policies and guidelines, implementing approval processes, reviewing membership conformance, ensuring validity of federation documents (e.g., legal agreements/contracts), facilitating the roles, relationships and mutual obligations of all parties operating in the federation, and providing administrative support for the Governance Board.
<br>

* **Identity Providers.** Federation governance should define the membership and roles and responsibilities of the Identity Providers. Identity Providers create, maintain, and manage accurate, reliable and current identity information for end users in accordance with their published procedures. Some responsibilities may include performing end user authentication and supplying the authenticated user information to relying parties, maintaining a direct relationship with end users, and communicating and implementing relevant federation rules into their agreements with end users. 
<br>

* **Relying Parties.** Federation governance should define the membership and roles and responsibilities of the relying parties. Relying parties supply electronic information services to users registered with an Identity Provider. 
<br>

* **Server Requirements.** Federation governance should describe the technical requirements related to how the servers are configured, on-boarded, audited, and checked for quality.
<br>

* **Security and Privacy.** Federation governance should describe the technical requirements for how security will be maintained within the federation. Some examples include the protections for personally identifiable data collected and maintained by the federation, personnel security processes for federation administrative staff, physical security for sites hosting federation services, and processes and tools used to detect failures and intrusion attempts and to mediate and recover from intrusions.
<br>

* **Integration and Testing.** Federation governance should describe the requirements for integrating and testing the technology that impacts the federation, such as identity management provisioning systems, authentication servers, user log-on client software, commercial products, schemes or protocols, applications that consume credentials, and auditing, alerting and logging infrastructure.

<br>

### Federation Topologies

To accommodate the wide range of mission and business reasons behind federation, there are a number of different information exchange approaches that an agency might choose. These approaches, referred to as topologies, differ based on the type of relationship that exists with the external parties involved and the level of trust required for the transaction and are driven by the organization’s business model. 
Three common federation trust topologies are: Point-to-Point, Hub-and-Spoke, and Networked.

* **Point-to-point:** Refers to a model in which an organization establishes a bilateral trust agreement with another organization directly and uses federation protocols to exchange data. 
<br>

| <center> Example </center> |
|----------------------------|
| An example of the Point-to-Point topology within the Federal Government is the Defense Support of Civil Authorities pilot program between DHS and DoD, which involved the exchange of data between the two agencies for the purpose of enabling DoD personnel to access DHS resources. Because the Defense Support of Civil Authorities pilot program involved only two organizations, the point-to-point model was deemed the most appropriate. |

<br>

* **Hub-and-spoke:** Refers to a model in which a single entity acts as a central point of communication and exchange for a number of relying parties. In this model, the relying parties do not communicate with each other; all communication and information exchange occurs through the central hub.
<br>

| <center> Example </center> |
|----------------------------|
| An example of the Hub-and-Spoke topology is OMB‘s Max.gov knowledge sharing and collaboration portal. Max.gov acts as a central broker that each agency connects to in order to communicate and share data with other agencies. The hub-and-spoke model was selected due to the number of parties involved and the desire to consolidate data in a single location that could enforce strict access restrictions. |

<br>

* **Networked:** Refers to a peer-to-peer model in which all entities are interconnected and can communicate and exchange data with all others. Entities in this model may be leveraging one or more approved Identity Providers. 
<br>

| <center> Example </center> |
|----------------------------|
| An example of the Networked topology is InCommon Federation, which provides a common framework for trustworthy shared management of access to online resources in support of education and research. InCommon uses the networked model because it provides a common trust and technology fabric that enables relying parties to quickly establish peer-to-peer connections as the need arises. |

<br>

When establishing a new federation, it is likely that an agency will be able to select a trust model to meet the specific needs of the involved parties. This decision is often affected by existing infrastructure availability, business requirements, privacy considerations, and granular attribute release needs. An agency’s existing ICAM investments, such as modernized logical access control systems, may also provide additional capabilities that could impact the federation topology that best meets the agency’s needs. These additional factors may drive an agency to adopt a hybrid approach that combines elements of multiple topologies, resulting in a model that closely represents the agency’s needs.

Regardless of the federation trust topology selected, there are a number of resources that have been established within the Federal Government to provide agencies with a foundational level of trust. When entering into an established federation; however, it is likely that the existing federation members have already chosen a trust topology. Therefore it is important than an agency examine the factors previously discussed to select a federation that most closely meets its needs.










