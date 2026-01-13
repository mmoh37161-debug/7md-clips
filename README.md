{
	"folders": [
		{
			"path": "."
		}
	],
	"settings": {
		"liveServer.settings.multiRootWorkspaceName": "test"
	}
}
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8" />
  <title>لقطات خاصة بالمحترف 7MD</title>
  <style>
    body {font-family: Tahoma, Arial, sans-serif; background:#373737; margin:0;}
    header {background:#111; color:#eeeeee; padding:15px 30px; display:flex; align-items:center; gap:15px;}
    header img {width:50px; height:50px; object-fit:contain;}
    header h1 {font-size:20px; margin:0;}
    .container {max-width:1100px; margin:30px auto; padding:0 15px; display:grid; grid-template-columns:repeat(auto-fill,minmax(280px,1fr)); gap:20px;}
    .card {background:#111111; border-radius:10px; box-shadow:0 4px 10px rgba(0,0,0,.1); overflow:hidden;}
    video {width:100%; height:200px; object-fit:cover;}
    .content {padding:15px;}
    .actions {display:flex; gap:10px;}
    .btn {flex:1; text-align:center; padding:10px; background:#590202; color:#fff; text-decoration:none; border-radius:6px; font-size:14px;}
    .btn.download {background:#541a1a;}
    footer {text-align:center; padding:20px; color:#9f9e9e;}
  </style>
</head>
<body>

<header>
  <img src="logo.png/i.jpg" alt="Logo">
  <h1>لقطات خاصة بالمحترف 7MD</h1>
</header>

<section class="container" id="clipsContainer"></section>

<footer>© 2026 | لقطات خاصة بالمحترف 7MD</footer>

<script>
/*
  ملاحظة مهمة:
  هذا الكود يعمل تلقائي فقط إذا كان الموقع مرفوع على استضافة
  (وليس فتح الملف مباشرة من الكمبيوتر)
*/

fetch('clips/clips.json')
  .then(res => res.json())
  .then(data => {
    const container = document.getElementById('clipsContainer');
    data.forEach(clip => {
      container.innerHTML += `
        <div class="card">
          <video src="clips/${clip.file}" controls></video>
          <div class="content">
            <h3>${clip.title}</h3>
            <div class="actions">
              <a class="btn" href="clips/${clip.file}" target="_blank">مشاهدة</a>
              <a class="btn download" href="clips/${clip.file}" download>تحميل</a>
            </div>
          </div>
        </div>`;
    });
  });
</script>

</body>
</html>
