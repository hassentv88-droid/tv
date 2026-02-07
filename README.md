<!DOCTYPE html>
<html lang="ar">
<head>
<meta charset="UTF-8">
<title>Video Player</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<style>
  body, html {
    margin: 0;
    padding: 0;
    height: 100%;
    background: black;
  }

  .video-container {
    position: relative;
    width: 100%;
    height: 100%;
    overflow: hidden;
  }

  iframe {
    width: 100%;
    height: 100%;
    border: none;
  }

  /* الغطاء الأسود العلوي */
  .top-cover {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 90px; /* تنجم تغيّر حسب الغطاء اللي تحب */
    background: black;
    z-index: 9999;
    pointer-events: all; /* يمنع الضغط على أي شي تحت */
  }
</style>
</head>
<body>

<div class="video-container">
  <!-- فيديو MEGA -->
  <iframe 
    src="https://mega.nz/embed/wAN12QRA#GWWaFqngpIhYuFPd5IwlGt-5ERR20f67XnRQhqPYBu8" 
    allowfullscreen
    allow="autoplay">
  </iframe>

  <!-- الغطاء الأسود -->
  <div class="top-cover"></div>
</div>

</body>
</html>
