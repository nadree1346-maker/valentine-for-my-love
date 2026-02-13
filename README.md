<!DOCTYPE html>
<html lang="th">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For My Love ❤️</title>

<style>
body {
    margin: 0;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    background: linear-gradient(135deg, #ff758c, #ff7eb3);
    font-family: 'Segoe UI', sans-serif;
    overflow: hidden;
}

.card {
    background: white;
    padding: 40px;
    border-radius: 20px;
    text-align: center;
    box-shadow: 0 10px 30px rgba(0,0,0,0.2);
    z-index: 2;
}

h1 {
    color: #ff2e63;
}

button {
    padding: 12px 25px;
    font-size: 18px;
    border: none;
    border-radius: 30px;
    background: #ff2e63;
    color: white;
    cursor: pointer;
    transition: 0.3s;
}

button:hover {
    transform: scale(1.1);
}

.flower {
    font-size: 80px;
    margin-top: 20px;
    display: none;
    animation: pop 0.8s ease forwards;
}

@keyframes pop {
    from {transform: scale(0);}
    to {transform: scale(1);}
}

.heart {
    position: absolute;
    color: red;
    font-size: 20px;
    animation: floatUp 5s linear infinite;
}

@keyframes floatUp {
    0% {transform: translateY(100vh); opacity: 1;}
    100% {transform: translateY(-10vh); opacity: 0;}
}
</style>
</head>

<body>

<div class="card">
    <h1>Happy Valentine's Day ❤️</h1>
    <p>กดเพื่อรับดอกไม้จากนัท 💌</p>
    <button onclick="showSurprise()">กดรับดอกไม้ 🌹</button>
    <div class="flower" id="flower">🌹</div>
</div>

<!-- เพลง (ใส่ไฟล์ mp3 ชื่อ love.mp3 ไว้โฟลเดอร์เดียวกัน) -->
<audio id="bgmusic" src="love.mp3"></audio>

<script>
function showSurprise() {
    document.getElementById("flower").style.display = "block";
    document.getElementById("bgmusic").play();
    createHearts();
}

function createHearts() {
    setInterval(() => {
        const heart = document.createElement("div");
        heart.classList.add("heart");
        heart.innerHTML = "❤️";
        heart.style.left = Math.random() * 100 + "vw";
        heart.style.fontSize = Math.random() * 30 + 20 + "px";
        document.body.appendChild(heart);

        setTimeout(() => {
            heart.remove();
        }, 5000);
    }, 300);
}
</script>

</body>
</html>
