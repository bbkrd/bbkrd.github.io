---
layout: left-menu
title: GUI
tagline: user documentation for CompRes using GitHub Pages
description: CompRes GUI
order: 30
---

The plug-in adds another node to the existing output nodes named CompRes. Here, the user can choose among three sub-nodes: Charts, CCA and Table, each of which contains helpful contents for working with controlled current adjustment.

The node CompRes contains:

|||
|---|---|
| *Summary*            | Summary from the node Main results in the GUI of JDemetra+.       |
| *Regression model*   | Table from the node Pre-processing in the GUI of JDemetra+.       |
| *ARIMA model*        | Table from the node Pre-processing in the GUI of JDemetra+.       |
| *Seasonality tests*  | F-Test for stable seasonality and F-Test for moving seasonality.  |
| *Series*             | Figure with original series, trend, seasonally adjusted and seasonally adjusted (current).                                    |

<br/>                         
The sub-node Charts contains:

|||
|---|---|
| *SA*       | Chart of the original series, trend, seasonally adjusted series and seasonally adjusted series (current).|
| *Only SA*  | Chart of the original series, trend, seasonally adjusted series and only seasonally adjusted series. |
| *S-I ratio*| Chart of S-I ratios of each period, ie the raw seasonal component, final seasonal component and final seasonal component (current). |
| *Seasonal* | Chart of the final seasonal component and the final seasonal component (current).|

<br/>
The sub-node CCA contains:

<table class="table table-bordered">
	<tr>
		<td><i>Specifications</i></td>
        <td>Summary on users' input:
			<ul>
				<li>Sigmalimit</li>
				<li>Seasonalfilters</li>
				<li>Outliers critical value</li>
				<li>Calendarsigma</li>
			</ul>
		</td>
	</tr>
	<tr>
		<td><i>Final filters</i></td>
		<td>Seasonal and trend filters.</td>
	</tr>
	<tr>
		<td><i>MSR</i></td>
		<td>Moving seasonality ratio of the irregular to the seasonal component on a period specific basis.</td>
	</tr>
	<tr>
		<td><i>I/C Ratio</i></td>
		<td>Ratio of irregular to trend component.</td>
	</tr>
	<tr>
		<td><i>Seasonality tests</i></td>
		<td>F-Test for stable seasonality and F-Test for moving seasonality.</td>
	</tr>
	<tr>
		<td><i>Heteroskedasticity</i></td>
		<td>Cochran-test on equal variances within each period.</td>
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
				<li>Seasonal component</li>
				<li>Calendar component</li>
				<li>Seasonally adjusted series (current)</li>
				<li>Seasonal component (current)</li>
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
				<li>Seasonal component</li>
				<li>Calendar component</li>
				<li>Seasonally adjusted series (current)</li>
				<li>Seasonal component (current)</li>
				<li>Calendar component (current)</li>
			</ul>
		</td>
	</tr>	
</table>
