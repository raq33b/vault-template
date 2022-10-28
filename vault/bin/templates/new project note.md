---
title: '<% tp.file.title %>'
category: '<% tp.file.creation_date("YYYY") %>'
tags:
  - projects
created: <% moment(tp.file.creation_date("YYYY-MM-DDTHH:mm:ss.SSSZ")).toISOString() %>
updated: <% moment(tp.file.last_modified_date("YYYY-MM-DDTHH:mm:ss.SSSZ")).toISOString() %>
---
