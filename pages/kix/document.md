---
layout: left-menu
title: KIX Document
tagline: user documentation for KIX using GitHub Pages
description: KIX Document
order: 10
---

The KIX document is the main device of the plug-in, as it enables data input and calculations based on different chain-linking methods as well as storage of the results. A new document can be created and opened simultaneously by selecting

$$\text{Tools} \rhd  \text{KIX}$$

from the JD+ drop down menu. As a sequential alternative, a new KIX document can be created by choosing **New** after right-clicking on

$$\text{KIX}$$

in the **Workspace** window. Then, the created document can be opened by double-clicking on it. Either way, the default name of a new KIX document is **KIX-Number**, where **Number** is a counter of the KIX documents which are available in the current workspace. For example, a new document created in a workspace which does not contain any other KIX document will be named **KIX-1**. Any default name can be changed by right-clicking on

$$\text{KIX} \rhd \text{KIX-Number}$$

in the **Workspace** window and selecting **Rename**. For convenience, we subsequently use the name **MyKIX** to refer to the KIX document currently in use. The global option menu of the plug-in can be accessed by choosing $\text{Tools} \rhd  \text{Options} \rhd \text{Demetra} \rhd \text{KIX}$ from the drop down menu.

### General structure

The KIX document consists of four elements: the command line panel, two data panels and a results panel.

* The command line panel is used to specify and execute operations of data stored in the two data panels.
* The **Index Data** panel is used to input and store index series. After data input, it provides the information shown in Table 1.
* The **Weight Data** panel is used to input and store the series which are used to derive the weights that correspond to the index series. After data input, it provides the information shown in Table 1.
* The **Results** panel is used to display the results of the operations executed in the command line panel. It is essentially a table, the $k$-th column of which is the data obtained from executing the $k$-th command.

<table id="table1" class="table table-bordered">
  <caption>Table 1: Index and weight data panel content of the KIX document</caption>
  <tr>
    <th>Column</th>
    <th>Content</th>
  </tr>
  <tr>
    <td>Name</td>
    <td>Reference name of the input series to be used in the command line panel. It is simply $i$ for index data and $w$ for weight data followed by a running number.</td>
  </tr>
  <tr>
    <td>Description</td>
    <td>Original name of the input series.</td>
  </tr>
  <tr>
    <td>Frequency</td>
    <td>Periodicity of the input series.</td>
  </tr>
  <tr>
    <td>Start</td>
    <td>First period of the input series.</td>
  </tr>
  <tr>
    <td>End</td>
    <td>Last period of the input series.</td>
  </tr>
</table>

### Data input

After the index and weighting series have been imported to the current JD+ workspace via any of the available data providers, they can be made available in the **Index Data** and **Weight Data** panels via drag and drop, in line with familiar JD+ standards. Note that for either data type the running numbers of the reference names are determined by the order of the series in the data provider. Therefore, it is highly recommended to sort the index and weighting series in the same way in the data provider in order to avoid any mismatch between corresponding running numbers.

If the index and/or weighting series are changed or updated in the external data source after they have been loaded into a KIX document, they can be updated in the KIX document as well by selecting **Refresh** after right-clicking on

$$\text{KIX} \rhd \text{MyKIX}$$

in the **Workspace** window. In this case, all calculations specified in the command line panel will be recomputed automatically with the refreshed data and displayed in the **Results** panel. However, refreshing the index and/or weighting series in a KIX document does not affect calculations in other JD+ documents, such as seasonal adjustment documents, which are based on data stored in the **Results** panel.

### Data storage

KIX documents can be saved as part of the current JD+ workspace. Also, single time series displayed in the **Results** panel can be dragged and dropped to other JD+ documents of the current workspace and, when appropriate, to external programs such as Excel.
