---
layout: left-menu
title: Storage introduction
tagline: user documentation for CompRes using GitHub Pages
description: CompRes Storage intro
category: Storage
order: 20
---

Since CompRes compares current adjustment with partial concurrent adjustment, forecasted seasonal and calendar components are needed. These can be saved in the workspace (Alternatively, the components can be loaded from an external data provider e.g. [ExcelAdapter](excelAdapter). Therefore, you need an individual Output Adapter. Then this option can be chosen under $\text{Tools} \rhd \text{Options} \rhd \text{Demetra} \rhd \text{DatasourceUpdateOptions}$.) 

Once, the forecasted components of an SA-item shall be replaced by new estimates, right mouse click "Save to workspace" on the SA-item and select "Seasonal factor" or "Calendar factor". If components for more than one SA-item are to be saved, first select the SA-items and then right mouse click "Save to Workspace" and select "Seasonal factor" or "Calendar factor".

The calendar component consists of the combined tables A6 and A7 and the seasonal component is table D10. Both series are extended with their forecasts. The forecast horizon is to be defined within the X11 specification of JDemetra+. The values can be made visible by choosing $\text{Windows} \rhd \text{Properties}$ from the menu under Metadata. These values are saved, when the workspace is saved.
