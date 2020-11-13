---
layout: left-menu
title: Introduction
tagline: user documentation for Xlsx2Ws using GitHub Pages
description: Xlsx2Ws Introduction
order: 0
---

Xlsx2Ws reads xlsx files and creates JD+ workspaces. To do so there are some conventions to follow.
The first row has to contain the headers of information.

<table class="table table-bordered" id="headers">
 <thead>
  <tr>
   <th>Header</th>
   <th>Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td>multidoc</td>
   <td>Name of the multidocument</td>
  </tr>
  <tr>
   <td>saitem</td>
   <td>Name of the saitem (necessary)</td>
  </tr>
  <tr>
   <td>providername</td>
   <td>Name of the provider e.g. EXCEL</td>
  </tr>
  <tr>
   <td>specificationname</td>
   <td>Name of the specification e.g. X13</td>
  </tr>
 </tbody>
</table>

To specify additional information add headers starting with "p_"(provider), "s_"(spec) or "m_"(metadata). More detailed information on implemented headers can be found in the navigation on the left.