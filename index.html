<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Smart Notes AI</title>

<link href="https://fonts.googleapis.com/css2?family=Amiri:wght@400;700&family=Tajawal:wght@300;400;500;700;900&display=swap" rel="stylesheet">

<style>
:root{
  --paper:#faf6ed;
  --ink:#1e1208;
  --gold:#f5c518;
  --bg:#0d0a1a;
  --card:#1a1530;
  --text:#e8e0ff;
}

*{margin:0;padding:0;box-sizing:border-box;}

body{
  font-family:'Tajawal',sans-serif;
  background:var(--bg);
  color:var(--text);
}

#form-page{
  max-width:520px;
  margin:auto;
  padding:20px;
}

.card{
  background:var(--card);
  padding:16px;
  border-radius:12px;
  margin-bottom:14px;
}

input,textarea{
  width:100%;
  padding:10px;
  margin-top:8px;
  border-radius:8px;
  border:1px solid #333;
  background:#111;
  color:#fff;
}

button{
  width:100%;
  padding:14px;
  background:var(--gold);
  border:none;
  font-weight:bold;
  border-radius:10px;
  margin-top:10px;
}

#result-page{
  display:none;
  background:var(--paper);
  color:var(--ink);
  width:100vw;
  min-height:100vh;
}

.book{
  width:100vw;
  min-height:100vh;
  background:#fffdf6;
  padding:20px;
}

.main-title{
  font-size:1.8rem;
  text-align:center;
  margin-bottom:20px;
}

.h2{font-size:1.7rem;border-right:3px solid #8a6a3a;padding-right:10px;margin:10px 0;}
.h3{font-size:1rem;margin:8px 0;}
.h3.ar-num{font-size:1.3rem;border-right:3px solid #a88b55;padding-right:10px;}
.p{font-size:0.9rem;line-height:2;}

.loading{
  display:none;
  text-align:center;
  padding:40px;
}

#saved-page{
  display:none;
  padding:20px;
}

.saved-card{
  background:var(--card);
  padding:15px;
  margin-bottom:10px;
  border-radius:10px;
}
</style>
</head>

<body>

<!-- FORM -->
<div id="form-page">
  <div class="card">
    <h3>📌 بيانات النص</h3>
    <input id="title" placeholder="عنوان المادة">
    <textarea id="text" placeholder="اكتب النص هنا..."></textarea>
  </div>

  <button onclick="start()">ابدأ المعالجة</button>
  <button onclick="showSaved()">📚 المحتويات المحفوظة</button>
</div>

<div id="loading" class="loading">⏳ جاري المعالجة...</div>

<div id="result-page">
  <div class="book" id="output"></div>
</div>

<div id="saved-page">
  <div class="book">
    <h2 class="main-title">📚 المحفوظات</h2>
    <div id="saved-list"></div>
    <button onclick="backHome()">رجوع</button>
  </div>
</div>

<script>

function detectType(line){
  line=line.trim();
  if(/^\d+\./.test(line)) return "h2";
  if(/^[\u0660-\u0669]+\./.test(line)) return "ar";
  if(line.length<60) return "h3";
  return "p";
}

function render(text){
  return text.split("\n").map(line=>{
    if(!line.trim()) return "";
    let t=detectType(line);
    if(t==="h2") return `<div class="h2">${line}</div>`;
    if(t==="ar") return `<div class="h3 ar-num">${line}</div>`;
    if(t==="h3") return `<div class="h3">${line}</div>`;
    return `<div class="p">${line}</div>`;
  }).join("");
}

/* ✅ عرض الناتج من المعالجة */
function start(){

  let text=document.getElementById("text").value;
  let title=document.getElementById("title").value;

  if(!text){alert("اكتب النص");return;}

  document.getElementById("form-page").style.display="none";
  document.getElementById("loading").style.display="block";

  let processed=text;
  saveContent(title,processed);

  setTimeout(()=>{

    document.getElementById("loading").style.display="none";
    document.getElementById("result-page").style.display="block";

    document.getElementById("output").innerHTML =
      `<div class="main-title">${title}</div>`+
      render(processed)+
      `<button onclick="backHome()" 
        style="
          margin-top:25px;
          background:#4caf50;
          color:#fff;
          border:none;
          padding:14px;
          border-radius:10px;
          width:100%;
          font-weight:bold;
        ">
        🔙 الرجوع إلى صفحة معالجة النصوص
      </button>`;

  },800);
}

function saveContent(title,text){
  let saved=JSON.parse(localStorage.getItem("smartNotesSaved")||"[]");
  saved.unshift({
    id:Date.now(),
    title:title||"بدون عنوان",
    text,
    date:new Date().toLocaleDateString("ar-EG")
  });
  localStorage.setItem("smartNotesSaved",JSON.stringify(saved));
}

function showSaved(){

  document.getElementById("form-page").style.display="none";
  document.getElementById("result-page").style.display="none";
  document.getElementById("saved-page").style.display="block";

  let saved=JSON.parse(localStorage.getItem("smartNotesSaved")||"[]");

  let html="";
  if(saved.length===0) html="<div class='saved-card'>لا يوجد</div>";

  saved.forEach(item=>{
    html+=`
      <div class="saved-card">
        <h3>${item.title}</h3>
        <button onclick="openSaved(${item.id})">فتح</button>
        <button onclick="deleteSaved(${item.id})">حذف</button>
      </div>
    `;
  });

  document.getElementById("saved-list").innerHTML=html;
}

/* ✅ فتح المحتوى المحفوظ + زر تحت النص */
function openSaved(id){

  let saved=JSON.parse(localStorage.getItem("smartNotesSaved")||"[]");
  let item=saved.find(x=>x.id===id);
  if(!item) return;

  document.getElementById("saved-page").style.display="none";
  document.getElementById("result-page").style.display="block";

  document.getElementById("output").innerHTML =
    `<div class="main-title">${item.title}</div>`+
    render(item.text)+
    `<button onclick="backHome()" 
      style="
        margin-top:25px;
        background:#4caf50;
        color:#fff;
        border:none;
        padding:14px;
        border-radius:10px;
        width:100%;
        font-weight:bold;
      ">
      🔙 الرجوع إلى صفحة معالجة النصوص
    </button>`;
}

function deleteSaved(id){
  let saved=JSON.parse(localStorage.getItem("smartNotesSaved")||"[]");
  saved=saved.filter(x=>x.id!==id);
  localStorage.setItem("smartNotesSaved",JSON.stringify(saved));
  showSaved();
}

function backHome(){
  document.getElementById("saved-page").style.display="none";
  document.getElementById("result-page").style.display="none";
  document.getElementById("loading").style.display="none";
  document.getElementById("form-page").style.display="block";
}

</script>

</body>
</html>