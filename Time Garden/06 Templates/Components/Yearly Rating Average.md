```tracker
searchType: frontmatter
searchTarget: dayRating
dateFormat: DD-MM-YYYY-dddd
datasetName: yearRating
startDate: <% moment(tp.file.title, 'YYYY').startOf('year').locale('ru').format("DD-MM-YYYY-dddd") %>
endDate: <% moment(tp.file.title, 'YYYY').endOf('year').locale('ru').format("DD-MM-YYYY-dddd") %>
summary:
    template: "Average Rating: {{average()}}" 
```