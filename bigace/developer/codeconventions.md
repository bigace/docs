# Code conventions

{{page>wiki:templates:incomplete}}

This page describes basic code formattings rules and coding conventions used in the  Bigace development lifecycle.

## Closing PHP tags

Do **not** use closing PHP tags before the end of a file. Even if some PHP coder consider a missing closing tag ?> at the end of a file a broken syntax, it is used throughout several big frameworks and best practice in many projects. 

Bigace does not include any closing PHP tag in its source files, as it can lead to the well know "Cannot send headers, already sended in ..." problem.
