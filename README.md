<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>💖 Sorry Letter for Sweta 💖</title>

<!-- Google Fonts -->
<link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@600&family=Great+Vibes&display=swap" rel="stylesheet">

<style>
:root {
  --bg1: #f8cdda;
  --bg2: #1d2b64;
}
body {
  margin: 0;
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  background: linear-gradient(135deg, var(--bg1), var(--bg2));
  color: #333;
  overflow: hidden;
  text-align: center;
  position: relative;
}
h1 {
  font-family: 'Great Vibes', cursive; /* Stylish heading font */
  font-size: 3em;
  color: #ff69b4;
  margin-bottom: 10px;
}
.message-box {
  width: 90%;
  max-width: 600px;
  height: 300px;
  background: rgba(255,255,255,0.9);
  border-radius: 20px;
  box-shadow: 0 0 25px rgba(0,0,0,0.25);
  padding: 20px;
  overflow-y: auto;
  font-family: 'Dancing Script', cursive; /* Stylish message font */
  font-size: 1.25em;
  line-height: 1.75;
  display: none;
  text-align: left;
}
.buttons {
  margin-top: 15px;
  display: flex;
  justify-content: center;
  gap: 15px;
}
button {
  background: #ff4da6;
  color: white;
  border: none;
  padding: 10px 25px;
  border-radius: 25px;
  cursor: pointer;
  font-size: 1em;
  transition: all 0.3s;
  font-family: 'Dancing Script', cursive;
}
button:hover {background: #ff1a8c;}
audio {display: none;}

/* Floating Hearts */
.heart {
  position: absolute;
  width: 20px;
  height: 20px;
  background: pink;
  transform: rotate(45deg);
  animation: float 6s linear infinite;
}
.heart::before,
.heart::after {
  content: "";
  position: absolute;
  width: 20px;
  height: 20px;
  background: pink;
  border-radius: 50%;
}
.heart::before { top: -10px; left: 0; }
.heart::after { left: 10px; top: 0; }

@keyframes float {
  0% { transform: translateY(100vh) rotate(0deg); opacity:1; }
  100% { transform: translateY(-50px) rotate(360deg); opacity:0; }
}
</style>
</head>
<body>

<h1>💌 Sorry Letter for Sweta 💌</h1>
<button id="playBtn">🎵 Play Song & Start 💖</button>
<audio id="bgMusic" src="https://www.dropbox.com/scl/fi/pqsq50nagsnmzyvr7i5ta/AudioCutter_Tera-Yaar-Hoon-Main.mp3?rlkey=qwxp78iitej7spjsngbh7z4xh&st=b730ve62&raw=1"></audio>

<div class="message-box" id="msgBox"></div>
<div class="buttons">
  <button id="prevBtn">⬅ Previous</button>
  <button id="nextBtn">Next ➡</button>
</div>

<script>
const parts = [
  `Dear Doremon (aka meri pyari Chimkandi 😄),<br><br>Sabse pehle tho mai yahi kehna chahta hu ki haan, maine galti ki hai… aur honestly, ye galti itni badi hai ki agar Angry Bird tumhare haath me hota toh shayad mujhe hawa me uda deta 😅.`,
  `But sach me, mera intention kabhi bhi tumhe hurt karne ka nahi tha. Sweta, tum sirf meri bestie nahi ho, tum meri hasi ki wajah ho, meri pareshaniyon ki partner ho, aur kabhi-kabhi meri personal life ki unofficial therapist bhi 😜.`,
  `Aur mai janta hu ki maine kuch aise moments create kiye jisse tumhe bura laga, aur mujhe ab realize hua ki mere chote-chote jokes ya funny moments kabhi kabhi bahut impact kar dete hain.`,
  `Doremon, mujhe yaad hai kaise tum hamesha meri har stupid baat par hans deti thi, aur meri har sharaarat ko tolerate karti thi. Aur ab wahi sharaarat maine ki jiski wajah se tum naraz ho gayi.`,
  `Angry Bird wali tumhari energy aur meri har choti galti ko handle karna honestly mera biggest challenge hai 😅.`,
  `Mai janta hu ki sirf “sorry” bolna enough nahi hai, but believe me, ye sorry mera dil se hai.`,
  `Mai tumhare bina apni har crazy, funny aur boring din ki imagination bhi nahi kar sakta.`,
  `Tumhare jokes, tumhari annoying baatein, tumhari hasi ke chote-chote moments… sab mujhe miss ho rahe hain.`,
  `Chimkandi, mai promise karta hu ki ab se mai zyada careful rahunga, zyada understanding dikhauga, aur kabhi bhi tumhare dil ko hurt karne wala kaam nahi karunga.`,
  `Sorry Sweta! Tum meri bestie ho aur hamesha rahogi. Mai tumhe bahut miss kar raha hu! ❤️<br><br>Tumhara bestu,<br><b>Bhrat</b>`
];

let index = 0;
const msgBox = document.getElementById('msgBox');
const nextBtn = document.getElementById('nextBtn');
const prevBtn = document.getElementById('prevBtn');
const playBtn = document.getElementById('playBtn');
const bgMusic = document.getElementById('bgMusic');

function typeMessage(text, callback){
  msgBox.innerHTML = '';
  let i=0;
  function typing(){
    if(i < text.length){
      if(text[i]==='<'){
        const close = text.indexOf('>', i);
        msgBox.innerHTML += text.slice(i, close+1);
        i = close+1;
      } else {
        msgBox.innerHTML += text[i];
        i++;
      }
      setTimeout(typing, 25);
    } else callback && callback();
  }
  typing();
}

function createHeart(){
  const h = document.createElement('div');
  h.className = 'heart';
  h.style.left = Math.random()*100+'%';
  h.style.animationDuration = (5 + Math.random()*3)+'s';
  document.body.appendChild(h);
  setTimeout(()=>{h.remove()}, 8000);
}

playBtn.addEventListener('click', () => {
  bgMusic.play().then(() => {
    playBtn.style.display = 'none';
    msgBox.style.display = 'block';
    typeMessage(parts[index]);
    setInterval(createHeart, 500);
  }).catch(() => { alert("Please tap again to start the music 🎶"); });
});

function showMessage() { typeMessage(parts[index]); }

nextBtn.addEventListener('click', () => { if(index < parts.length-1) index++; showMessage(); });
prevBtn.addEventListener('click', () => { if(index > 0) index--; showMessage(); });
</script>

</body>
</html>
