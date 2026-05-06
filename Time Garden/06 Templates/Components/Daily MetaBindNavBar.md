`BUTTON[prev-day, current-week, next-day]`
```meta-bind-button
id: prev-day
class: phone-responsive
style: primary
label: ← Yesterday
hidden: true
actions:
  - type: templaterCreateNote
    templateFile: "<%* tR += window?.timeGarden?.rootPath.substring(1); _%>06 Templates/Parents/Daily.md"
    folderPath: "<%* tR += window?.timeGarden?.rootPath.substring(1); _%>01 Daily/<%* tR += moment(tp.file.title, 'DD-MM-YYYY-dddd', 'ru').subtract(1, 'd').locale('ru').format('YYYY/MM-MMMM'); _%>"
    fileName: "<%* tR += moment(tp.file.title, 'DD-MM-YYYY-dddd', 'ru').subtract(1, 'd').locale('ru').format('DD-MM-YYYY-dddd'); _%>"
    openIfAlreadyExists: true
    openNote: true
```
```meta-bind-button
id: current-week 
style: primary
class: phone-responsive
label: This Week
hidden: true
actions:
  - type: open
    link: "[[<%* tR += window?.timeGarden?.rootPath; _%>02 Weekly/<% fileDate = moment(tp.file.title, 'DD-MM-YYYY-dddd', 'ru').format('YYYY/YYYY-[W]WW') %>]]"
    newTab: false
```
```meta-bind-button
id: next-day
style: primary
class: phone-responsive
label: Tomorrow →
hidden: true
actions:
  - type: templaterCreateNote
    templateFile: "<%* tR += window?.timeGarden?.rootPath.substring(1); _%>06 Templates/Parents/Daily.md"
    folderPath: "<%* tR += window?.timeGarden?.rootPath.substring(1); _%>01 Daily/<%* tR += moment(tp.file.title, 'DD-MM-YYYY-dddd', 'ru').add(1, 'd').locale('ru').format('YYYY/MM-MMMM'); _%>"
    fileName: "<%* tR += moment(tp.file.title, 'DD-MM-YYYY-dddd', 'ru').add(1, 'd').locale('ru').format('DD-MM-YYYY-dddd'); _%>"
    openIfAlreadyExists: true
    openNote: true
```