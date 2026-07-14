<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Happy Birthday, My Love! ❤️</title>
<!-- Google Fonts -->
<link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
<!-- Canvas Confetti Library -->
<script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.5.1/dist/confetti.browser.min.js"></script>

<style>
* {
margin: 0;
padding: 0;
box-sizing: border-box;
}

body {
background: linear-gradient(135deg, #1f011b, #3d0532, #11000f);
color: #fff;
font-family: 'Poppins', sans-serif;
min-height: 100vh;
overflow-x: hidden;
display: flex;
flex-direction: column;
align-items: center;
justify-content: flex-start;
padding: 20px;
}

/* Floating background hearts */
.hearts-container {
position: fixed;
top: 0;
left: 0;
width: 100%;
height: 100%;
pointer-events: none;
overflow: hidden;
z-index: 0;
}

.heart {
position: absolute;
bottom: -50px;
background: rgba(255, 105, 180, 0.3);
transform: rotate(-45deg);
animation: floatUp 8s infinite linear;
}

.heart::before, .heart::after {
content: '';
position: absolute;
width: 100%;
height: 100%;
background: inherit;
border-radius: 50%;
}

.heart::before {
top: -50%;
left: 0;
}

.heart::after {
top: 0;
left: 50%;
}

@keyframes floatUp {
0% {
transform: translateY(0) rotate(-45deg) scale(0.6);
opacity: 1;
}
100% {
transform: translateY(-100vh) rotate(-45deg) scale(1.2);
opacity: 0;
}
}

/* Main Card */
.container {
position: relative;
z-index: 1;
max-width: 600px;
width: 100%;
background: rgba(255, 255, 255, 0.05);
backdrop-filter: blur(12px);
border: 1px solid rgba(255, 255, 255, 0.15);
border-radius: 20px;
padding: 40px 30px;
box-shadow: 0 15px 35px rgba(0, 0, 0, 0.5);
text-align: center;
margin-top: 30px;
}

h1 {
font-family: 'Dancing Script', cursive;
font-size: 3.5rem;
color: #ff758c;
margin-bottom: 10px;
text-shadow: 0 0 15px rgba(255, 117, 140, 0.5);
}

.subtitle {
font-size: 1.1rem;
color: #ffb1c1;
margin-bottom: 25px;
font-weight: 300;
}

/* Photo Frame */
.photo-frame {
width: 180px;
height: 180px;
margin: 0 auto 25px;
border-radius: 50%;
overflow: hidden;
border: 4px solid #ff758c;
box-shadow: 0 0 20px rgba(255, 117, 140, 0.4);
}

.photo-frame img {
width: 100%;
height: 100%;
object-fit: cover;
}

/* Message Box */
.message-box {
background: rgba(0, 0, 0, 0.2);
padding: 20px;
border-radius: 12px;
border-left: 4px solid #ff758c;
margin-bottom: 30px;
text-align: left;
font-size: 0.95rem;
line-height: 1.6;
color: #fce4ec;
}

/* Interactive Button */
.btn-surprise {
background: linear-gradient(135deg, #ff758c, #ff7eb3);
color: white;
border: none;
padding: 12px 30px;
font-size: 1.1rem;
font-weight: 600;
border-radius: 30px;
cursor: pointer;
box-shadow: 0 5px 15px rgba(255, 117, 140, 0.4);
transition: all 0.3s ease;
}

.btn-surprise:hover {
transform: scale(1.05);
box-shadow: 0 8px 20px rgba(255, 117, 140, 0.6);
}

/* Hidden Surprise Section */
.hidden-surprise {
display: none;
margin-top: 25px;
animation: fadeIn 1s ease forwards;
}

.hidden-surprise p {
font-size: 1.1rem;
color: #ffebee;
font-family: 'Dancing Script', cursive;
font-size: 2rem;
color: #ff80ab;
}

@keyframes fadeIn {
from { opacity: 0; transform: translateY(10px); }
to { opacity: 1; transform: translateY(0); }
}

footer {
margin-top: 30px;
font-size: 0.8rem;
color: rgba(255, 255, 255, 0.4);
z-index: 1;
}
</style>
</head>
<body>

<!-- Floating Hearts Animation Background -->
<div class="hearts-container" id="hearts-container"></div>

<div class="container">
<!-- Change to her name -->
<h1>Happy Birthday, My Love!</h1>
<div class="subtitle">To the most special girl in my world ✨</div>

<!-- Replace the src link with a picture of her or both of you -->
<div class="photo-frame">
<img src="https://images.unsplash.com/photo-1534528741775-53994a69daeb?auto=format&fit=crop&w=400&q=80" alt="Her Photo">
</div>

<!-- Customize your heartfelt message here -->
<div class="message-box">
<p>Every single day with you feels like a gift. Thank you for bringing so much brightness, laughter, and endless love into my life. I hope your special day is just as amazing, beautiful, and wonderful as you are. I love you today and always! ❤️</p>
</div>

<button class="btn-surprise" onclick="revealSurprise()">Open Your Surprise 🎁</button>

<div class="hidden-surprise" id="surprise-text">
<p>You are my favorite reason to smile! 🥰</p>
</div>
</div>

<footer>Made with all my love, just for you.</footer>

<script>
// Generate floating background hearts dynamically
function createHeart() {
const container = document.getElementById('hearts-container');
const heart = document.createElement('div');
heart.classList.add('heart');

const size = Math.random() * 20 + 10 + 'px';
heart.style.width = size;
heart.style.height = size;
heart.style.left = Math.random() * 100 + 'vw';
heart.style.animationDuration = Math.random() * 4 + 5 + 's';

container.appendChild(heart);

setTimeout(() => {
heart.remove();
}, 9000);
}

setInterval(createHeart, 400);

// Surprise button action + Confetti
function revealSurprise() {
const surprise = document.getElementById('surprise-text');
surprise.style.display = 'block';

// Trigger beautiful celebratory confetti
confetti({
particleCount: 100,
spread: 70,
origin: { y: 0.6 },
colors: ['#ff758c', '#ff7eb3', '#ffffff', '#ff80ab']
});
}
</script>
</body>
</html>
