```tracker
searchType: frontmatter
searchTarget: dayRating
dateFormat: DD-MM-YYYY-dddd
datasetName: dayRating
startDate: <%moment(tp.file.title, 'YYYY-[W]ww').add(1, 'days').locale('ru').format("DD-MM-YYYY-dddd") %>
endDate: <% moment(tp.file.title, 'YYYY-[W]ww').add(1, 'weeks').locale('ru').format("DD-MM-YYYY-dddd") %>
summary:
    template: "Average Rating: {{average()}}" 
```