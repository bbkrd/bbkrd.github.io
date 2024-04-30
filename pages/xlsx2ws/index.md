---
layout: left-menu
title: Introduction
tagline: user documentation for Xlsx2Ws using GitHub Pages
description: Xlsx2Ws Introduction
order: 0
---

Xlsx2Ws reads xlsx files and creates JD+ workspaces.
To do so there are some conventions to follow. The first row has to contain the headers of information.

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
   <td>Name of the saitem (<b>mandatory and unique</b>)</td>
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

To specify additional information add headers starting with "p[rov]\_"(provider), "s[pec]\_"(specification) or "m[eta]\_"(metadata). More detailed information on implemented headers can be found in the navigation on the left. Everything not specified is not implemented at the moment e.g. TRAMO/SEATS.

The name of the saitem in the workspace has to be given manually by the user or with a plug-in.

To use the features go to File and choose from these actions:

<table class="table table-bordered" id="actions">
 <thead>
  <tr>
   <th>Name</th>
   <th>Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td>Create new Workspace from Xlsx file</td>
   <td>Creates a new workspace from a xlsx file. The information providername and specificationname are mandatory for this action!</td>
  </tr>
  <tr>
   <td>Import from Xlsx file</td>
   <td>Import the information from a xlsx file to the current workspace, overriding existing items if necessary</td>
  </tr>
  <tr>
   <td>Export to Xlsx file</td>
   <td>Opens a dialog to export the current workspace to xlsx</td>
  </tr>
 </tbody>
</table>

