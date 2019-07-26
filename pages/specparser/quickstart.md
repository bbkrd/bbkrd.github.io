---
layout: left-menu
title: Quick start
tagline: user Documentation for SpecParser using GitHub Pages
description: Quick start
order: 10
---

The general usage of the SpecParser is identical for both modes.  
However they serve different purposes. 
Choose an x13-document to translate a single spc-file to the JD$+$ workspace.
Choose a multi-document to translate an mta-file with various spc-files.

#### Steps

1. Right-click on the document in the JD$+$ workspace window and push the button **Open SpecParser** in the context menu.
2. An empty SpecParser window opens. (The windows differ slightly for single and multi mode.)
3. Click the button **Load ...** on the top to open the file manager. Navigate to the respective document to be translated (.spc or .mta).
4. The translation starts automatically. The progress can be seen at the bottom.
5. After the SpecParser has completed the translation the message *Translation completed* is prompted.
6. In the SpecParser window the translated specification is on the right hand side and a translation report at the bottom.
7. The results are stored in the chosen document of the JD+ workspace. Regression variables are stored in $\text{Utilities} \rhd \text{Variables} \rhd \text{reg\_SpecParser}$ in the respective workspace. 
