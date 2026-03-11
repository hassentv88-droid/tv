
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>حكاية الزواج</title>
<style>
body {
    margin:0;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background: linear-gradient(to bottom, #0a0a0a, #1a1a1a);
    color: white;
    transition: background 0.3s;
}

.container {
    width: 100%;
    max-width: 480px;
    margin: auto;
    transition: all 0.3s;
}

.header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 12px 15px;
    background: linear-gradient(to bottom, rgba(0,0,0,0.95), transparent);
    position: sticky;
    top: 0;
    z-index: 10;
    box-shadow: 0 5px 10px rgba(0,0,0,0.5);
    border-bottom-left-radius: 15px;
    border-bottom-right-radius: 15px;
}

.header div {
    font-size: 24px;
    cursor: pointer;
    transition: transform 0.2s;
}

.header div:hover {
    transform: scale(1.2);
}

.poster-container {
    width: 100%;
    height: 250px;
    margin-bottom: 10px;
    border-radius: 15px;
    overflow: hidden;
    box-shadow: 0 10px 20px rgba(0,0,0,0.6);
}

.poster-container img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    transition: transform 0.3s;
}

.poster-container img:hover {
    transform: scale(1.05);
}

.details {
    padding: 15px;
}

.title {
    font-size: 22px;
    font-weight: bold;
    margin-bottom: 8px;
    text-shadow: 1px 1px 5px rgba(0,0,0,0.7);
}

.description {
    font-size: 14px;
    color: #ccc;
    line-height: 1.5;
}

.episodes-list {
    padding: 15px;
}

.episode-item {
    display: flex;
    align-items: center;
    background: #1a1a1a;
    padding: 10px;
    border-radius: 12px;
    margin-bottom: 12px;
    cursor: pointer;
    transition: 0.3s;
    box-shadow: 0 4px 8px rgba(0,0,0,0.4);
}

.episode-item:hover {
    background: #2a2a2a;
    transform: translateX(5px);
    box-shadow: 0 6px 12px rgba(0,0,0,0.6);
}

.episode-thumb img {
    width: 90px;
    height: 55px;
    object-fit: cover;
    border-radius: 8px;
    margin-left: 12px;
    transition: transform 0.3s;
}

.episode-thumb img:hover {
    transform: scale(1.05);
}

.episode-info {
    flex: 1;
}

.episode-name {
    font-size: 14px;
    color: #fff;
}

.video-player-container {
    width: 100%;
    position: relative;
    padding-top: 56.25%; /* 16:9 ratio */
    margin-bottom: 15px;
    box-shadow: 0 10px 20px rgba(0,0,0,0.6);
    border-radius: 15px;
}

.video-player-container iframe {
    position: absolute;
    top:0;
    left:0;
    width:100%;
    height:100%;
    border-radius: 15px;
}

.hidden { display: none; }

</style>
</head>
<body>

<div class="container">

    <!-- الواجهة الأولى -->
    <div id="homeView">
        <div class="header">
            <div>✕</div>
            <div>🔍</div>
        </div>

        <div class="poster-container">
            <img src="https://i.supaimg.com/9d110cce-8a32-4520-9cc3-6d47949cddc8/72fee475-6b22-4cd1-b4c6-d4412ede1afd.jpg" alt="حكاية الزواج">
        </div>

        <div class="details">
            <div class="title">حكاية الزواج</div>
            <div class="description">
                دراما تركية تحكي قصة مجموعة من المحاميات المتخصصات في قضايا الطلاق
                والعلاقات الزوجية وكيف تتغير حياتهم بين الحب والعمل والمشاكل العائلية.
            </div>
        </div>

        <div class="episodes-list">
            <div class="episode-item" onclick="openEpisode('1172572110')">
                <div class="episode-thumb">
                    <img src="https://i.supaimg.com/9d110cce-8a32-4520-9cc3-6d47949cddc8/a225bb7c-f64f-4a22-89f2-7aae949304b0.jpg" alt="الحلقة 1">
                </div>
                <div class="episode-info">
                    <span class="episode-name">الحلقة 1</span>
                </div>
            </div>
        </div>
    </div>

    <!-- الواجهة الثانية (مشغل الفيديو + قائمة الحلقات) -->
    <div id="episodeView" class="hidden">
        <div class="header">
            <div onclick="backHome()">←</div>
            <div>🔍</div>
        </div>

        <div class="video-player-container">
            <iframe id="videoPlayer" src="" frameborder="0" allow="autoplay; fullscreen; picture-in-picture; clipboard-write; encrypted-media; web-share" referrerpolicy="strict-origin-when-cross-origin" title="الحلقة"></iframe>
        </div>

        <div class="episodes-list">
            <div class="episode-item" onclick="playEpisode('1172572110')">
                <div class="episode-thumb">
                    <img src="https://i.supaimg.com/9d110cce-8a32-4520-9cc3-6d47949cddc8/a225bb7c-f64f-4a22-89f2-7aae949304b0.jpg" alt="الحلقة 1">
                </div>
                <div class="episode-info">
                    <span class="episode-name">الحلقة 1</span>
                </div>
            </div>
        </div>
    </div>

</div>

<script src="https://player.vimeo.com/api/player.js"></script>
<script>
function openEpisode(vimeoID){
    document.getElementById('homeView').classList.add('hidden');
    document.getElementById('episodeView').classList.remove('hidden');
    playEpisode(vimeoID);
}

function backHome(){
    document.getElementById('episodeView').classList.add('hidden');
    document.getElementById('homeView').classList.remove('hidden');
}

function playEpisode(vimeoID){
    document.getElementById('videoPlayer').src = "https://player.vimeo.com/video/" + vimeoID + "?badge=0&autopause=0&player_id=0&app_id=58479";
}
</script>

</body>
</html>
