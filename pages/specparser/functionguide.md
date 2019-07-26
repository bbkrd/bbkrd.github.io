---
layout: left-menu
title: Function guide
tagline: user Documentation for SpecParser using GitHub Pages
description: Function guide
order: 20
---

#### General

{: .table .table-bordered}
**Data input format** |  X-12ARIMA allows to use different data input formats. The SpecParser supports the most important formats: free and datevalue. % and x12save. Further details on the formats are provided in the X-12ARIMA Reference Manual.
**Translation report** | There are differences in both software, e.g. missing specifications, different default values or calculations. The translation report informs about possible reasons of differences in the results.Three categories of notifications are reported:<br/> *Errors* no translation possible, e.g. there is no data<br/> *Warnings* results of JD+ and X-12ARIMA are likely to differ<br/> *Messages* differences that do not affect the results
**Start argument** | The SpecParser loads all data available in the JD+ workspace ignoring the *start* argument. Instead the content of the *start* argument specifies the span.
**List of variables** | Only one variables list in **Utilities** called reg\_SpecParser contains the regressors with no regard to the number of times the SpecParser is used in the current workspace. <br/> The names of the regressors are defined in the *user* argument. If a regressor with the same name but with different values already exists in the list of reg\_SpecParser, the second variable gets an appendix with a counter on its name, e.g. myReg[1].
**Allocation of user-defined regressors**  |  There are different locations in the X-12 algorithm where the regressors have an effect on the results. Two modes are available in the SpecParser options to replicate the most common uses: <br/> *Default mode* This is the default setting. The allocation is the same as in X-12ARIMA. The regressors get their component type allocation from the *usertype* argument. They are set at **User-defined variables** in the JD+ regression specification. For more details see table [1 in the appendix](./appendix#allocationRegular).<br/> *Calendar mode* This option sets the regressors at $\text{Calendars} \rhd \text{TradingDays} \rhd \text{UserDefined}$ in the JD$+$ regression specification All regressors are allocated to a calendar (see table [2 in the appendix](./appendix#allocationCalendar)).

<br/>
#### Single mode

{: .table .table-bordered}
**Denotation**            | The x13-document gets the name of the spc-file.
**Spec is modifiable**    | The loaded specification file is shown in a text area of the SpecParser window.                                    The content of the spc-file can be changed here.                                    Click on the button **Refresh JD+Spec** to translate the changes.                                    However, the x13-document has to be closed before, since there is no automatic update for the graphical interface.

<br/>
#### Multi mode

<table class="table table-bordered">
	<tr>
		<th>Denotation</th>
        <td>The multi-document gets the name of the mta-file. The single series get their name from the input of the mta-file.</td>
	</tr>
	<tr>
		<th>List of mta input</th>
		<td>The list consists of defined spc-files in the mta-file. For each specification the translation report is shown when the respective list item is marked. With a double click on an item the single SpecParser window opens with the specification input. If desired the content can be modified here.</td>
	</tr>
	<tr>
		<th>Highlighted items</th>
		<td>The highlighting depends on the translation report:
			<dl>
			<dt><i>Red</i></dt>
			<dd>There are one or more errors.</dd>
			<dt><i>Orange</i></dt>
			<dd>There are one or more warnings that require the user to act on.</dd>
			<dt><i>Yellow</i></dt>
			<dd>There are one or more warnings that are unlikely to require the users intervention.</dd>
			<dt><i>Green</i></dt>
			<dd>There are only messages</dd>
			</dl>
		</td>
	</tr>
	<tr>
		<th>Refresh of input data</th>
		<td>There is no possibility to refresh the input data (series and regressors) loaded by the SpecParser. But the data in the translated document can be exchanged by loading the data in the provider window and drag'n'drop it in the document.</td>
	</tr>
</table>