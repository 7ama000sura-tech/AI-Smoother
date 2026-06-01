<!DOCTYPE html>
<html lang="ku" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>LOVE</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            background-color: #fbc4cd; /* ڕەنگی پەمەیی وەک ڤیدیۆکە */
            font-family: 'Tahoma', sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            overflow: hidden;
        }

        /* سندوقی کلاسیکی خۆڵەمێشی ویندۆز ٩٨ */
        .window {
            background-color: #d6d6d6;
            border-top: 3px solid #fff;
            border-left: 3px solid #fff;
            border-right: 3px solid #555;
            border-bottom: 3px solid #555;
            width: 320px;
            box-shadow: 2px 2px 10px rgba(0,0,0,0.2);
            position: relative;
            z-index: 10;
        }

        /* شریتی سەرەوە */
        .title-bar {
            background: linear-gradient(90deg, #f05a7e, #fbc4cd);
            padding: 4px 8px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            color: white;
            font-weight: bold;
            font-size: 14px;
        }

        .title-bar-controls button {
            background-color: #d6d6d6;
            border-top: 1px solid #fff;
            border-left: 1px solid #fff;
            border-right: 1px solid #555;
            border-bottom: 1px solid #555;
            width: 16px;
            height: 14px;
            font-size: 9px;
            display: flex;
            justify-content: center;
            align-items: center;
            cursor: pointer;
        }

        .window-body {
            padding: 25px;
            text-align: center;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        /* ستایلی وێنەی پشیلە جوڵاوەکە */
        .cat-gif {
            width: 120px;
            height: 120px;
            margin-bottom: 15px;
            object-fit: contain;
        }

        h2 {
            color: #000;
            font-size: 18px;
            margin: 0 0 20px 0;
            font-weight: bold;
        }

        .buttons {
            display: flex;
            justify-content: center;
            gap: 40px;
            margin-top: 15px;
            height: 40px;
            width: 100%;
        }

        .btn {
            padding: 6px 25px;
            font-size: 15px;
            font-weight: bold;
            font-family: 'Tahoma', sans-serif;
            border-top: 2px solid #fff;
            border-left: 2px solid #fff;
            border-right: 2px solid #555;
            border-bottom: 2px solid #555;
            background-color: #d6d6d6;
            cursor: pointer;
            outline: none;
        }

        .btn:active {
            border-top: 2px solid #555;
            border-left: 2px solid #555;
            border-right: 2px solid #fff;
            border-bottom: 2px solid #fff;
        }

        .yes-btn {
            color: #2b8a3e;
        }

        /* دوگمەی نەخێر لێرەدا فێکس کراوە بۆ ئەوەی ڕاکات و ون نەبێت */
        .no-btn {
            color: #c92a2a;
            position: fixed;
            z-index: 999;
        }

        /* ئەنیمەیشنی بارانی دڵەکان */
        .heart-rain {
            position: fixed;
            top: -20px;
            animation: fall linear forwards;
            opacity: 0.7;
            z-index: 1;
            user-select: none;
            pointer-events: none;
        }

        @keyframes fall {
            to { transform: translateY(105vh); }
        }
    </style>
</head>
<body>

    <div class="window" id="mainCard">
        <div class="title-bar">
            <div class="title-text">LOVE</div>
            <div class="title-bar-controls">
                <button>X</button>
            </div>
        </div>
        <div class="window-body">
            <img class="cat-gif" id="catImg" src="https://i.postimg.co/ydXg9m9g/cat-cute.gif" alt="Cat">
            
            <h2>دەبیت بە خۆشەویستم؟</h2>
            
            <div class="buttons">
                <button class="btn yes-btn" onclick="sayYes()">بەڵێ</button>
                <button class="btn no-btn" id="noBtn" onmouseover="moveButton()" onclick="moveButton()">نەخێر</button>
            </div>
        </div>
    </div>

    <script>
        const noBtn = document.getElementById('noBtn');

        // ڕێکخستنی شوێنی سەرەتایی دوگمەی نەخێر لە تەنیشت بەڵێ
        function initButton() {
            const yesBtn = document.querySelector('.yes-btn');
            const rect = yesBtn.getBoundingClientRect();
            noBtn.style.left = (rect.right + 40) + 'px';
            noBtn.style.top = rect.top + 'px';
        }
        
        window.onload = initButton;
        window.onresize = initButton;

        // فەنکشنی بازدانی دوگمەی نەخێر
        function moveButton() {
            const x = Math.random() * (window.innerWidth - noBtn.offsetWidth - 50) + 25;
            const y = Math.random() * (window.innerHeight - noBtn.offsetHeight - 50) + 25;
            
            noBtn.style.left = `${x}px`;
            noBtn.style.top = `${y}px`;
        }

        // فەنکشنی کلیککردن لەسەر بەڵێ
        function sayYes() {
            const card = document.getElementById('mainCard');
            if(noBtn) noBtn.remove(); // سڕینەوەی دوگمەی نەخێر
            
            card.innerHTML = `
                <div class="title-bar">
                    <div class="title-text">LOVE</div>
                    <div class="title-bar-controls"><button>X</button></div>
                </div>
                <div class="window-body">
                    <img class="cat-gif" src="https://i.postimg.co/N0MvXy3X/cat-happy.gif" alt="Happy Cat">
                    <h2 style="color: #c92a2a; font-size: 24px; margin-bottom: 5px;">پایپیی! 🎉</h2>
                    <p style="font-weight: bold; font-size: 16px; color: #000; margin: 5px 0;">زۆرم خۆش دەوێیت بێلان 😍</p>
                </div>
            `;
            
            setInterval(createHeart, 100);
        }

        // دروستکردنی بارانی دڵ
        function createHeart() {
            const heart = document.createElement('div');
            heart.classList.add('heart-rain');
            
            const hearts = ['❤️', '💖', '💗', '💕'];
            heart.innerText = hearts[Math.floor(Math.random() * hearts.length)];
            
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.animationDuration = Math.random() * 2 + 2 + 's'; 
            heart.style.fontSize = Math.random() * 20 + 15 + 'px';
            
            document.body.appendChild(heart);
            
            setTimeout(() => {
                heart.remove();
            }, 4000);
        }
    </script>
</body>
</html>
