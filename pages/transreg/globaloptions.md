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

<table class="table table-bordered" id="table1">
  <caption>Table 1: TransReg global options</caption>
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
      <td>Maximum number of groups</td>
      <td>The maximum number of period-specific daughter regression variables, $g_\mathit{max}$, to be allowed for grouping a mother regression variable. It applies to monthly and quarterly data alike. If $g_\mathit{max} > 4$ and a quarterly regression variable is considered, then $g_\mathit{max} = 4$ is automatically used in this particular case. </td>
      <td>$g_\mathit{max} \in \{2, \ldots, 12\}$ </td>
      <td>$g_\mathit{max} = 2$ </td>
    </tr>
    <tr>
      <td>Thresholds for pre-test</td>
      <td>The exponents $k_\mathit{upp}$ and $k_\mathit{low}$ to be used for calculating the upper and lower thresholds according to $$\varepsilon_\mathit{upp} = 10^{- k_\mathit{upp}}$$ and $$\varepsilon_\mathit{low} = 10^{-k_\mathit{low}}.$$ Any choice where $k_\mathit{upp} \geq k_\mathit{low}$ will generate a warning message and cannot be saved. </td>
	  <td>$k_\mathit{upp} \in \{0, \ldots, 99\}$ $k_\mathit{low} \in \{1, \ldots, 100\}$ </td>
	  <td>$k_\mathit{upp} = 4$ $k_\mathit{low} = 12$ </td>
    </tr>
  </tbody>
</table>