<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Be My Valentine?</title>


<style>
body {
margin: 0;
height: 100vh;
display: flex;
align-items: center;
justify-content: center;
background: linear-gradient(135deg, #ffb6c1, #ffe4e1);
font-family: 'Comic Sans MS', 'Poppins', sans-serif;
}


.card {
background: white;
padding: 30px 25px;
border-radius: 20px;
text-align: center;
box-shadow: 0 15px 30px rgba(0,0,0,0.15);
max-width: 350px;
width: 90%;
}


h1 {
color: #ff4d6d;
margin-bottom: 15px;
}


p {
color: #555;
margin-bottom: 20px;
font-size: 18px;
}


img {
width: 100%;
max-height: 220px;
object-fit: cover;
border-radius: 15px;
margin-bottom: 20px;
}


.buttons {
display: flex;
justify-content: center;
gap: 15px;
}


button {
padding: 10px 20px;
font-size: 16px;
border: none;
border-radius: 20px;
cursor: pointer;
transition: transform 0.2s;
}


#yesBtn {
background-color: #ff4d6d;
color: white;
}


#noBtn {
background-color: #ddd;
color: #333;
}


button:hover {
transform: scale(1.05);
}
</style>
</head>
<body>


<div class="card">
<img id="mainImg" src="cat.png" alt="Cute Valentine Cat" />


<h1 id="title">Will you be my Valentine? 💖</h1>
<p id="text"></p>


<div class="buttons">
<button id="yesBtn">Yes 💕</button>
<button id="noBtn">No 🙃</button>
</div>
</div>


<script>
const yesBtn = document.getElementById('yesBtn');
const noBtn = document.getElementById('noBtn');
const title = document.getElementById('title');
const text = document.getElementById('text');
const img = document.getElementById('mainImg');


let yesClicks = 0;
let stage = 'start';


yesBtn.addEventListener('click', () => {
if (stage === 'start') {
yesClicks++;
if (yesClicks === 1) {
title.textContent = 'Are you sure? 😏';
} else if (yesClicks === 2) {
title.textContent = 'pls click no first 🙄';
}
} else if (stage === 'orElse') {
document.body.innerHTML = `
<div style="text-align:center; padding:40px;">
<h1 style="color:#ff4d6d;">YAYYY 💘💘</h1>
<p style="font-size:20px;">Correct choice 😌❤️</p>
</div>
`;
}
});


noBtn.addEventListener('click', () => {
// Go to the "or else" page
stage = 'orElse';
img.src = 'or_else.png';
title.textContent = 'Click yes 😼';
text.textContent = 'or else.';
});
</script>


</body>
</html>
