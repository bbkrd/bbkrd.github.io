---
layout: left-menu
title: Short report
tagline: user documentation for CompRes using GitHub Pages
description: CompRes HTML output
order: 15
category: Report
---

The HTML report is a short summary for the comparison of current and partial concurrent adjusted series that is split into two parts which broadly result in two DIN-A-4 pages if printed out (The HTML report contains SVG graphics. It may be possible that your PDF creator does not support this format). The first part of the report summarises the specifications and the regARIMA results, the second part contains results concerning the X-11 results and the quality of the final seasonal adjustment.

The HTML documents contain the following information.

<table class="table table-bordered">
	<tr>
		<td><i>Header left</i></td>
        <td>On the left hand side of the header you find 
			<ul>
				<li>Name of SA-item </li>
				<li>Database key of the Time series (optional)</li>
				<li>Time series name</li>
				<li>Span of the series</li>
			</ul> 
		</td>
	</tr>
	<tr>
		<td><i>Header right</i></td>
        <td>On the right hand side of the header you find
			<ul>
				<li>Time stamp </li>
				<li>User identificator (optional)</li>
			</ul>
		</td>
	</tr>	
</table>

<br/>
On the left hand side of the first page you find:

{: .table .table-bordered}
| *Specification*        | Summary of user settings<br/>(Transform, Outlier detection, Outliers critical value,Regression variable, Trading days user-defined variable, ARIMA model, Forecast horizon, Sigmalimit, Seasonal filters, Trendfilter, Calendarsigma and Excludefcst)|
| *Summary* | Summary from the node Main results in the GUI of JDemetra+.|
| *Regression model* | Table from the node Pre-processing in the GUI of JDemetra+.|
| *ARIMA model* | Table from the node Pre-processing in the GUI of JDemetra+.|

<br/>
On the right hand side of the first page you find figures for:

{: .table .table-bordered}
| *Series* | Figure with original series, seasonally adjusted and seasonally adjusted (current)|
| *Autocorrelations*| Correlation diagram for the residuals.|
| *Autoregressive spectrum* | Autoregressive spectrum of the original.|
| *Periodogram* | Periodogram of the seasonally adjusted series.|

<br/>
The second page contains

{: .table .table-bordered}
| *Table D.8b* | Matrix of the raw seasonal factors (D8) augmented with information on outliers and extreme values as well as the seasonal component and the seasonal component (current) for the last year, respectively.|
| *Seasonally Adjusted*   | The period-to-period growth rates (PtP GR) of the seasonally adjusted series and the seasonally adjusted series (current).|
| *S-I-Ratio* | Chart of S-I-ratio for the latest two periods including the raw seasonal component (dots), the seasonal component (blue line and the seasonal component (current) (red line).|
| *Final filters* | Final seasonal and trend filters used.|
| *MSR* | Moving seasonality ratio of the irregular to the seasonal component on a period specific basis.|
| *I/C Ratio*| Ratio of irregular to trend component.|
| *Seasonality tests* | F-Test for stable seasonality and F-Test for moving seasonality.  |


