---
layout: left-menu
title: TransReg document
tagline: user documentation for TransReg using GitHub Pages
description: TransReg document
order: 10
---

The TransReg document is the main device of the plug-in as it enables input and transformation of regression variables as well as storage of transformed regression variables. A new document can be created and opened simultaneously by selecting

$$ \text{Tools} \rhd \text{TransReg}$$

from the JD+ drop down menu. As a sequential alternative, a new TransReg document can be created by choosing **New** after right-clicking on

$$ \text{Utilities} \rhd \text{TransReg} $$

in the **Workspace** window. Then the created document can be opened by double-clicking on it. Either way, the default name of a new TransReg document is **TransReg-Number**, where **Number** is a counter of the TransReg documents which are available in the current workspace. For example, a new document created in a workspace which does not contain any other TransReg document will be named **TransReg-1**. Any default name can be changed by right-clicking on

$$ \text{Utilities} \rhd \text{TransReg} \rhd \text{TransReg-Number}$$

in the **Workspace** window and selecting **Rename**. For convenience, we subsequently use the name **MyTransReg** to refer to the TransReg document currently in use. Similarly, we will use **MyRegVar** as the default name of a user-defined regression variable.

### General structure

The TransReg document consists of three elements: the top banner, the data panel and the specification panel.

* The top banner contains the data input field labelled *Drop data here*, in line with familiar JD+ standards.
* The data panel is essentially a table with a maximum of eight columns. The information reported in these columns is summarised in Table [2](#table2) . By default, all columns are displayed but the user can customise the appearance of the data panel by right-clicking on any spot in the light grey title row and selecting the preferred columns, except for "Variable" which is always displayed.
* The specification panel provides functionalities for transforming regression variables loaded into the data panel. A detailed description of the available transformations is given in Section [Transformation](./transformations). The appearance of this panel has been adopted from the specifications used for seasonal adjustment.

<b id="table2">Table 2: Data Panel content of the TransReg document</b>

| *Column* || *Information* || *Displayed for* |
| --- || --- || --- |
| Variable || Name of regression variable. Transformed variables are ordered in a tree-type structure to facilitate identification of dependencies. || All variables. |
| Level || Type of regression variable: original for untransformed variables, group identifier for grouped variables, centring identifier for centred variables. || All variables. |
| Frequency || Periodicity of regression variable: biannual, quarterly or monthly. || All variables. |
| Period || Observation span. || All variables. |
| Pre-test || Test if regression variable has already been centred (see Section [Pre-test](./transformations#pretest)). || Original and grouped variables. |
| Timestamp || Time of data generation. || All variables. |
| Mean calculation span || Span chosen for the calculation of sample mean as given by centring identifier (see level). || Centred variables. |
| Sample mean || Value of the sample mean as given by centring identifier (see level). || Centred variables. |

<br/>
### Data input

To load a user-defined regression variable into the plug-in, either create and open an empty new TransReg document or open an existing document which may already contain some data. Then, drag and drop the regression variable from your data provider of choice into the data input field of the top banner of the TransReg document. Note that missing values are allowed and treated as being not a number (NaN). If the document already contains one or more regression variables with the same name (**MyRegVar**), then the name of the regression variable added most recently will be changed automatically to

$$ \text{MyRegVar} \rhd \text{Number},$$

where **Number** is a counter which works in exactly the same way as the counter of the TransReg documents.

This data input procedure also works for loading multiple regression variables simultaneously. For example, dragging and dropping an Excel sheet with $k$ user-defined regression variables from the spreadsheets provider into the data input field will input the $k$ variables in one step.

If a regression variable which has been loaded into a TransReg document is changed or updated in the external data source, it can be refreshed in the TransReg document by selecting **Refresh** after right-clicking on

$$ \text{Utilities} \rhd \text{TransReg} \rhd \text{MyTransReg}$$

in the **Workspace** window. In this case, all specified transformations will be recalculated automatically for the refreshed regression variable using the saved options.

### Specification panel

The specification panel shows up automatically at the right edge of the TransReg document as soon as a regression variable is selected in the data panel. It allows the user to carry out the transformations described in Section [Transformation](./transformations). In this regard, it should be noted that the basic principle of the plug-in is simultaneous rather than sequential performance of multiple transformations. Therefore, the following rules apply:

* For untransformed regression variables, the user has to specify all transformations which should be performed in a single specification panel. Once the **Calculate** button in the bottom line is pressed, the transformed regression variables obtained at the intermediate steps and the final stage are saved to the data panel in a tree-type structure.
* For transformed regression variables, the user cannot specify any further transformation. Still, the saved options used for obtaining the transformed variable are displayed in the specification panel.

As an example, assume a user-defined mother regression variable should be grouped into two daughter regression variables, each of which should be centred around period-specific sample means. Then, the two transformations (grouping, centring) have to be specified jointly since grouping the mother regression variable in a first step and centring the saved daughter regression variables in a second step will not work according the plug-in's basic principle.

### Data storage

In general, TransReg documents can be saved easily as part of the current workspace. In this case, however, the transformed regression variables are not available in JD+ for other purposes, such as seasonal adjustment. To remedy this situation, the transformed regression variables which should be generally available in JD+ could be copied to a variable list accessible under

$$ \text{Utilities} \rhd \text{Variables}$$

in the **Workspace** window. Note that this approach also enables exchange of transformed regression variables with users who did not install the TransReg plug-in to their JD+ environment.

To copy data from a TransReg document to a variables list, double-click on the transformed regression variable in the TransReg document which opens a new data window. Select **Chart** or **Grid** and proceed as follows:

* For **Chart**, click on any spot in the time series of the transformed regression variable and drag and drop it into the opened variables list.
* For **Grid**, click on the upper left corner of the table of the transformed regression variable and drag and drop it into the opened variables list.