---
layout: left-menu
title: Commands
tagline: user documentation for KIX2.0 using GitHub Pages
description: KIX2.0 Commands
order: 120
category: KIX2.0
---

Any single command or stack of commands is specified in the command line panel and executed by pressing either the Ctrl+Enter keys together or the "green arrow" button in the upper left corner of that panel.
Please note that the plug-in is not developed to check the sensibility of your computations. To yield sensible results the chain-linked indices to be aggregated or disaggregated have to have the same reference period. In this sense, the reference period is defined as the period for which the series is based to an annual average of 100. Furthermore, the program does not re-reference the results. The resulting chain-linked index is normalised to a weighted average of the annual averages of the components for the year which the user specifies as the reference year.

Each command described in this section is essentially a sequence of mandatory and optional arguments. To distinguish the two types of arguments, the latter are displayed in brackets. Comments can be added as entire lines by using the **#** symbol as the first character in the respective lines. However, please note that comments cannot be added after commands.

#### Chaining: the CHA.ANN command

The $\text{CHA.ANN}$ command is used to chain an unchained time series according to annual overlap. To this end, the values of the unchained time series in year $t$ are multiplied by the cumulated annual averages of the unchained time series up to year $t-1$ and divided by 100. For $t = 1$, the multiplication is carried out using the annual average of the first year. The specification of the command is given by

$$\text{[Name=]CHA.ANN,series[,refyr]}$$

with the following arguments:

{: .table .table-bordered}
$\text{Name}$ | Name of the chained series to be displayed in the **Results** panel. If not specified, it is set to *Formula* $n$, where $n$ is the line of the command in the command line panel of the **MyKIX** document. 
$\text{series}$ | Unchained time series to be chained. This can be any series from the **Index Data** or **Weight Data** panel.
$\text{refyr}$ | Reference year for the chained time series. If not specified, the chained time series is not normalised.

<br/>
<div class="bg-faded" id="ExampleCHAANN">
<b>Example 1: (<i>CHA.ANN</i> command)</b> Suppose we have loaded four index series and four weighting series to the <b>Index Data</b> and <b>Weight Data</b> panels, respectively, the observation span of either data type includes the year 2010 and the command line panel reads:
<br/><br/>
<div style="margin-left:3em"> 
   $\text{CHA.ANN,}i1  \\
		\text{CHA.ANN,}w4 \\
		\text{CHA.ANN,}i1,2010 \\
		\text{MyCLi1=CHA.ANN,}i1,2010$
</div><br/>
Executing these commands, the <b>Results</b> panel will display four series:
	<ol>
		<li>a chained version of index series $i1$ with the name Formula $1$,</li>
		<li>a chained version of weighting series $w4$ with the name Formula $2$,</li>
		<li>a normalised version of Formula $1$ with the name Formula $3$ and an annual average of $100$ for the year 2010 and </li>
		<li>a renamed version of Formula $3$ with the name MyCLi1.</li>
	</ol>
</div>

#### Unchaining: the UNC.ANN command

The $\text{UNC.ANN}$ command is used to unchain a chained time series according to annual overlap. To this end, the values of the chained time series in year $t$ are divided by the annual average of the chained time series in year $t-1$ and multiplied by 100. For $t = 1$, the division is carried out using the annual average of the first year. Consequently, the annual average of the resulting unchained time series equals 100 in the first year. The specification of the command is given by

$$\text{[Name=]UNC.ANN,series}$$

with the following arguments:

{: .table .table-bordered}
$\text{Name}$ | Name of the unchained series to be displayed in the **Results** panel. If not specified, it is set to *Formula* $n$, where $n$ is the line of the command in the command line panel of the **MyKIX** document. 
$\text{series}$ | Chained time series to be unchained. This can be any series from the **Index Data** or **Weight Data** panel.

<br/>
<div class="bg-faded" id="ExampleUNCANN">
<b>Example 2: (<i>UNC.ANN</i> command)</b>
Suppose we have loaded four index series and four weighting series to the <b>Index Data</b> and <b>Weight Data</b> panels, respectively, and the command line panel reads:
<br/>
<br/>
	<div style="margin-left:3em">
		$\text{UNC.ANN,}i1\\
		\text{UNC.ANN,}w4\\
		\text{MyUCi1=UNC.ANN,}i1$
	</div>
<br/>
Executing this stack of commands, the <b>Results</b> panel will display three series: 
	<ol>
		<li>an unchained version of index series $i1$ with the name Formula $1$,</li>
		<li>an unchained version of weighting series $w4$ with the name Formula $2$ and </li>
		<li>a renamed version of Formula $1$ with the name MyUCi1.</li>
	</ol>
