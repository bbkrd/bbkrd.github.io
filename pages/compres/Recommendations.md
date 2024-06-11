---
layout: left-menu
title: Recommendations
tagline: user documentation for CompRes using GitHub Pages
description: CompRes Recommendations
order: 40
---

The Recommendation functionality by the compRes plugin helps with the decision of whether to keep or not to keep using the previously forecasted seasonal component. 
This feature is useful when working with the controlled current seasonal adjustment regime. It compares two seasonal adjustment results. First, the results obtained when using a seasonal component that has been forecasted in the past. Second, the results obtained when using the seasonal component that has been estimated right now by JD+ given the latest available data.
<br/> 
#### Outcome

Three different output results are possible: 

{: .table .table-bordered}
| *Recommendation* |*Meaning*|
| *Check* |Check the specification of the SA-Item.|
| *Update* |Switch to the new components.|
| *Keep* |Continue with the current seasonal and calendar components.|
<br/>
The recommendations are color-coded similar to a traffic light: Green for Keep, yellow for Update and red for Check.
If no such recommendation can be given the output result Unknown is display in red.

<br/> 
#### Specifications

For each SA-Item specifications can be changed in the properties sheet ($\text{Windows} \rhd \text{Properties}$). To display the recommendation specification select the SA-Item(s), right mouse click and select $\text{CompRes Recommendations} \rhd \text{Add MetaData}$. To reset an SA-Item’s specification to the default setting select $\text{CompRes Recommendations} \rhd \text{Reset MetaData}$. If not specified, a default value will be applied.              

{: .table .table-bordered}
| *Name* |*Description* | *Default*|
| *compres.nd8* |Number of last periods for which the SI-ratios are used for the comparison.| 3 |
| *compres.tolgrowth* |Acceptable absolute deviation between new and old growth rates.| 1.0 |
| *compres.ngrowth* |Number of last periods whose growth rates are used for the large movement detection.| 10 |
| *compres.trim* |Defines the quantiles for the growth rates to be used in the large movement detection.| 0.05 |

<br/> 
#### Special Cases

If you select one or both the checkboxes under $\text{Tools} \rhd \text{Options} \rhd \text{Demetra} \rhd \text{CompRes} \rhd \text{Data Source} \rhd \text{Recommendations: Special Cases}$ it might affect the recommendation.  
In case of constant seasonal factors (current), the recommendation can be overwritten so that it will always be Keep.
In case the calendar factor (current) is missing, it can be assumed that seasonal adjustment happens without a calendar component. Otherwise the recommendation Unknown will be given.
