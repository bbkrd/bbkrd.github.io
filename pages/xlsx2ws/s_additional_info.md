---
layout: left-menu
title: Additional Information
description: Xlsx2Ws Specification Additional Information
order: 210
category: Specification
---

<h4 id="dates">Supported date formats</h4>

<table class="table table-bordered" id="dates">
 <thead>
  <tr>
   <th>Format</th>
   <th>Example</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td>YYYY[.MM[.DD]]</td>
   <td>	1989		→ 01.01.1989 <br/>
		1989.03		→ 01.03.1989 <br/>
		1989.03.15	→ 15.03.1989</td>
  </tr>
  <tr>
   <td>Excel date value</td>
   <td>	1		→ 	01.01.1900<br/>
		43890	→ 	29.02.2020</td>
  </tr>
 </tbody>
</table>

<h4 id="span">Span</h4>
<table class="table table-bordered">
 <thead>
  <tr>
   <th>JDemetra+</th>
   <th>Excel</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td>All</td>
   <td>default/don't specify any span</td>
  </tr>
  <tr>
   <td>None</td>
   <td>_start or _end filled with "X"</td>
  </tr>
  <tr>
   <td>From</td>
   <td>just _start</td>
  </tr>
  <tr>
   <td>Between</td>
   <td>_start and _end</td>
  </tr>
  <tr>
   <td>To</td>
   <td>just _end</td>
  </tr>
  <tr>
   <td>First</td>
   <td>just _first</td>
  </tr>
  <tr>
   <td>Last</td>
   <td>just _last</td>
  </tr>
  <tr>
   <td>Excluding</td>
   <td>_first and _last</td>
  </tr>
 </tbody>
</table>

<h4 id="regressor">Regressor syntax</h4>
Variables.Name[\*Regressortype] e.g. Weather.iceDays\*c for the regressor iceDays in variables "weather" as userdefined calendar or Vars-1.x_1\*t for the regressor "x_1" in variables "Vars-1" as trend regressor.

<table class="table table-bordered">
 <thead>
  <tr>
   <th>Syntaxpart</th>
   <th>Example</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td>Variables</td>
   <td>Vars-1 <br/>
Weather</td>
  </tr>
  <tr>
   <td>Name</td>
   <td>	x_1<br/>
		iceDays</td>
  </tr>
  <tr>
   <td>Regressortype</td>
   <td>c - UserdefinedCalendar<br/>
i - Irregular<br/>
t - Trend<br/>
y - Series<br/>
s - Seasonal<br/>
sa - SeasonallyAdjusted<br/>
u - Undefined</td>
  </tr>
 </tbody>
</table>

<h4 id="parameter">Parameter syntax</h4>
Value[\*Parametertype] e.g. 0.5\*f for a 0.5 fixed valued parameter <br/>
If an unknown or no parameter type is specified the parameter will be fixed.
<table class="table table-bordered">
 <thead>
  <tr>
   <th>Syntaxpart</th>
   <th>Example</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td>Value</td>
   <td>	0.5 <br/>
		2.1 </td>
  </tr>
  <tr>
   <td>Parameter type</td>
   <td>	i - Initial  <br/>
u - Undefined <br/>
f - Fixed</td>
  </tr>
 </tbody>
</table>