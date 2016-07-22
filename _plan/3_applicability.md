---
layout: page_collection
title: Determine Applicability to Security and Privacy Controls
collection: plan
permalink: plan/3_applicability/
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
-------------------------------------------------------------

To mitigate residual risk, an RP implementing compensating controls as part of a layered security program should select and implement controls in accordance to the Risk Management Framework (RMF). Compensating controls are an additional set of controls selected out of the broader control families described in [NIST SP 800-53](http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-53r4.pdf). Once all compensating controls have been implemented, an agency should evaluate the controls to determine if there is any remaining residual risk and repeat the risk management steps as needed. The controls that are specific to federation are further discussed below.

After taking steps to mitigate residual risk, the RP should determine if it needs to modify the security and privacy controls associated with its application. For an existing application, it is expected that the security controls were selected and implemented as part of the security requirements under Federal Information Security Management Act (FISMA) and the RMF. Implementation of a federation solution, however, is likely to affect the existing controls because of the changes associated with managing and granting access to users. For example, any security controls related to the RP’s management and direct validation of user credentials would need to be updated to reflect the shift of responsibility for the activities associated with authentication to an external CSP. 

The assessments described in [Understand the RP Environment](../2_environment) provide an input into the controls that an agency needs to implement. These controls are based on SP 800-53, which defines a set of control families that are specific to security and privacy. While it is important for the RP to review and implement all of the control families, the scope of this document is the control families that are impacted by third-party credentials. These include:

* **Identification and Authentication (IA).** These controls are in place to ensure that users and devices are properly authenticated prior to allowing access to an Information Technology (IT) resource.
<br>

* **Access Control (AC)**. These controls ensure that proper restrictions are in place to limit access to authorized users with a need to know.
<br>

If the RP needs to implement compensating controls for a layered security program, it will need to implement controls in addition to these two control families. The RP will need to determine what other control families in SP 800-53 are applicable depending on the risks posed to the application and the security posture of the agency.

Based on the assessments completed, the RP will need to assess the impact of the changes made to the application’s security controls. The RP should compare these impacts to its existing controls to determine if it needs to add new controls or modify existing controls. The RP should review each control and perform an assessment to determine how to appropriately meet the control. A tool to help the agency conduct this impact analysis is called the Security Impact Analysis (SIA). This tool provides an orderly process for analyzing the proposed changes to the information system and analyzing the potential effects on the overall security posture of the information system.

While the above addresses specific privacy concerns, an agency should involve representatives from their Privacy Office to ensure that all applicable privacy policies and regulations are enforced. These policies and regulations help ensure the privacy of personal information exchanged between a relying party application and Identity Provider as well as data contained within the relying party application. Additionally, the agency application may require back-up support in the event of an outage or security incident. Each application should determine availability and incident response requirements independently as low availability applications can often sustain extended periods of down time while high-availability applications have little or no tolerance for service outages.









