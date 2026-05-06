<%*
const now = window.moment().locale("ru");
const year = now.format("YYYY");
const monthFolder = now.format("MM-MMMM");
const fileTitle = now.format("DD-MM-YYYY-dddd");
const dailyPath = `Time Garden/01 Daily/${year}/${monthFolder}/${fileTitle}.md`;

if (await tp.file.exists(dailyPath)) {
  await app.workspace.openLinkText(dailyPath, "", false);
}
%>