</div>

#### Chain-linking: the CLI.ANN command

The $\text{CLI.ANN}$ command is used to aggregate and/or disaggregate two or more chain-linked (volume) indices according to annual overlap. To this end, the following steps are carried out under the assumption that all chain-linked indices involved in the calculation have the same base and reference years:

* Each chain-linked index is unchained as described for the $\text{UNC.ANN}$ command.
* A weighted sum/difference of the unchained time series is calculated, where the weight of each unchained series in year $t$ is given by the share of the annual average of the respective weighting series in year $t-1$. If a weighting series does not cover the year $t = 0$, then its annual average in this year is approximated by the annual average in year $t = 1$. However, the user can decide whether (default) or not the values of the chain-linked aggregate are displayed for year $t = 1$, see section [Options](.\globaloptions) for further details.
* The resulting series is chained and normalised to the weighted average of the annual averages of the underlying chain-linked indices in the reference year. Thus, chaining at the end of chain-linking differs from chaining according to the $\text{CHA.ANN}$ command in terms of normalisation.

The specification of the command is given by

$$\text{[Name=]CLI.ANN,index1,[weight1,]}+\text{/}-\text{,index2,[weight2,]...,refyr}$$

with the following arguments:

{: .table .table-bordered}
$\text{Name}$ | Name of the chain-linked aggregate to be displayed in the **Results** panel. If not specified, it is set to *Formula* $n$, where $n$ is the line of the command in the command line panel of the **MyKIX** document. 
$\text{index1}$ | First chain-linked index from the **Index Data** panel to be used in the aggregation/disaggregation. 
$\text{weight1}$ | Weighting series from the **Weight Data** panel which corresponds to the first chain-linked index ($\text{index1}$). If not specified, the weighting series with the same running number as the first chain-linked index is taken automatically. 
$+\text{/}-$ | Operator used to indicate aggregation (+) or disaggregation (-). All operations are executed "from left to right". 
$\text{index2}$ | Second chain-linked index from the **Index Data** panel to be used in the aggregation/disaggregation. 
$\text{weight2}$ | Weighting series from the **Weight Data** panel which corresponds to the second chain-linked index ($\text{index2}$). If not specified, the weighting series with the same running number as the second chain-linked index is taken automatically. 
$\text{...}$ | Additional chain-linked indices, corresponding weighting series and operators to be included in the aggregation/disaggregation. 
$\text{refyr}$ | Reference year of the chain-linked index. Note that no re-referencing is carried out, that is the annual average of the chain-linked index may differ from $100$ in the reference year.

<br/>
<div class="bg-faded" id="ExampleCLIANN">
<b>Example 3: (<i>CLI.ANN</i> command)</b>
Suppose we have loaded five chain-linked indices and five weighting series to the <b>Index Data</b> and <b>Weight Data</b> panels, respectively, and the command line panel reads:
<br/><br/>
	<div style="margin-left:3em">
		$\text{CLI.ANN,}i1,+,i3,2010\\
		\text{CLI.ANN,}i1,w2,+,i3,w4,2010\\
		\text{CLI.ANN,}i2,w5,-,i3,w4,2010\\
		\text{MyCLIi1=CLI.ANN,}i1,w2,+,i3,w4,2010$
	</div>
<br/>
Executing these commands, the <b>Results</b> panel will display four chain-linked indices with reference year 2010:
<ol>
	<li>a chain-linked aggregate of the index series $i1$ and $i3$ with the name Formula $1$. Note that this command is equivalent to
	<div style="margin-left:3em">
		$\text{CLI.ANN,}i1,w1,+,i3,w3,2010$
	</div></li>
	<li>the same chain-linked indices are used for aggregation but the weighting series $w2$ and $w4$ from the <b>Weight Data</b> panel in use, respectively, and the name of the chain-linked aggregate is Formula $2$</li>
	<li>a disaggregated chain-linked index with the name Formula $3$ derived by subtracting the chain-linked index $i3$ from the chain-linked aggregate $i2$, using the respective weighting series $w4$ for index series $i3$ and $w5$ for the aggregate $i2$</li>
	<li>a renamed version of Formula $2$ with the name MyCLi1.</li>
</ol>
</div>

#### Contribution to growth: the CTG.ANN command

The $\text{CTG.ANN}$ command is used to compute the growth contribution of a chain-linked component to a chain-linked aggregate with the partial contribution to growth method when chain-linking is done according to annual overlap. That means, the growth contribution is calculated as the difference between the aggregate growth and the growth obtained assuming that the component has not changed. To this end, the following steps are carried out:

