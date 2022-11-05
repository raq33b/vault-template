<%* let title = tp.file.title
  if (title.startsWith("Untitled")) {
    title = await tp.system.prompt("Title");
    await tp.file.rename(title);
  } 
-%>
<%*
  let result = title.replace(/\b\w/g, c => c.toUpperCase());
  tR += "---"
%>
title: '<% tp.file.title %>'
category: '<% tp.file.creation_date("YYYY") %>'
tags:
  - books
created: <% moment(tp.file.creation_date("YYYY-MM-DDTHH:mm:ss.SSSZ")).toISOString() %>
updated: <% moment(tp.file.last_modified_date("YYYY-MM-DDTHH:mm:ss.SSSZ")).toISOString() %>
---

Title:: <% await tp.system.prompt("What is the actual book title?") %>
Topics:: <% await tp.system.prompt("Enter backlinks to topics") %>
By::  <% await tp.system.prompt("Who are the authors") %>
Related::  <% await tp.system.prompt("Any related backlinks?") %>

---