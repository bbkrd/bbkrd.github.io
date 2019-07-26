---
layout: left-menu
title: Commands
tagline: user documentation for KIX-CC using GitHub Pages
description: KIX-CC Commands
order: 320
category: KIX-CC
---

Any single command or stack of commands is specified in the command line panel and executed by pressing either the Ctrl+Enter keys together or the "green arrow" button in the upper left corner of that panel.
Please note that the plug-in is not developed to check the sensibility of your computations. To yield sensible results, the chain-linked indices to be aggregated or disaggregated have to have the same reference period. In this sense, the reference period is defined as the period for which the series is based to an average of 100.

Each command described in this section is essentially a sequence of mandatory and optional arguments. To distinguish the two types of arguments, the latter are displayed in brackets. Comments can be added as entire lines by using the **#** symbol as the first character in the respective lines. However, please note that comments cannot be added after commands.

### Chain linking: the CLI.CC command

The $\text{CLI.CC}$ command is used to aggregate and/or disaggregate two or more continuously chained indices. To this end, the following steps are carried out under the assumption that all continuously chained indices involved in the calculation have the same base and reference periods:

1. Each index is unchained.
2. A weighted sum/difference of the unchained time series is calculated, where the weight of each unchained series in period $t$ is given by the last value of the respective weighting series in period $t-1$.
3. In cases where a subindex's weight is changed to $0$ in period $t-1$, the subindex is unchanged and its value keeps the amount of period $t-1$.
4. The resulting series is chained. To obtain a time series showing the long-term growth compared to the first observation, the aggregated growth factors are continuously multiplied. For the first period, a starting value of 100 is set.
5. The aggregate is normalised to the desired reference period, so that the reference period equals 100.

The specification of the command is given by

$$ \text{[Name=]CLI.CC,index1,[weight1,]}+/-\text{,index2,[weight2,]...,refperiod} $$

with the following arguments:

{: .table .table-bordered}
$$ \text{Name}$$	| Name of the continuously chained aggregate to be displayed in the **Results** panel. If not specified, it is set to *Formula n*, where *n* is the line of the command in the command line panel of the **MyKIX** document.
$$\text{index1}$$ | First index from the **Index Data** panel to be used in the aggregation/disaggregation.
$$\text{weight1}$$ | Weighting series from the **Weight Data** panel which corresponds to the first index $$index1$$. If not specified, the weighting series with the same running number as the first index is taken automatically.
$$+/-$$ | Operator used to indicate aggregation ($$+$$) or disaggregation ($$-$$). All operations are executed "from left to right".
$$\text{index2}$$ | Second index from the **Index Data** panel to be used in the aggregation/disaggregation.
$$\text{weight2}$$ | Weighting series from the **Weight Data** panel which corresponds to the second index $$index2$$. If not specified, the weighting series with the same running number as the second index is taken automatically.
$$\text{...}$$ | Additional indices, corresponding weighting series and operators to be included in the aggregation/disaggregation.
$$\text{refperiod}$$ | Depend on the period unit (monthly, quarterly, semi-annual or annual) the user has to choice the correct reference period of the continuously chained index (for example: the notation $\text{IV-2012}$ means the April of $2012$ for monthly time series; for quarterly time series it means the fourth quarter of $2012$).

&nbsp;
<div class="bg-faded" id="ExampleCliCC">
	<b>Example 1: (CLI.CC command)</b> Suppose we have loaded five quarterly indices and seven quarterly weighting series to the <b>Index Data</b> and <b>Weight Data</b> panels, respectively, and the command line panel reads:

	<div style="margin-left:3em">
		$\text{CLI.CC},i1,+,i2,\text{IV-2012} \\
		\text{CLI.CC},i5,w5,-,i4,w4,\text{IV-2012} \\
		\text{MyCLi1=CLI.CC},i1,w6,+,i2,w7,-,i4,w4,\text{I-2015}$
	</div>

	Executing these commands, the <b>Results</b> panel will display three continuously chained indices:
	<ol>
		<li>
		A continuously chained aggregate of the index series $i1$ and $i2$, where $w1$ and $w2$ are used as respective weighting series from the <b>Weight Data</b> panel and with reference period fourth quarter of 2012, with the name <i>Formula 1</i>,
		</li>
		<li>
		A disaggregated continuously chained index with the name <i>Formula 2</i> derived by subtracting the continuously chained index $i4$ from the continuously chained aggregate $i5$, using the weighting series $w4$ for index series $i4$ and $w5$ for the aggregate $i5$ and with reference period fourth quarter of 2012,
		</li>
		<li>
		A continuously chained aggregate with the name <i>Formula 3</i>, where the index series $i1$ and $i2$ are aggregated with the aid of the weighting series $w6$ and $w7$, and subtracting the component index series $i4$ using $w4$ as weighting series from the <b>Weight Data</b> panel, with reference period first quarter of 2015 and renamed by user's choice.
		</li>
	</ol>
	
	See the Excel file "KIXCC Examples" in the repository for numeric examples.
