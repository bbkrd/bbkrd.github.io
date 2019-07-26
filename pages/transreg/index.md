---
layout: left-menu
title: Introduction
tagline: user documentation for TransReg using GitHub Pages
description: Introduction to TransReg
order: 0
---

Calendar effects play an important role in the seasonal adjustment of many German macroeconomic stock and flow series. For example, they account for as much as 1 percentage point of the quarterly rate of change in real gross domestic product. Depending on the economic sector and/or the economic activity, calendar effects can be constant or vary over the months or quarters. For orders received by industry, for example, one additional working day leads to an average increase by 3.1 % in each month. For output in industry, however, the average rise is not constant over the year. More precisely, one additional working day in the months January to November leads, on average, to an increase in output by 3.5 %, whereas the average rise is significantly smaller in December (2.3 %), since many firms reduce production around Christmas. A detailed discussion of working-day and other calendar effects in German macroeconomic time series, including further examples, is given by <cite>Deutsche Bundesbank 2012</cite>.

To estimate calendar effects, regARIMA and related time series regression models have proved to be effective. In this regard, calendar variables have to be centred in order to yield a meaningful estimate of the calendar component. As shown in Figure 1 for orders received by industry, usage of calendar variables which have not been centred is likely to result in a mismatch between the levels of the original and calendar (and seasonally) adjusted time series. For this reason, many seasonal adjustment programs, such as X-12-ARIMA, X-13ARIMA-SEATS and TRAMO/SEATS, automatically centre built-in calendar variables and provide options for doing the same with user-defined calendar variables. In JDemetra+ (JD+), however, the latter option is not available as user-defined variables are assumed to be loaded in centred form.

![Image](S3PR0297(engl).png)

The absence of a centring option in JD+ motivated the work on this plug-in. In particular, we believe that centring user-defined calendar variables outside JD+ and then loading the centred version into the program is neither comfortable nor sustainable. In addition, creating a centring plug-in opens up the possibility for implementing further transformations of user-defined regression variables which are currently not available in JD+ (and the seasonal adjustment programs mentioned above). A prime example is splitting a calendar variable into two or more period-specific variables which is necessary for estimating period-specific calendar effects, as in the case of output in industry.

### Overview

The TransReg plug-in allows the user to carry out grouping and centring of user-defined regression variables in JD+:

*  Grouping is the generation of a set of period-specific daughter regression variables from a mother regression variable. The user can assign the periods to the daughter regression variables.
*  Centring is the subtraction of the sample mean. The user can (1) choose between the overall sample mean and period-specific sample means and (2) specify the time span to be used for calculating the chosen type of sample mean.

