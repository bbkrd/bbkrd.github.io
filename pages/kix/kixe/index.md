---
layout: left-menu
title: Introduction
tagline: user documentation for KIXE using GitHub Pages
description: Introduction to KIXE
order: 200
category: KIXE
---

As opposed to fixed-base indices, aggregating chain-linked index series is anything but trivial. Yet, some of the most prominent macroeconomic indicators, such as national accounts or harmonised indices of consumer prices, are constructed as Laspeyres-type chain-linked indices.

Furthermore, chain-linking also has implications for seasonal adjustment, whenever aggregates are indirectly seasonally adjusted from directly seasonally adjusted components (see <cite>Eurostat:2015</cite>, items 3.1 and 6.5). Since the software JDemetra+ (JD+) is primarily developed for the seasonal adjustment process itself, it does not offer this kind of features.

Hence, the KIX_E plug-in has been designed to facilitate the handling of chain-linked indices, where KIX is the abbreviation of KettenIndeX which is the German word for chain index. It offers chaining, unchaining, chain-linking (aggregation or disaggregation of two or more chain-linked indices) as well as the calculation of growth contributions. In contrast to fixed-base indices the outcome of the latter is dependent on the method used to calculate the growth contributions. KIX_E offers an elegant way where only the chain-linked indices of interest as well as the corresponding weights are needed to compute the growth contributions. It implements the method of <cite>Ribe:1999</cite> for price indices chain-linked according to one-period overlap.

All operations are available for monthly and quarterly time series. Although primarily developed for the handling of chain-linked indices in the seasonal adjustment process, all calculations of course can be applied to original (unadjusted) figures as well.

Currently, the software does not apply any tests concerning the usefulness or appropriateness of the investigated time series. In this sense, no test is implemented to check whether or not input series are chained or unchained. Furthermore, the software does not check the reference year of the input series. In the end, the user is solely responsible for the meaningfulness of any operation.

#### Overview

The following table provides an overview of all commands available in the current version of KIX_E:

{: .table .table-bordered}
Operation | Command  | Description
|---|---|---|
Chaining | *CHA.PER* | Chaining of growth factors with one-period overlap.
Unchaining | *UNC.PER* | Calculation of growth factors of a chain-linked index series with one-period overlap.
Chain-linking | *CLI.PER* | Aggregation and disaggregation of chain-linked indices with one-period overlap.
Growth contribution | *CTG.PER* | Calculation of growth contribution of a component series to an aggregate series' growth rate according to Ribe (1999). 