</div>
<br/>
### Contribution to growth: the CTG.CC command

The $\text{CTG.CC}$ command is used to compute the growth contribution of a continuously chained component to a continuously chained aggregate with the method of Rentzsch 2019. To this end, the following steps are carried out:

1. The continuously chained component and the continuously chained aggregate are unchained.
2. The period-on-period growth rates of the unchained components are weighted by their preceding periods' weighting shares.
3. The overall growth and partial growth rates are cumulated over all relevant periods.

The specification of the command is given by

$$ \text{[Name=]CTG.CC,iContr,[wContr,]iTotal,[wTotal,]lags} $$

with the following arguments:

{: .table .table-bordered}
$\text{Name}$| Name of the growth contribution to be displayed in the **Results** panel. If not specified, it is set to *Formula n*, where *n* is the line of the command in the command line panel of the **MyKIX** document. 
$\text{iContr}$| Continuously chained index from the **Index Data** panel, the growth contribution of which is to be computed. 
$\text{wContr}$| Weighting series from the **Weight Data** panel which corresponds to the chain-linked index $iContr$. If not specified, the weighting series with the same running number as the continuously chained index is taken automatically. 
$\text{iTotal}$| Continuously chained aggregate from the **Index Data** panel. 
$\text{wTotal}$| Weighting series from the **Weight Data** panel which corresponds to the continuously chained aggregate $iTotal$. If not specified, the weighting series with the same running number as the continuously chained aggregate is taken automatically. 
$\text{lags}$| Time span that the growth contribution is calculated for. The syntax does not depend on the periodicity of the data. For example, a lag of $1$ calculates the contribution to the period-on-period growth rate. To obtain the contribution to the year-on-year growth rate, the lag for monthly data must be set to $12$ and for quarterly data to $4$. Alternatively, $-1$ or $-2$ may be used for a lag of $1$ or $2$ years, respectively.

Note that the $\text{CTG.CC}$ command always assumes an additive aggregation of the continuously chained components to the continuously chained aggregate.


<div class="bg-faded" id="ExampleCtgCC">
	<b>Example 2: (CTG.CC command)</b> Suppose we have loaded five quarterly continuously chained indices and seven quarterly weighting series to the <b>Index Data</b> and <b>Weight Data</b> panels, respectively, and the command line panel reads:

	<div style="margin-left:3em">
			$\text{CTG.CC},i1,i3,1 \\
			\text{CTG.CC},i3,w3,i5,w5,4 \\
			\text{MyUCi1=CTG.CC},i2,w7,i3,w3,1$
	</div>

	Executing these commands, the <b>Results</b> panel will display three growth contributions:
	<ol>
		<li>
		The contribution of the continuously chained component $i1$ to the growth rate of the continuously chained aggregate $i3$, compared to the previous quarter and named <i>Formula 1</i>, where $w1$ and $w3$ are used as respective weighting series from the <b>Weight Data</b> panel,
		</li>
		<li>
		The contribution of the continuously chained component $i3$ to the growth rate of the continuously chained aggregate $i5$, compared to the previous year (four periods) and named <i>Formula 2</i>, where $w3$ and $w5$ are used as weighting series from the <b>Weight Data</b> panel,
		</li>
		<li>
		The contribution of the continuously chained component $i2$ to the growth rate of the continuously chained aggregate $i3$, compared to the previous quarter and named <i>Formula 3</i>, where $w7$ and $w3$ are used as weighting series from the <b>Weight Data</b> panel and the result is renamed by user's choice.
		</li>
	</ol>
	
	See the Excel file "KIXCC Examples" in the repository for numeric examples.
</div>