To illustrate the two transformations, we consider the monthly number of working days in Germany as reported in Table [1](#table1). These figures account for both national and regional public holidays as the latter are counted as partial working days. This is a fundamental assumption of the working-day model which applies to a large number of German economic indicators and is described in more detail in *Deutsche Bundesbank 2012*.

<table class="table table-bordered" id="table1">
  <caption>Table 1: Monthly number of working days in Germany</caption>
  <thead>
    <tr>
      <th>Year</th>
      <th>Jan</th>
      <th>Feb</th>
      <th>Mar</th>
      <th>Apr</th>
      <th>May</th>
      <th>June</th>
      <th>July</th>
      <th>Aug</th>
      <th>Sep</th>
      <th>Oct</th>
      <th>Nov</th>
      <th>Dec</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>2011</td>
      <td>20.6</td>
      <td>20.0</td>
      <td>22.6</td>
      <td>19.0</td>
      <td>22.0</td>
      <td>19.3</td>
      <td>21.0</td>
      <td>22.8</td>
      <td>22.0</td>
      <td>19.9</td>
      <td>21.3</td>
      <td>21.0</td>
    </tr>
    <tr>
      <td>2012</td>
      <td>21.6</td>
      <td>20.6</td>
      <td>22.0</td>
      <td>19.0</td>
      <td>20.0</td>
      <td>20.3</td>
      <td>22.0</td>
      <td>22.8</td>
      <td>20.0</td>
      <td>21.9</td>
      <td>21.3</td>
      <td>17.0</td>
    </tr>
    <tr>
      <td>2013</td>
      <td>22.0</td>
      <td>19.6</td>
      <td>20.0</td>
      <td>21.0</td>
      <td>19.3</td>
      <td>20.0</td>
      <td>23.0</td>
      <td>21.8</td>
      <td>21.0</td>
      <td>21.9</td>
      <td>20.3</td>
      <td>18.0</td>
    </tr>
    <tr>
      <td>2014</td>
      <td>21.6</td>
      <td>20.0</td>
      <td>20.6</td>
      <td>20.0</td>
      <td>20.0</td>
      <td>19.3</td>
      <td>23.0</td>
      <td>20.8</td>
      <td>22.0</td>
      <td>21.9</td>
      <td>20.0</td>
      <td>19.0</td>
    </tr>
    <tr>
      <td>2015</td>
      <td>20.6</td>
      <td>19.6</td>
      <td>22.0</td>
      <td>20.0</td>
      <td>18.0</td>
      <td>21.3</td>
      <td>23.0</td>
      <td>21.0</td>
      <td>22.0</td>
      <td>22.0</td>
      <td>21.0</td>
      <td>20.0</td>
    </tr>
    <tr>
      <td>2016</td>
      <td>19.6</td>
      <td>20.6</td>
      <td>21.0</td>
      <td>21.0</td>
      <td>19.3</td>
      <td>22.0</td>
      <td>21.0</td>
      <td>22.8</td>
      <td>22.0</td>
      <td>19.9</td>
      <td>21.3</td>
      <td>21.0</td>
    </tr>
    <tr>
      <td>2017</td>
      <td>21.6</td>
      <td>19.6</td>
      <td>23.0</td>
      <td>18.0</td>
      <td>21.0</td>
      <td>20.3</td>
      <td>21.0</td>
      <td>22.8</td>
      <td>21.0</td>
      <td>20.0</td>
      <td>21.3</td>
      <td>19.0</td>
    </tr>
    <tr>
      <td>2018</td>
      <td>22.0</td>
      <td>19.6</td>
      <td>21.0</td>
      <td>20.0</td>
      <td>19.3</td>
      <td>21.0</td>
      <td>22.0</td>
      <td>22.8</td>
      <td>20.0</td>
      <td>21.9</td>
      <td>21.3</td>
      <td>17.0</td>
    </tr>
    <tr>
      <td>2019</td>
      <td>22.0</td>
      <td>20.0</td>
      <td>20.6</td>
      <td>20.0</td>
      <td>21.0</td>
      <td>18.3</td>
      <td>23.0</td>
      <td>21.8</td>
      <td>21.0</td>
      <td>21.9</td>
      <td>20.3</td>
      <td>18.0</td>
    </tr>
    <tr>
      <td>2020</td>
      <td>21.6</td>
      <td>19.6</td>
      <td>22.0</td>
      <td>20.0</td>
      <td>19.0</td>
      <td>20.3</td>
      <td>23.0</td>
      <td>21.0</td>
      <td>22.0</td>
      <td>22.0</td>
      <td>21.0</td>
      <td>20.0</td>
    </tr>
  </tbody>
</table>

### Installation

Download the latest installation file from [the plug-in's GitHub repository](https://github.com/bbkrd/TransReg/releases) and save it to your local folder of choice. Choose
 
$$ \text{Tools}  \rhd  \text{Plugins} $$

from the JD+ drop down menu, open the **Downloaded** sheet and press the **Add Plugins** button. Select the local copy of the installation file, click the **Install** button and accept the terms in the licence agreements. Once the installation is finished, TransReg documents and a global option menu are available. Note that the plug-in is automatically activated and, therefore, a restart of JD+ is not necessary.

The remainder of this manual is organised as follows:

*  Section [TransReg document](./transregdocument) describes the basic structure of the TransReg document as well as data input and storage.
*  Section [Transformation](./transformations) explains how the available transformations can be carried out in the specification panel of the TransReg document.
*  Finally, Section [Global Options](./globaloptions) addresses the global options available for customising the plug-in according to the user's preferences.