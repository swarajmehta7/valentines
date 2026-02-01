![Uploading background.<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Valentine 💘</title>

<style>
    body {
        margin: 0;
        height: 100vh;
        background: linear-gradient(
            rgba(0,0,0,0.45),
            rgba(0,0,0,0.45)
        ),
        url("background.jpg") center/cover no-repeat;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        font-family: Arial, sans-serif;
        color: white;
        overflow: hidden;
        text-align: center;
    }

    h1 {
        font-size: 2rem;
        margin-bottom: 15px;
        padding: 0 12px;
    }

    .countdown {
        font-size: 1.1rem;
        margin-bottom: 20px;
        opacity: 0.9;
    }

    .buttons {
        position: relative;
        width: 260px;
        height: 150px;
    }

    button {
        padding: 14px 24px;
        font-size: 1.1rem;
        border: none;
        border-radius: 14px;
        cursor: pointer;
    }

    #yes {
        background: #2ecc71;
        color: white;
    }

    #no {
        background: #e74c3c;
        color: white;
        position: absolute;
        left: 120px;
        top: 70px;
    }

    .heart {
        position: fixed;
        bottom: -20px;
        animation: floatUp 6s linear infinite;
        opacity: 0.8;
    }

    @keyframes floatUp {
        from { transform: translateY(0); opacity: 1; }
        to { transform: translateY(-110vh); opacity: 0; }
    }

    .typing {
        font-size: 2.2rem;
        margin-top: 20px;
        white-space: nowrap;
        overflow: hidden;
        border-right: 3px solid white;
        animation: blink 0.8s infinite;
    }

    @keyframes blink {
        50% { border-color: transparent; }
    }

    .kiss {
        position: fixed;
        font-size: 30px;
        animation: explode 2s ease-out forwards;
    }

    @keyframes explode {
        from { transform: scale(0); opacity: 1; }
        to { transform: scale(2); opacity: 0; }
    }
</style>
</head>

<body>

<h1>Amishi 💕<br>Will you be my Valentine?</h1>
<div class="countdown" id="countdown"></div>

<div class="buttons">
    <button id="yes" onclick="yesClicked()">Yes 💖</button>
    <button id="no" onmouseover="moveNo()">No 🙈</button>
</div>

<audio id="song">
    <source src="call_out_my_name.mp3" type="audio/mpeg">
</audio>

<script>
    function moveNo() {
        const no = document.getElementById("no");
        no.style.left = Math.random() * 180 + "px";
        no.style.top = Math.random() * 90 + "px";
    }

    function yesClicked() {
        document.getElementById("song").play();
        document.body.innerHTML = "";

        const title = document.createElement("h1");
        title.innerHTML = "LET'S GOOOOOO 🎉💖<br>Amishi & Swaraj 💑";
        document.body.appendChild(title);

        setTimeout(typeLove, 1500);
        setInterval(kissExplosion, 300);
    }

    function typeLove() {
        const text = "I love you Amishi ❤️";
        let i = 0;
        const div = document.createElement("div");
        div.className = "typing";
        document.body.appendChild(div);

        const interval = setInterval(() => {
            div.textContent += text[i];
            i++;
            if (i === text.length) clearInterval(interval);
        }, 120);
    }

    function kissExplosion() {
        const kiss = document.createElement("div");
        kiss.className = "kiss";
        kiss.textContent = "💋";
        kiss.style.left = Math.random() * 100 + "vw";
        kiss.style.top = Math.random() * 100 + "vh";
        document.body.appendChild(kiss);
        setTimeout(() => kiss.remove(), 2000);
    }

    // Floating hearts
    setInterval(() => {
        const heart = document.createElement("div");
        heart.className = "heart";
        heart.innerHTML = "❤️";
        heart.style.left = Math.random() * 100 + "vw";
        heart.style.fontSize = (16 + Math.random() * 24) + "px";
        document.body.appendChild(heart);
        setTimeout(() => heart.remove(), 6000);
    }, 250);

    // Countdown to Feb 14
    const countdownEl = document.getElementById("countdown");
    const valentine = new Date("February 14, 2026 00:00:00").getTime();

    setInterval(() => {
        const now = new Date().getTime();
        const diff = valentine - now;

        if (diff > 0) {
            const d = Math.floor(diff / (1000 * 60 * 60 * 24));
            const h = Math.floor((diff / (1000 * 60 * 60)) % 24);
            const m = Math.floor((diff / (1000 * 60)) % 60);
            countdownEl.innerHTML =
                `⏳ Valentine in ${d}d ${h}h ${m}m`;
        } else {
            countdownEl.innerHTML = "💘 It's Valentine’s Day!";
        }
    }, 1000);
</script>

</body>
</html>jpg…]()
