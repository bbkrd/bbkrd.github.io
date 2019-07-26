---
layout: left-menu
title: Introduction
tagline: user documentation for KIX-CC using GitHub Pages
description: Introduction to KIX-CC
order: 300
category: KIX-CC
---

The program KIX-CC offers chain-linking procedures for continuously chain-linked indices like the IIE. That means the aggregation or disaggregation of two or more chain-linked indices, as well as the calculation of growth contributions.

The plug-in requires the indices of interest and the corresponding weights for all operations. Indices and weights may be of any periodicity (e.g. monthly, quarterly or annual). The contribution of a subindex's growth to the overall growth can be calculated for the change to the previous periods (i.e. changes to previous month, quarter, half-year or year). In contrast to fixed-base indices, the outcome of the growth contribution depends on the method used. The KIX-CC plug-in uses the formula of Arz/Rentzsch 2019, which was developed in accordance with the approach of Ribe 1999 for chain-linked price indices of  the one-period overlap type.

Currently, the software does not apply any tests concerning the usefulness or appropriateness of the investigated time series. In this sense, no test is implemented to check whether or not input series are chained or unchained. Furthermore, the software does not check the reference year of the input series. In the end, the user is solely responsible for the meaningfulness of any operation.

## Overview

The KIX-CC plug-in allows the user to carry out aggregation and disaggregation of continuously chained indices as well as calculation of their growth contributions in JD+. The following table provides an overview of the operations, commands, functions, and methods available for monthly and quarterly time series:


{: .table .table-bordered}
| Operation | Command |Description |  Method |
| --------- | -------- | ------- | ------ |
| Chain-linking | *CLI.CC* |Aggregation and disaggregation of continuously chained indices |  Arz/Rentzsch 2019|
| Growth contribution | *CTG.CC* |Calculation of growth contribution of a component series to an aggregate series' growth rate |  Rentzsch 2019|

## Installation

Download the installation file from the plug-in's GitHub repository and save it to your local folder of choice. Choose

$$\text{Tools} \rhd \text{Plugins}$$

from the JD+ drop down menu, open the **Downloaded** sheet and press the **Add Plugins** button. Select the local copy of the installation file, click the **Install** button and accept the terms in the licence agreements. Once the installation is finished, KIX documents and a global option menu are available. Note that the plug-in is automatically activated and, therefore, a restart of JD+ is not necessary.