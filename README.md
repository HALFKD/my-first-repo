<!DOCTYPE html>
<html>
    <head>
    <meta charset="UTF-8">
    <title>自己紹介</title>
    <style>
    body {
        background: #fff;
        color: #fff;
        font-family: sans-serif;
        margin: 0;
        padding: 0;
    }
    .container {
        display: flex;
        justify-content: center;
        gap: 40px;
        margin-top: 60px;
    }
    .card {
        background: #fff;
        color: black;
        border-radius: 16px;
        box-shadow: 0 4px 16px #0002;
        padding: 32px 40px 40px 40px;
        min-width: 340px;
        text-align: center;
    }
    .title {
        font-size: 2em;
        font-weight: bold;
        margin-bottom: 16px;
    }
    .desc {
        font-size: 1.1em;
        margin-bottom: 32px;
    }
    .switch-btn {
        background: #4285f4;
        color: #fff;
        border: none;
        border-radius: 24px;
        padding: 12px 32px;
        font-size: 1em;
        cursor: pointer;
        transition: background 0.2s;
    }
    .switch-btn:hover {
        background: #3367d6;
    }
    </style>
</head>
<body>
<div class="container">
    <div class="card" id="jp-card" style="display:none;">
        <div class="title">自己紹介</div>
        <div class="desc">
            こんにちは！私の名前は晴です。<br>
            BotWでキャラクターのお尻を振って高速移動するのが好きです
        </div>
        <button class="switch-btn" onclick="switchLang('en')">Switch to English</button>
        </div>
        <div class="card" id="en-card" style="display:none;">
        <div class="title">About Me</div>
        <div class="desc">
            Hello! My name is Hal.<br>
            I like to shake my character's butt in BotW to move fast!.
        </div>
        <button class="switch-btn" onclick="switchLang('jp')">日本語に切り替える</button>
    </div>
    </div>
    <script>
    function getLang() {
        const params = new URLSearchParams(location.search);
        const lang = params.get('language') || params.get('language') || 'jp';
        if (lang === 'en') return 'en';
        return 'jp';
    }
    function showCard(lang) {
        document.getElementById('jp-card').style.display = (lang === 'jp') ? 'block' : 'none';
        document.getElementById('en-card').style.display = (lang === 'en') ? 'block' : 'none';
    }
    function switchLang(lang) {
        location.href = location.pathname + '?language=' + lang;
    }
    showCard(getLang());
    </script>
    </body>
</html>
