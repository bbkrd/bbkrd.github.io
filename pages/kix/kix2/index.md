---
layout: left-menu
title: Introduction
tagline: user documentation for KIX2.0 using GitHub Pages
description: Introduction to KIX2.0
order: 100
category: KIX2.0
---

As opposed to fixed-base indices, aggregating chain-linked index series is anything but trivial. Yet, some of the most prominent macroeconomic indicators, such as national accounts or harmonised indices of consumer prices, are constructed as Laspeyres-type chain-linked indices.

Furthermore, chain-linking also has implications for seasonal adjustment, whenever aggregates are indirectly seasonally adjusted from directly seasonally adjusted components (see <cite>Eurostat:2024</cite>, items 3.2 and 5.6). Since the software JDemetra+ (JD+) is primarily developed for the seasonal adjustment process itself, it does not offer this kind of features.

Hence, the KIX2.0 plug-in has been designed to facilitate the handling of chain-linked indices, where KIX is the abbreviation of KettenIndeX which is the German word for chain index. It offers chaining, unchaining, chain-linking (aggregation or disaggregation of two or more chain-linked indices) as well as the calculation of growth contributions. In contrast to fixed-base indices the outcome of the latter is dependent on the method used to calculate the growth contributions. KIX2.0 offers an elegant way where only the chain-linked indices of interest as well as the corresponding weights are needed to compute the growth contributions. It implements the partial contribution to growth method for volume indices chain-linked according to annual overlap.

All operations are available for monthly and quarterly time series. Although primarily developed for the handling of chain-linked indices in the seasonal adjustment process, all calculations of course can be applied to original (unadjusted) figures as well.

Currently, the software does not apply any tests concerning the usefulness or appropriateness of the investigated time series. In this sense, no test is implemented to check whether or not input series are chained or unchained. Furthermore, the software does not check the reference year of the input series. In the end, the user is solely responsible for the meaningfulness of any operation.

### Overview

The following table provides an overview of all commands available in the current version of KIX2.0:

{: .table .table-bordered}
|Operation | Command  | Description|
|---|---|---|
|Chaining | *CHA.ANN* | Chaining of growth factors with annual overlap. |
|Unchaining | *UNC.ANN* | Calculation of growth factors of a chain-linked index series with annual overlap.|
|Chain-linking | *CLI.ANN*| Aggregation and disaggregation of chain-linked indices with annual overlap. |
|Growth contribution | *CTG.ANN* | Calculation of growth contribution of a component series to an aggregate series' growth rate according to partial contribution to growth for annual overlap. | 

<br/>

### Installation

Download the installation file from the plug-in's GitHub repository and save it to your local folder of choice. Choose 

$$\text{Tools} \rhd \text{Plugins}$$

from the JD+ drop down menu, open the **Downloaded** sheet and press the **Add Plugins** button. Select the local copy of the installation file, click the **Install** button and accept the terms in the licence agreements. Once the installation is finished, KIX documents and a global option menu are available. Note that the plug-in is automatically activated and, therefore, a restart of JD+ is not necessary.
