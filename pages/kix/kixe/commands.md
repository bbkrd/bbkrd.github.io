---
layout: left-menu
title: Commands
tagline: user documentation for KIXE using GitHub Pages
description: KIXE Commands
order: 220
category: KIXE
---

Any single command or stack of commands is specified in the command line panel and executed by pressing either the **Ctrl + Enter** keys together or the "green arrow" button in the upper left corner of that panel.
Please note that the plug-in is not developed to check the sensibility of your computations. To yield sensible results the chain-linked indices to be aggregated or disaggregated have to have the same reference period. In this sense, the reference period is defined as the period for which the series is based to an annual average of 100. Furthermore, the program does not re-reference the results. The resulting chain-linked index is normalised to a weighted average of the annual averages of the components for the year which the user specifies as the reference year.

Each command described in this section is essentially a sequence of mandatory and optional arguments. To distinguish the two types of arguments, the latter are displayed in brackets. Comments can be added as entire lines by using the **#** symbol as the first character in the respective lines. However, please note that comments cannot be added after commands.

#### Chaining: the CHA.PER command

The $\text{CHA.PER}$ command is used to chain an unchained time series according to one-period overlap. To this end, the values of the unchained time series in year $t$ are multiplied by the cumulated last values of the unchained time series up to year $t-1$ and divided by 100. For $t = 1$, the multiplication is carried out using the last value of the first year. The specification of the command is given by

$$\text{[Name=]CHA.PER,series[,refyr]}$$

with the following arguments:

{: .table .table-bordered}
$\text{Name}$ | Name of the chained series to be displayed in the **Results** panel. If not specified, it is set to *Formula* $n$, where $n$ is the line of the command in the command line panel of the **MyKIX** document. 
$\text{series}$ | Unchained time series to be chained. This can be any series from the **Index Data** or **Weight Data** panel. 
$\text{refyr}$ | Reference year for the chained time series. If not specified, the chained time series is not normalised.

<br/>
<div class="bg-faded" id="ExampleCHAPER">
<b>Example 1: (<i>CHA.PER</i> command)</b> Suppose we have loaded four index series and four weighting series to the <b>Index Data</b> and <b>Weight Data</b> panels, respectively, the observation span of either data type includes the year 2010 and the command line panel reads:
<br/><br/>
	<div style="margin-left:3em"> 
		$\text{CHA.PER},i1\\
		\text{CHA.PER},w4\\
		\text{CHA.PER},i1,2010\\
		\text{MyCLi1}=\text{CHA.PER},i1,2010$
	</div><br/>
Executing these commands, the <b>Results</b> panel will display four series:
	<ol>
		<li>
			a chained version of index series $i1$ with the name Formula $1$,
		</li>
		<li>
			a chained version of weighting series $w4$ with the name Formula $2$,
		</li>
		<li>
			a normalised version of Formula $1$ with the name Formula $3$ and an annual average of $100$ for the year 2010 and
		</li>
		<li>
			a renamed version of Formula $3$ with the name MyCLi1.
		</li>
	</ol>
</div>

#### Unchaining: the UNC.PER command

The $\text{UNC.PER}$ command is used to unchain a chained time series according to one-period overlap. To this end, the values of the chained time series in year $t$ are divided by last value of the chained time series in year $t-1$ and multiplied by 100. For $t = 1$, the division is carried out using the last value of the first year. Consequently, the last value of the resulting unchained time series equals 100 in the first year. The specification of the command is given by

$$\text{[Name=]UNC.PER,series}$$

with the following arguments:

{: .table .table-bordered}
$\text{Name}$ | Name of the unchained series to be displayed in the **Results** panel. If not specified, it is set to *Formula* $n$, where $n$ is the line of the command in the command line panel of the **MyKIX** document. 
$\text{series}$ | Chained time series to be unchained. This can be any series from the **Index Data** or **Weight Data** panel.

<br/>
<div class="bg-faded" id="ExampleUNCPER">
<b>Example 2: (<i>UNC.PER</i> command)</b> Suppose we have loaded four index series and four weighting series to the <b>Index Data</b> and <b>Weight Data</b> panels, respectively, and the command line panel reads:
<br/><br/>
	<div style="margin-left:3em"> 
		$\text{UNC.PER,i1}\\
		\text{UNC.PER,w4}\\
		\text{MyUCi1=UNC.PER,i1}$
	</div><br/>	