1. The chain-linked component and the chain-linked aggregate are unchained as described for the $\text{UNC.ANN}$ command. Then, two auxiliary series are calculated:
* The residual series is given by the weighted difference/sum of the unchained aggregate and the unchained component, where the weight of each unchained series in year $t$ is given by the share of the annual average of the respective weighting series in year $t-1$. Essentially, this series is the unchained aggregate net of the component of interest.
* The weighting series of the residuals is given by the difference/sum of the weights used in the previous step.
2. The two auxiliary series are used to calculate a chained-linked aggregate assuming that the component has not changed:
* The chain-linked aggregate is normalised to 100 in its start year.
* The chain-linked component is lagged according to the time span for which the growth contribution is to be carried out and unchained using the previous-year annual averages of the chain-linked index.
* A weighted sum/difference of the residual series and the lagged component is calculated, where the weight of each series in year $t$ is given by the share of the annual average of the corresponding weighting series of the residuals and the weighting series of the component in year $t-1$.
* The resulting aggregate is chained using the previous-year annual averages of the unchained aggregate.
3. The partial contribution to growth is calculated as the difference between the growth rates of the normalised chain-linked aggregate and the chained-linked aggregate assuming that the component has not changed as derived in the previous step.

The specification of the command is given by

$$\text{[Name=]CTG.ANN,iContr,[wContr,]}+/-\text{,iTotal,[wTotal,]lags}$$

with the following arguments:

{: .table .table-bordered}
$\text{Name}$ | Name of the growth contribution to be displayed in the **Results** panel. If not specified, it is set to *Formula* $n$, where $n$ is the line of the command in the command line panel of the **MyKIX** document. 
$\text{iContr}$ | Chain-linked index from the **Index Data** panel, the growth contribution of which is to be computed. 
$\text{wContr}$ | Weighting series from the **Weight Data** panel which corresponds to the chain-linked index ($\text{iContr}$). If not specified, the weighting series with the same running number as the chain-linked index is taken automatically. 
$+/-$ | Operator used to indicate the direction of the growth contribution. 
$\text{iTotal}$ | Chain-linked aggregate from the **Index Data** panel. 
$\text{wTotal}$ | Weighting series from the **Weight Data** panel which corresponds to the chain-linked aggregate ($\text{iTotal}$). If not specified, the weighting series with the same running number as the chain-linked aggregate is taken automatically. 
$\text{lags}$ | Horizon of the partial contribution to growth, which must be in the interval $[1, \tau]$ and $\tau$ denotes the number of observations per year, that is $\tau = 12$ for monthly data and $\tau = 4$ for quarterly data.

<br/>
<div class="bg-faded" id="ExampleCLIANN">
<b>Example 4: (<i>CTG.ANN command</i>)</b>
Suppose we have loaded five quarterly chain-linked indices and five quarterly weighting series to the <b>Index Data</b> and <b>Weight Data</b> panels, respectively, and the command line panel reads:
	<div style="margin-left:3em">
		$\text{CTG.ANN},i1,+,i3,1\\
		\text{CTG.ANN},i1,w2,+,i3,w4,1\\
		\text{CTG.ANN},i2,w5,-,i3,w4,4\\
		\text{MyCTGi2=CTG.ANN},i2,w5,-,i3,w4,4$
	</div>
Executing these commands, the <b>Results</b> panel will display four growth contributions:
	<ol>
		<li>
			the contribution of the chain-linked component $i1$ to the growth rate of the chain-linked aggregate $i3$, compared to the previous quarter and named Formula $1$, where $w1$ and $w3$ are used as respective weighting series from the <b>Weight Data</b> panel. Note that this command is equivalent to
				<div style="margin-left:3em">
					$\text{CTG.ANN},i1,w1,+,i3,w3,1,$
				</div>
		</li>
		<li>
			the same growth contribution as in (1) but with the weighting series $w2$ and $w4$ used instead and labelled Formula $2$,
		</li>
		<li>
			the contribution of the chain-linked component $i2$ to the growth rate of the chain-linked aggregate $i3$, compared to the same quarter of the previous year, computed using the weighting series $w5$ and $w4$ from the <b>Weight Data</b> panel and labelled Formula $3$ in the <b>Results</b> panel. Note that the impact of the series $i2$ on the aggregate $i3$ is defined to be negative. Thus, a positive growth rate of the series $i2$ results in a decrease of the growth rate of the aggregate $i3$, and vice versa, and
		</li>
		<li>
			a renamed version of the previous growth contribution with the name MyCTGi2.
		</li>
	</ol>
</div>