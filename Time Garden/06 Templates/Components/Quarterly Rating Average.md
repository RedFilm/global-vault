```tracker
searchType: frontmatter
searchTarget: dayRating
dateFormat: DD-MM-YYYY-dddd
datasetName: monthRating
startDate: <% moment(tp.file.title, 'YYYY-[Q]Q', 'ru').startOf('quarter').locale('ru').format("DD-MM-YYYY-dddd") %>
endDate: <% moment(tp.file.title, 'YYYY-[Q]Q', 'ru').endOf('quarter').locale('ru').format("DD-MM-YYYY-dddd") %>
summary:
    template: "Average Rating: {{average()}}" 
```