---
layout: left-menu
title: Options
tagline: user documentation for KIX2.0 using GitHub Pages
description: KIX2.0 Options
order: 130
category: KIX2.0
---

#### Global options

The global option menu is accessible through $\text{Tools} \rhd  \text{Options} \rhd \text{Demetra} \rhd \text{KIX} $. Users can customise the outcome to be displayed in the **Results** panel after executing $\text{CLI.ANN}$ command. More precisely, when a weighting series does not cover the year before the start year of the respective index series, the previous-year weights for the start year are always approximated with the weights of the start year itself (annual average in case of annual overlap and last period in case of one-period overlap) and used in all subsequent calculations. However, the user can decide whether or not the final outcome of the command is displayed for the start year. In principle, two options are available:

$\text{Yes}$ ||  The final outcome is displayed for the start year. This is the default option for the $\text{CLI.ANN}$ command. 
$\text{No}$ || The final outcome is not displayed for the start year, that is the chain-linked aggregate lags the chain-linked indices by one year.

<br/>
#### Alias commands

The KIX2.0 plug-in is based on the Excel add-in which was firstly available in German language. Hence, some commands have older German abbreviations. In order to ease the migration from the Excel add-in to the KIX2.0 plug-in, the older commands are still available as aliases.

The following table gives an overview of the alias commands:

{: .table .table-bordered}
Command | Alias
---|---
$\text{CLI.ANN}$ | $\text{KIX}$ 
$\text{CTG.ANN}$ | $\text{WBG}$ 
