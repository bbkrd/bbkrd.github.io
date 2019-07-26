---
layout: left-menu
title: Appendix
tagline: user Documentation for SpecParser using GitHub Pages
description: Appendix
order: 30
---

#### Component type allocation of user-defined regressors
In X12-ARIMA and JD+ the user can specify which component an user-defined regressor should be allocated to. 
The tables show the interrelationship between both software and the algorithm.

<table class="table table-bordered" id="allocationRegular">
	<caption>Table 1: Allocation of user-defined regressors in default mode</caption>
	<tr>
		<th>X-12ARIMA spc-file</th>
        <th>JD+ specification</th>
		<th>Component type</th>
		<th>Algorithm table</th>
	</tr>
	<tr>
		<td><i>usertype = td</i></td>
        <td>$\text{Regression} \rhd \text{Calendar} \rhd \text{UserDefined}$</td>
		<td>-</td>
		<td>A6</td>
	</tr>
	<tr>
		<td><i>usertype = user<br/># user = final</i></td>
        <td style="vertical-align:middle" rowspan="5">$\text{Regression} \rhd \text{User-defined variables}$</td>
		<td>Irregular</td>
		<td>A8i, A8</td>
	</tr>
	<tr>
		<td><i>usertype = user<br/># user = final</i></td>
		<td>Series</td>
		<td>A9ser, A9</td>
	</tr>
	<tr>
		<td><i>usertype = seasonal</i></td>
		<td>Seasonal</td>
		<td>A8s, A8</td>
	</tr>
	<tr>
		<td><i>usertype = ls</i></td>
		<td>Trend</td>
		<td>A8t, A8</td>
	</tr>
	<tr>
		<td><i>usertype = holiday</i></td>
		<td>Undefined</td>
		<td>A9u</td>
	</tr>
</table>

<table class="table table-bordered" id="allocationCalendar">
	<caption>Table 2: Allocation of user-defined regressors in calendar mode</caption>
	<tr>
		<th>X-12ARIMA spc-file</th>
        <th>JD+ specification</th>
		<th>Algorithm table</th>
	</tr>
	<tr>
		<td><i>usertype = td</i></td>
        <td style="vertical-align:middle" rowspan="6">$\text{Regression} \rhd \text{User-defined variables}$</td>
		<td style="vertical-align:middle" rowspan="6">A6</td>
	</tr>
	<tr>
		<td><i>usertype = user<br/># user = final</i></td>
	</tr>
	<tr>
		<td><i>usertype = user<br/># user = final</i></td>
	</tr>
	<tr>
		<td><i>usertype = seasonal</i></td>
	</tr>
	<tr>
		<td><i>usertype = ls</i></td>
	</tr>
	<tr>
		<td><i>usertype = holiday</i></td>
	</tr>
</table>