<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Will you be my Valentine?</title>
<style>
/* Fullscreen background for mobile */
body {
    margin: 0;
    height: 100vh;
    width: 100vw;
    background: linear-gradient(rgba(0,0,0,0.45), rgba(0,0,0,0.45)),
                url("background.jpg") center center / cover no-repeat fixed;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    font-family: Arial, sans-serif;
    color: white;
    overflow: hidden;
    text-align: center;
}

/* Title */
h1 {
    font-size: 2rem;
    margin-bottom: 20px;
}

/* Buttons container */
.buttons {
    display: flex;
    justify-content: center;
    width: 80%;
    max-width: 260px;
    margin: auto;
}

button {
    flex: 1;
    margin: 5px;
    padding: 14px 0;
    font-size: 1.1rem;
    border: none;
    border-radius: 14px;
    cursor: pointer;
}

/* Heart animation */
.kiss {
    position: fixed;
    font-size: 2rem;
    pointer-events: none;
    animation: floatUp 2s linear forwards;
}

@keyframes floatUp {
    0% { opacity: 1; transform: translateY(0); }
    100% { opacity: 0; transform: translateY(-200px); }
}

/* Typing effect */
.typing {
    font-size: 1.5rem;
    margin-top: 20px;
}
</style>
</head>
<body>

<h1>Amishi 💕 Will you be my Valentine?</h1>
<div class="buttons">
    <button id="yes">Yes 💖</button>
    <button id="no">No 😢</button>
</div>

<audio id="song">
  <source src="call_out_my_name.mp3" type="audio/mpeg">
</audio>

<script>
// Move "No" button randomly on hover
const noBtn = document.getElementById("no");
noBtn.addEventListener("mouseenter", () => {
    const x = Math.random() * 60 + "%";
    const y = Math.random() * 60 + "%";
    noBtn.style.position = "absolute";
    noBtn.style.left = x;
    noBtn.style.top = y;
});

// When "Yes" clicked
document.getElementById("yes").addEventListener("click", yesClicked);

function yesClicked() {
    const song = document.getElementById("song");
    song.play();
    
    document.body.innerHTML = "";

    const wrapper = document.createElement("div");
    wrapper.style.display = "flex";
    wrapper.style.flexDirection = "column";
    wrapper.style.justifyContent = "center";
    wrapper.style.alignItems = "center";
    wrapper.style.height = "100vh";
    wrapper.style.textAlign = "center";
    document.body.appendChild(wrapper);

    const title = document.createElement("h1");
    title.innerHTML = "LET'S GOOOOOO 🎉💖<br>Amishi & Swaraj 💑";
    wrapper.appendChild(title);

    setTimeout(() => typeLove(wrapper), 1000);
    setInterval(() => kissExplosion(wrapper), 300);
}

// Typing effect
function typeLove(wrapper) {
    const text = "I love you Amishi ❤️";
    let i = 0;
    const div = document.createElement("div");
    div.className = "typing";
    wrapper.appendChild(div);

    const interval = setInterval(() => {
        div.textContent += text[i];
        i++;
        if (i === text.length) clearInterval(interval);
    }, 120);
}

// Floating hearts
function kissExplosion(wrapper) {
    const kiss = document.createElement("div");
    kiss.className = "kiss";
    kiss.textContent = "💋";
    kiss.style.left = Math.random() * 90 + "vw";
    kiss.style.top = Math.random() * 90 + "vh";
    document.body.appendChild(kiss);
    setTimeout(() => kiss.remove(), 2000);
}
</script>

</body>
</html>
