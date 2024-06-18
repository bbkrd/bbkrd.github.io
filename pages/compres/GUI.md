---
layout: left-menu
title: GUI
tagline: user documentation for CompRes using GitHub Pages
description: CompRes GUI
order: 30
---

The plug-in adds another node to the existing output nodes named CompRes. Here, the user can choose among three sub-nodes: Charts, CCA and Table, each of which contains helpful contents for working with controlled current adjustment.

The node CompRes contains:

{: .table .table-bordered}
| *Summary*            | Summary from the node Main results in the GUI of JDemetra+.       |
| *Regression model*   | Table from the node Pre-processing in the GUI of JDemetra+.       |
| *ARIMA model*        | Table from the node Pre-processing in the GUI of JDemetra+.       |
| *Seasonality tests*  | F-Test for stable seasonality and F-Test for moving seasonality.  |
| *Series*             | Figure with original series, trend, seasonally adjusted and seasonally adjusted (current).                                    |

<br/>                         
The sub-node Charts contains:

{: .table .table-bordered}
| *SA*       | Chart of the original series, trend, seasonally adjusted series and seasonally adjusted series (current).|
| *Only SA*  | Chart of the original series, trend, seasonally adjusted series and only seasonally adjusted series. |
| *S-I ratio*| Final filters: Seasonal and trend filters. Chart of S-I ratios of each period, i.e. the raw seasonal component, final seasonal component and final seasonal component (current). |
| *Seasonal* | Chart of the final seasonal component and the final seasonal component (current).|

<br/>
The sub-node CCA contains:

<table class="table table-bordered">
	<tr>
		<td><i>Table D8.B</i></td>
        	<td>Matrix of the raw seasonal components (D8) augmented with information on outliers and extreme values as well as the seasonal component and the seasonal component (current) for the last year, respectively.
		</td>
	</tr>
	<tr>
		<td><i>Seasonal Factor</i></td>
		<td>Final Seasonal Component</td>
	</tr>
	<tr>
		<td><i>Seasonal Factor (current)</i></td>
		<td>Final Seasonal Component (forecast in the past and saved in database)</td>
	</tr>
	<tr>
		<td><i>Recommendation</i></td>
		<td>Recommendation on how to proceed with the previously forecast seasonal component, numerical parameter specification, Large movement, Extreme value.
		</td>
	</tr>
	<tr>
		<td><i>S-I-Ratios</i></td>
		<td>Chart of S-I-ratio for the latest two periods including the raw seasonal component (dots), the seasonal component (blue line) and the seasonal component (current) (red line). Titles contain the period-to-period growth rates (PtP GR) of the seasonally adjusted series and the seasonally adjusted series (current).
		</td>
	</tr>
</table>

<br/>
The sub-node Table contains figures of pre-defined series and components:

<table class="table table-bordered">
	<tr>
		<td><i>Series</i></td>
        <td>Figures of
			<ul>
				<li>Original series</li>
				<li>Trend component</li>
				<li>Irregular component</li>
				<li>Seasonally adjusted series</li>
				<li>Seasonally adjusted series (current)</li>
				<li>Seasonal component</li>
				<li>Seasonal component (current)</li>
				<li>Calendar component</li>				
				<li>Calendar component (current)</li>
			</ul>
		</td>
	</tr>
	<tr>
		<td><i>Percentage<br/>Change</i></td>
        <td>Growth rate to the previous period for:
			<ul>
				<li>Original series</li>
				<li>Trend component</li>
				<li>Irregular component</li>
				<li>Seasonally adjusted series</li>
				<li>Seasonally adjusted series (current)</li>
				<li>Seasonal component</li>
				<li>Seasonal component (current)</li>
				<li>Calendar component</li>
				<li>Calendar component (current)</li>
			</ul>
		</td>
	</tr>	
</table>
