<!DOCTYPE html>
<html lang="zh-Hant">
<head>
    <meta charset="UTF-8">
    <title>活動倒數領券</title>
    <style>
        body{text-align:center;font-family:sans-serif;}
        button{padding:10px 20px;font-size:16px;margin-top:20px;}
    </style>
</head>
<body>
    <h2 id="timer">10:00</h2>
    <button id="getCoupon">領取禮卷</button>
    <p>目前已領取人數：<span id="counter">0</span>人</p>

    <script>
        // 倒數計時器(10分鐘)
        let time = 600;
        const timerElement = document.getElementById("timer");
        const btn = document.getElementById("getCoupon");
        const counterElement = document.getElementById("counter");

        let count = 0;

        const timer = setInterval(()=>{
            let mins = Math.floor(time / 60);
            let secs = time % 60;
            timerElement.textContent = `${mins}:${secs < 10 ? '0'+secs : secs}`;
            if(time <= 0){
                clearInterval(timer);
                btn.disabled = true;
                timerElement.textContent = "活動已結束";
            }
            time--;
        },1000);

        btn.onclick = ()=>{
            count++;
            counterElement.textContent = count;
            window.location.href = "success.html";
        };
    </script>
</body>
</html>
