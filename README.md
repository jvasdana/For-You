<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Selamat Ulang Tahun!!!</title>

<link href="https://fonts.googleapis.com/css2?family=Fredoka+One&display=swap" rel="stylesheet">

<style>
html, body {
    margin: 0;
    padding: 0;
    overflow: hidden;
    height: 100%;
}

/* ===== BACKGROUND ANIMASI ===== */
#bg {
    position: fixed;
    width: 100%;
    height: 100%;
    background: linear-gradient(180deg, #ffc0cb, #ffb6c1);
    z-index: -2;
}

.line {
    position: absolute;
    width: 2px;
    height: 100vh;
    background: linear-gradient(
        to bottom,
        rgba(255,105,180,0),
        rgba(255,105,180,0.4),
        rgba(255,105,180,0)
    );
    animation: moveLine linear infinite;
}

@keyframes moveLine {
    from { transform: translateY(-100vh); }
    to { transform: translateY(100vh); }
}

.heart {
    position: absolute;
    color: #ff4d88;
    font-size: 20px;
    animation: fall linear infinite;
    opacity: 0.8;
}

@keyframes fall {
    from { transform: translateY(-10vh); }
    to { transform: translateY(110vh); }
}

/* ===== KONTEN ===== */
body {
    font-family: Arial, sans-serif;
    text-align: center;
}

.container {
    padding: 50px;
    background-color: rgba(255,255,255,0.85);
    border-radius: 15px;
    margin: 30px auto;
    max-width: 600px;
    position: relative;
    z-index: 2;
}

h1 {
    color: #ff69b4;
    font-size: 3em;
}

.question {
    font-family: 'Fredoka One', cursive;
    font-size: 2em;
}

button {
    font-size: 1.2em;
    padding: 10px 20px;
    background-color: #ff69b4;
    color: white;
    border: none;
    cursor: pointer;
    margin-top: 10px;
}

button:hover {
    background-color: #ff1493;
}

.hidden { display: none; }

.firework {
    position: absolute;
    width: 10px;
    height: 10px;
    border-radius: 50%;
    animation: explode 2s ease-out forwards;
}

@keyframes explode {
    to { transform: scale(10); opacity: 0; }
}

.celebration, .wow-message {
    font-family: 'Fredoka One', cursive;
    color: #ff69b4;
    font-size: 2em;
}
</style>
</head>

<body>

<div id="bg"></div>

<div class="container">
    <div id="intro">
        <h1>Selamat Ulang Tahun, Shafa Amanah!</h1>
        <img src="2.gif" style="max-width:300px;border-radius:10px">
        <button onclick="startQuiz()">Ayo Main!!</button>
    </div>

    <div id="q1" class="hidden">
        <p class="question">1 + 1 = ?</p>
        <input type="number" id="ans1">
        <button onclick="checkAnswer(1,2)">Jawab</button>
    </div>

    <div id="q2" class="hidden">
        <p class="question">2 x 2 = ?</p>
        <input type="number" id="ans2">
        <button onclick="checkAnswer(2,4)">Jawab</button>
    </div>

    <div id="q3" class="hidden">
        <p class="question">4 x 4 = ?</p>
        <input type="number" id="ans3">
        <button onclick="checkAnswer(3,16)">Jawab</button>
    </div>

    <div id="wow" class="hidden">
        <p class="wow-message">WOW SUDAH 16 TAHUN YAA 💖</p>
    </div>

    <div id="celebration" class="hidden">
        <p class="celebration">Selamat Ulang Tahun!!!!</p>
        <p>Cieee setahun lagi sweet seventeen 🎉</p>
        <p>From: [Orang Gila]</p>
    </div>
</div>

<script>
/* BACKGROUND */
function createLine() {
    const l = document.createElement("div");
    l.className = "line";
    l.style.left = Math.random()*100 + "vw";
    l.style.animationDuration = (4+Math.random()*6)+"s";
    document.getElementById("bg").appendChild(l);
    setTimeout(()=>l.remove(),10000);
}

function createHeart() {
    const h = document.createElement("div");
    h.className = "heart";
    h.innerHTML = "❤";
    h.style.left = Math.random()*100+"vw";
    h.style.fontSize = (16+Math.random()*24)+"px";
    h.style.animationDuration = (3+Math.random()*5)+"s";
    document.getElementById("bg").appendChild(h);
    setTimeout(()=>h.remove(),8000);
}

setInterval(createLine, 400);
setInterval(createHeart, 200);

/* QUIZ */
let currentQuestion = 1;

function startQuiz() {
    intro.classList.add("hidden");
    q1.classList.remove("hidden");
}

function checkAnswer(n, ans) {
    if (parseInt(document.getElementById("ans"+n).value) === ans) {
        document.getElementById("q"+n).classList.add("hidden");
        currentQuestion++;
        if (currentQuestion<=3)
            document.getElementById("q"+currentQuestion).classList.remove("hidden");
        else {
            wow.classList.remove("hidden");
            setTimeout(()=>{
                wow.classList.add("hidden");
                explodeFireworks();
                new Audio("petasan.mp3").play();
                setTimeout(()=>new Audio("hbdeee.mp3").play(),2000);
                celebration.classList.remove("hidden");
            },3000);
        }
    } else alert("Jawaban salah!");
}

function explodeFireworks(){
    for(let i=0;i<20;i++){
        const f=document.createElement("div");
        f.className="firework";
        f.style.left=Math.random()*100+"vw";
        f.style.top=Math.random()*100+"vh";
        f.style.backgroundColor=["red","yellow","blue","pink"][Math.floor(Math.random()*4)];
        document.body.appendChild(f);
        setTimeout(()=>f.remove(),2000);
    }
}
</script>

</body>
</html>
