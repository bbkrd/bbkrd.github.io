---
layout: left-menu
title: Global Options
tagline: user documentation for TransReg using GitHub Pages
description: Global Options
order: 30
---

The global option menu enables some degree of customisation of the plug-in. It can be assessed by selecting

$$
\text{Tools} \rhd \text{Options}
$$

from the JD+ drop down menu and clicking on the **TransReg** sheet of the **Demetra** window. The implemented global options are summarised in Table [1](#table1).

<b>Table 1: TransReg global options</b>
<table class="table table-bordered" id="table1">
  <thead>
    <tr>
      <th>Option</th>
      <th>Variable</th>
      <th>Valid choices</th>
      <th>Defaults</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Thresholds for pre-test</td>
      <td>The exponents $k_\mathit{upp}$ and $k_\mathit{low}$ to be used for calculating the upper and lower thresholds according to $$\varepsilon_\mathit{upp} = 10^{- k_\mathit{upp}}$$ and $$\varepsilon_\mathit{low} = 10^{-k_\mathit{low}}.$$ Any choice where $k_\mathit{upp} \geq k_\mathit{low}$ will generate a warning message and cannot be saved. </td>
	  <td>$k_\mathit{upp} \in \{0, \ldots, 99\}$ $k_\mathit{low} \in \{1, \ldots, 100\}$ </td>
	  <td>$k_\mathit{upp} = 4$ $k_\mathit{low} = 12$ </td>
    </tr>
  </tbody>
</table>