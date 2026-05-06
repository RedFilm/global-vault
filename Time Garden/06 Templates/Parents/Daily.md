<%"---"%>
<%*
tR += await tp.file.include("[[Daily Banner Config]]"); 
%>

<%* tR+= "cssclasses:"%>
  - <%"image-borders"%>
  - image-small
  - <%"timegarden-daily"%>
  <%* 
    tR += "- " + moment(tp.file.title, 'DD-MM-YYYY-dddd', 'ru').locale('ru').format('dddd').toLowerCase()
    tR += "\n  - daily"
    %> 

date: <% moment(tp.file.title, 'DD-MM-YYYY-dddd', 'ru').format("YYYY-MM-DD") %>

alias: 
dayRating: 1
tags: "#type/daily-note"

journal: daily
journal-date: <% moment(tp.file.title, 'DD-MM-YYYY-dddd', 'ru').format('YYYY-MM-DD') %>
journal-start-date: <% moment(tp.file.title, 'DD-MM-YYYY-dddd', 'ru').format('YYYY-MM-DD') %>
journal-end-date: <% moment(tp.file.title, 'DD-MM-YYYY-dddd', 'ru').format('YYYY-MM-DD') %>

aiAnswer: ""
<%"---"%>
# ✧ <% moment(tp.file.title, 'DD-MM-YYYY-dddd', 'ru').locale('ru').format("dddd, DD MMMM YYYY") %>
[[<% // create hidden link to weekly note for graph view

moment(tp.file.title, 'DD-MM-YYYY-dddd', 'ru').format('YYYY-[W]WW') %>|]]
<%*
// create navbar
tR += await tp.file.include("[[Daily MetaBindNavBar]]");
%>

<%*
// create input field for alias
tR += await tp.file.include("[[Daily MetaBindAlias]]");
%>
---
- <% tp.file.cursor(0) %>