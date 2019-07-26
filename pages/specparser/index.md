---
layout: left-menu
title: Introduction
tagline: user Documentation for SpecParser using GitHub Pages
description: Introduction to SpecParser
order: 0
---

#### Overview of the plug-in
The SpecParser is a plug-in in JD+ that facilitates the automatic specification translation for the migration from X-12ARIMA to JDemetra+ (JD+).
This can be conducted using the following modes:

**Single mode** | Translation of a single spc-file to an x13-document 

**Multi mode** | Translation of an input metafile (mta-file) referring to multiple spc-files 

<br/>
#### Constraints

**Correctness of files**                  |  The plug-in does not test whether the contents specified in the input file is correct or valid.
**File extensions of specification files**  |   Only specification files ending with .spc are supported. Meta-files ending with .mta are supported, but the referenced files have to end with .spc.

<br/>
#### Differences to X-12ARIMA

**Separator for spec arguments**  |  In spc files for X-12ARIMA it is possible to have more than one argument in one line separated by a blank. The SpecParser accepts just one argument in a line.

<br/>
#### Installing and navigating to the plug-in

To install the SpecParser plug-in navigate to $ \text{Tools} \rhd \text{Plugins}$ in the drop down menu.
For detailed information see the "JDemetra+ Reference Manual".
Once the SpecParser plug-in has been successfully installed, a new button **Open SpecParser** becomes available when right-clicking on an x13- or a multi-document.

#### How to use this guide

This guide is split into two sections, a quick start guide and a function guide.

**Quick start**     |   Provides a brief overview how to use the plug-in.
**Function guide**  |   Provides a detailed description of the plug-in.

