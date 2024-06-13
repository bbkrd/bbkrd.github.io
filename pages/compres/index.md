---
layout: left-menu
title: Introduction
tagline: user documentation for CompRes using GitHub Pages
description: CompRes Introduction
order: 0
---

Seasonally adjusted data provide more understandable series for analysts revealing the "news" contained in the time series of interest. Hence, they ease the comparison of longterm
and short-term movements. Due to their importance, their quality must be checked thoroughly. Unfortunately, in contrast to original data, seasonally adjusted time series
contain revisions for two reasons.

First, they may be revised due to a revision of the unadjusted data. Since this occurs due to the availability of an improved information set it is also highly recommended for seasonally adjusted data to be revised correspondingly. The second source of revisions is a more technical reason and caused by a different estimate of the seasonal pattern due to new information (first kind of revisions as well as new data points). Generally, new information should lead to a better (more precise) estimate of the seasonal- and calendar components and hence to a better estimate of the seasonally adjusted figure. On the other hand, this always goes along with revisions and possible confusion of the users. Especially, if these technical revisions occur only due to new observations, the seasonally adjusted time series shows revisions while the original series does not, which may be difficult for users
to comprehend.

The ESS guidelines on seasonal adjustment suggest a balanced procedure, where both precision as well as revisions are taken into consideration. One suggested approach
is called partial concurrent and re-identifies the model only once a year, but re-estimates the coefficients every time new or revised data become available. This lowers the revisions
on average, but revisions still occur with each new or revised data point. A second recommended approach is called controlled current adjustment and can be used
if the seasonal component is stable enough. The guidelines describe this approach in the following way:
<div style = "margin-left:2.5em">"Forecasted seasonal and calendar factors derived from a current adjustment are used to seasonally adjust the new or revised unadjusted data. However, an internal check is performed against the results of the partial concurrent adjustment, which is preferred if a significant difference exists. This means that each series needs to be seasonally adjusted twice." (Eurostat, 2015)</div>
<br/>
This plug-in supports the controlled current adjustment approach. Therefore, the first important feature is the storage of the current components. Secondly, some key quality measures for the comparison between the current adjustment and the partial concurrent adjustment are summarised in an additional node of the graphical user interface. Finally, a pre-defined summary of the output containing the most important quality measures can be exported to HTML files.