Executing this stack of commands, the <b>Results</b> panel will display three series:
	<ol>
		<li>
			an unchained version of index series $i1$ with the name Formula $1$,
		</li>
		<li>
			an unchained version of weighting series $w4$ with the name Formula $2$ and
		</li>
		<li>
			a renamed version of Formula $1$ with the name MyUCi1.
		</li>
	</ol>
</div>

#### Chain-linking: the CLI.PER command

The $\text{CLI.PER}$ command is used to aggregate and/or disaggregate two or more chain-linked indices according to one-period overlap. To this end, the following steps are carried out under the assumption that all chain-linked indices involved in the calculation have the same base and reference years:

* Each chain-linked index is unchained as described for the *UNC.PER* command.
* A weighted sum/difference of the unchained time series is calculated, where the weight of each unchained series in year $t$ is given by the last value of the respective weighting series in year $t-1$. If a weighting series does not cover the year $t = 0$, then its last value in this year is approximated by the last value in year $t = 1$. However, the user can decide whether or not (default) the values of the chain-linked aggregate are displayed for year $t = 1$, see section  [Options](.\globaloptions) for further details.
* The resulting series is chained and normalised to a weighted average of the annual averages of the underlying chain-linked indices in the reference year. Thereby, the weights are given by the projected last values of the weighting series in the year prior to the reference year, using the chain-linked indices' growth factors between the last period of the year prior to the reference year and the annual average in the reference year. Thus, chaining at the end of chain-linking differs from chaining according to the *CHA.PER* command in terms of normalisation.

The specification of the command is given by

$$\text{[Name=]CLI.PER,index1,[weight1,]+/-,index2,[weight2,]...,refyr}$$

with the following arguments:

{: .table .table-bordered}
$\text{Name}$ | Name of the chain-linked aggregate to be displayed in the **Results** panel. If not specified, it is set to *Formula* $n$, where $n$ is the line of the command in the command line panel of the **MyKIX** document. 
$\text{index1}$ | First chain-linked index from the **Index Data** panel to be used in the aggregation/disaggregation. 
$\text{weight1}$ | Weighting series from the **Weight Data** panel which corresponds to the first chain-linked index (*index1*). If not specified, the weighting series with the same running number as the first chain-linked index is taken automatically. 
$+/-$ | Operator used to indicate aggregation (+) or disaggregation (-). All operations are executed "from left to right". 
$\text{index2}$ | Second chain-linked index from the **Index Data** panel to be used in the aggregation/disaggregation. 
$\text{weight2}$ | Weighting series from the **Weight Data** panel which corresponds to the second chain-linked index (*index2*). If not specified, the weighting series with the same running number as the second chain-linked index is taken automatically. 
$\text{...}$ | Additional chain-linked indices, corresponding weighting series and operators to be included in the aggregation/disaggregation. 
$\text{refyr}$ | Reference year of the chain-linked index. Note that no re-referencing is carried out, that is the annual average of the chain-linked index may differ from $100$ in the reference year.


<br/>
<div class="bg-faded" id="ExampleCLIPER">
<b>Example 3: (<i>CLI.PER</i> command)</b> Suppose we have loaded five chain-linked indices and five weighting series to the <b>Index Data</b> and <b>Weight Data</b> panels, respectively, and the command line panel reads:
<br/><br/>
	<div style="margin-left:3em"> 
		$\text{CLI.PER},i1,+,i3,2010\\
    \text{CLI.PER},i1,w2,+,i3,w4,2010\\
    \text{CLI.PER},i2,w5,-,i3,w4,2010\\
    \text{MyCLi1=CLI.PER},i1,w2,+,i3,w4,2010$
	</div><br/>	
