---
layout: left-menu
title: ExcelAdapter
tagline: user documentation for CompRes using GitHub Pages
description: CompRes ExcelAdapter
category: Storage
order: 21
---

The ExcelAdapter is an external OutputAdapter as described in [Storage introduction](storage). You can download the latest installation files *ExcelAdapter-X.X.nbm* from the releases of the [GitHub repository](https://github.com/bbkrd/ExcelAdapter/releases).

The following features will be added to your JDemetra+ Installation:

#### Loading data via Excel for the CompRes Plug-In
Under $\text{Tools} \rhd \text{Options} \rhd \text{Demetra} \rhd \text{DatasourceUpdateOptions}$ you will get the ExcelConnection.
It will use the following metadata:

{: .table .table-bordered}
|*Name*|*Description*|
|excel.file|Absolut path to the Xlsx|
|excel.sheet|Name of the worksheet|
|excel.series|Name of the time series in the worksheet|

You can add the needed metadata to a time series with rightclick "Add Excel MetaData". Then you can change the information in the properties sheet ($\text{Windows} \rhd \text{Properties}$).


#### Write specific data from X13 to Excel

The following time series can be written to Excel: A1a, A6(including A7), D10, D11, D12, D13. In $\text{Tools} \rhd \text{Options} \rhd \text{Demetra} \rhd \text{ExcelAdapter}$ you can select them.

To start the saving process you can select the items in the multidocument and rightclick "Save to Excel" or use $\text{Statistical Methods} \rhd \text{Save all MD to Excel}$ to save all items of all multidocuments to Excel.
