```tracker
searchType: frontmatter
searchTarget: dayRating
dateFormat: DD-MM-YYYY-dddd
datasetName: dayRating
startDate: <% moment(tp.file.title, 'YYYY-MM-MMMM', 'ru').startOf('month').locale('ru').format("DD-MM-YYYY-dddd") %>
endDate: <% moment(tp.file.title, 'YYYY-MM-MMMM', 'ru').endOf('month').locale('ru').format("DD-MM-YYYY-dddd") %>
summary:
    template: "Average Rating: {{average()}}" 
```