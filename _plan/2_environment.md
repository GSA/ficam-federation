---
layout: page_collection
title: Understand the RP Environment
collection: plan
permalink: plan/2_environment/
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
-----------------------------------------------

Understanding the RP environment prior to enabling federation is another aspect for federation planning. It is necessary for the RP to determine if there will be any impacts to assurance level or existing privacy considerations through externalizing identity proofing and credential lifecycle management. Key steps for evaluating the RP environment include:
<br>

* **Gather existing documentation.** As part of designing and deploying an RP application, a variety of assessments related to security, authentication, and privacy should be conducted, including the ICAM maturity model if one has been completed, Federal Information Processing Standard (FIPS) 199 security categorization, eAuthentication risk assessment, Privacy Impact Assessment (PIA), and System of Records Notice (SORN).
<br>

* **Review and analyze documentation.** Existing documentation should be reviewed to understand the current state of the RP application. After reviewing the assessments, the RP should conduct a gap analysis between the current and target state. This will provide the RP with the detailed requirements and design that it will need to implement a federation capability.
<br>

* **Update documentation (if necessary).** The RP will need to determine if the documents it gathered require updates. While the FIPS 199 assessment may be reused, an eAuthentication risk assessment, PIA, and SORN should be updated to reflect the target state, which includes accepting externally-issued credentials, as necessary. To carry out these tasks, the RP should familiarize itself with applicable stakeholders within the agency. 
<br>

* **Conduct application assessment.** Once the agency has determined the risks and privacy impacts that affect its application, the next step is to conduct a deep dive review of the application in preparation for implementation. This review consists of understanding the application security model in order to paint a comprehensive picture of the application's current state and future state to assist in performing a gap analysis. The information gained from this assessment will be used by the application development team within the agency to create a detailed design, describing how changes will be implemented to the application in order to accept third-party credentials.

<br>

| <center> FAQ </center> |
|------------------------|
| **Can the results of my FIPS 199 assessment and eAuthentication risk assessment be different?** <br><br>Yes, the eAuthentication assurance levels are not directly related to the system security categories defined by FIPS 199. The FIPS 199 assessment determines the security categorization of the application based on the impact of a breach of confidentiality, integrity, and availability to the application. The eAuthentication risk assessment is focused on the risk associated with the authentication event. |

<br>

The figure below provides additional details related to the different assessments that should be gathered and reviewed by the RP and highlights specific actions that should be taken by the RP when pursuing a federation solution. 
<br>

| <center> Assessment </center> | <center> Description </center> | <center> RP Actions </center> |
|----------------------------------------|
| **FIPS 109** | FIPS 199 defines potential impacts on organizations or individuals if a breach of security occurs. The results of a breach are categorized as low, moderate, or high. | • Identify existing FIPS 199 assessment and security category. <br><br> • Determine if accepting third-party credentials is classified as a major change to the application’s security posture and if so determine if a new FIPS 199 is required. <br><br> •	Determine if the system’s security controls specified by NIST SP 800-53 need to be changed. |
| **eAuthentication Risk Assessment** | An eAuthentication risk assessment focuses on the risk associated with false/positive authentication. The results of the assessment determine the recommended strength of the authentication requirements expressed as Levels of Assurance (LOA) 1 to 4. | • Conduct (or re-assess) eAuthentication risk assessment for each application that is being modified to accept third-party credentials and determine assurance level for that application. <br><br> • Enforce the use of a credential that matches or exceeds that level of assurance for the given application. <br><br> • Select a Credential Service Provider (CSP) that meets or exceeds the level of assurance of the application. <br><br> •	Identify if any residual risk remains and determine whether to accept the risk or select and implement compensating controls. |
| **Privacy Impact Assessment (PIA)** | A PIA is an analysis of how information is handled to: <br><br> • Ensure that it complies with legal, regulatory, and policy requirements regarding privacy (e.g., Privacy Act of 1974); <br><br> • Determine the risks and effects of collecting, maintaining, and disseminating such information; and <br><br> • Examine and evaluate protections and alternative processes for handling information to mitigate privacy risk. | • Identify the attributes that the Relying Party (RP) needs about a user. The RP can use these attributes to link the user’s CSP identity to his/her RP account. <br><br> • Identify which attributes are necessary to complete the transaction. If the attributes are not necessary, reduce the set of attributes in order to be in compliance with the minimalism principle. <br><br> • Identify which of the attributes are Personally Identifiable Information (PII). This is especially important when handling information about public citizens. <br><br> • Determine requirements to protect the PII. |
| **System of Records Notice (SORN)** | A SORN is used to ensure that agencies are not creating an unnecessary burden on individuals; nor collecting or using information for purposes that are not consistent with the intent of the application. | •	Determine the legal authority for collecting the information. <br><br> • Identify how collected information is shared outside the agency. |