Executing this stack of commands, the <b>Results</b> panel will display four chain-linked indices with reference year 2010:
	<ol>
		<li>
			a chain-linked aggregate of the index series $i1$ and $i3$ with the name Formula $1$. Note that this command is equivalent to
			<div style="margin-left:0.75em"> 
				$\text{CLI.ANN},i1,w1,+,i3,w3,2010$
			</div>
		</li>
		<li>
			the same chain-linked indices are used for aggregation but the weighting series $w2$ and $w4$ from the <b>Weight Data</b> panel in use, respectively, and the name of the chain-linked aggregate is Formula $2$,
		</li>
		<li>
			a disaggregated chain-linked index with the name Formula $3$ derived by subtracting the chain-linked index $i3$ from the chain-linked aggregate $i2$, using the respective weighting series $w4$ for index series $i3$ and $w5$ for the aggregate $i2$, and
		</li>
		<li>
			a renamed version of Formula $2$ with the name MyCLi1.
		</li>
	</ol>
</div>

#### Contribution to growth: the CTG.PER command

The $\text{CTG.PER}$ command is used to compute the growth contribution of a chain-linked component to a chain-linked aggregate with the method of <cite>Ribe:1999</cite> when chain-linking is done according to one-period overlap. To this end, the following steps are carried out:

* The chain-linked component and the chain-linked aggregate are unchained as described for the *UNC.PER* command.
* The growth contribution is calculated directly from the unchained component and aggregate according to formulas derived by <cite>Ribe:1999</cite>.

The specification of the command is given by

$$[Name=]CTG.PER,iContr,[wContr,]iTotal,[wTotal,]lags$$

with the following arguments:

{: .table .table-bordered}
$\text{Name}$ | Name of the growth contribution to be displayed in the **Results** panel. If not specified, it is set to *Formula* $n$, where $n$ is the line of the command in the command line panel of the **MyKIX** document. 
$\text{iContr}$ | Chain-linked index from the **Index Data** panel, the growth contribution of which is to be computed. 
$\text{wContr}$ | Weighting series from the **Weight Data** panel which corresponds to the chain-linked index (*iContr*). If not specified, the weighting series with the same running number as the chain-linked index is taken automatically. 
$\text{iTotal}$ | Chain-linked aggregate from the **Index Data** panel. 
$\text{wTotal}$ | Weighting series from the **Weight Data** panel which corresponds to the chain-linked aggregate (*iTotal*). If not specified, the weighting series with the same running number as the chain-linked aggregate is taken automatically. 
$\text{lags}$ | Horizon of the growth contribution, which must be in the set $\{1, 2, 4\}$ for quarterly data and $\{1, 3, 6, 12\}$ for monthly data.

Note that the *CTG.PER* command always assumes an additive aggregation of the chain-linked components to the chain-linked aggregate. Therefore, the direction of the growth contribution (*+/-*) cannot be specified, as opposed to the *CTG.ANN* command.


<br/>
<div class="bg-faded" id="ExampleCTGPER">
<b>Example 4: (<i>CTG.PER</i> command)</b> Suppose we have loaded four quarterly chain-linked indices and four quarterly weighting series to the <b>Index Data</b> and <b>Weight Data</b> panels, respectively, and the command line panel reads:
<br/><br/>
	<div style="margin-left:3em"> 
		$\text{CTG.PER},i1,i3,1\\
    \text{CTG.PER},i1,w2,i3,w4,1\\
    \text{CTG.PER},i1,w2,i3,w4,4\\
    \text{MyCTGi1=CTG.PER},i1,w2,i3,w4,4$
	</div><br/>	
Executing these commands, the <b>Results</b> panel will display four growth contributions:
	<ol>
		<li>
			the contribution of the chain-linked component $i1$ to the growth rate of the chain-linked aggregate $i3$, compared to the previous quarter and named Formula $1$, where $w1$ and $w3$ are used as respective weighting series from the <b>Weight Data</b> panel. Note that this command is equivalent to
			<div style="margin-left:0.75em"> 
				$\text{CTG.ANN},i1,w1,i3,w3,1,$
			</div>
		</li>
		<li>
			the same growth contribution as in (1) but with the weighting series $w2$ and $w4$ used instead and named Formula $2$,
		</li>
		<li>
			the contribution of the chain-linked component $i1$ to the growth rate of the chain-linked aggregate $i3$, compared to the same quarter of the previous year, computed using the same weighting series as in (2) and named Formula $3$ and
		</li>
		<li>
			a renamed version of the previous growth contribution with the name MyCTGi1.
		</li>
	</ol>
</div>