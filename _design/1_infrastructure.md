---
layout: page_collection
title: Evaluate Existing Infrastructure and Services
collection: design
permalink: design/1_infrastructure/
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
--------------------------------------

As each RP looks to accept third-party credentials, the requirements inherent to each application may vary, which in turn may affect the architecture that it chooses to use. An RP needs to look to its agency to determine if a complete or partial ICAM solution already exists. The ICAM team or Program Management Office (PMO) can provide the RP with guidance on the agency’s policies and methodology for ICAM. 

For example, if the agency has a complete ICAM solution and application owners are required to integrate with it, the ICAM PMO will be able to provide details to the RP on how this integration will work and what the RP needs to do. If no ICAM solution exists, the PMO may be able to provide the RP with agency policies and standards in addition to resources to assist the RP with planning and design. The RP should work with the ICAM PMO or appropriate governance body to complete the actions described in the figure below. 

<br>

| <center> Agency ICAM Solution Status </center> | <center> Description </center> | <center> Considerations </center> |
|---------------------------------------------|
| **No Existing ICAM Solution** | An agency has no centralized identity and access management system. Each application provides its own access control function, and maintains information about its users in a disconnected data store. | • Align with the agency’s requirements. <br><br> • Determine if the agency would benefit from an enterprise federation solution or if the Relying Party (RP) should implement a stand-alone solution. |
| **ICAM Solution Partially Meets Requirements** | An agency has a centralized identity and access management system; however, it does not provide federation capability that meets the requirements of the RP. | • Determine specific requirements that the RP has that are not met by the existing ICAM solution. <br><br> • Determine if the existing solution can be modified to meet the requirements of the RP at the enterprise level. If not, the ICAM Program Management Office may be able to assist the RP in implementing a stand-alone federation solution. |
| **ICAM Solution Fully Meets Requirements** | An agency has a centralized identity and access management system with which many of the applications integrate. In addition, this solution provides federation capability that meets the requirements of the RP. | • Integrate with the existing enterprise federation solution. |

<br>

After the RP has determined the current state of its agency’s ICAM solution, it is in a position to leverage this information to determine the appropriate architecture approach. 

















