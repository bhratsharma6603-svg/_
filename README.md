<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>💖 Sorry Letter — Sweta 💖</title>
<!-- Romantic + clean fonts -->
<link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
<style>
:root{
  --bg1:#ffe4ec;
  --bg2:#fff3fa;
  --accent:#ff3b7d;
  --text:#3a3a3a;
}
*{box-sizing:border-box;margin:0;padding:0;}
body{
  min-height:100vh;
  background:linear-gradient(135deg,var(--bg1),var(--bg2));
  display:flex;
  justify-content:center;
  align-items:center;
  padding:20px;
  font-family:'Poppins',sans-serif;
}
.stage{
  width:100%;
  max-width:820px;
  background:rgba(255,255,255,0.85);
  border-radius:24px;
  padding:26px;
  text-align:center;
  position:relative;
  box-shadow:0 18px 40px rgba(12,18,35,0.12);
  animation:fadeIn 1s ease forwards;
}
@keyframes fadeIn{from{opacity:0;transform:translateY(20px);}to{opacity:1;transform:none;}}
h1{
  color:var(--accent);
  font-family:'Great Vibes',cursive;
  font-size:38px;
  margin-bottom:12px;
}
#letterWrap{
  display:none;
  margin-top:18px;
}
#letter{
  background:white;
  border-radius:16px;
  padding:22px;
  height:55vh;
  overflow:auto;
  font-family:'Great Vibes',cursive;
  font-size:20px;
  line-height:1.8;
  color:var(--text);
  box-shadow:0 8px 25px rgba(0,0,0,0.08);
  text-align:left;
}
.controls{
  margin-top:18px;
  display:flex;
  justify-content:center;
  gap:10px;
}
.btn{
  border:none;
  border-radius:999px;
  padding:10px 24px;
  cursor:pointer;
  font-weight:600;
  font-size:16px;
  transition:0.3s;
  font-family:'Poppins',sans-serif;
}
.btn.play{
  background:linear-gradient(45deg,#ff3b7d,#ff7aa3);
  color:white;
  box-shadow:0 8px 25px rgba(255,59,125,0.4);
}
.btn.play:hover{transform:scale(1.05);}
.btn.nav{
  background:#ffd6e8;
  color:#ff3b7d;
  border:2px solid #ff3b7d;
}
.btn.nav:hover{
  background:#ff3b7d;
  color:white;
}
</style>
</head>
<body>
<div class="stage">
  <h1>💖 Sorry Letter for Sweta 💖</h1>
  <button id="playBtn" class="btn play">Play Song & Show Letter 🎵</button>
  <div id="letterWrap">
    <div id="letter"></div>
    <div class="controls">
      <button id="prevBtn" class="btn nav">⬅ Previous</button>
      <button id="nextBtn" class="btn nav">Next ➡</button>
    </div>
  </div>
</div>
<!-- Song -->
<audio id="bgAudio" preload="auto">
  <source src="https://www.dropbox.com/scl/fi/pqsq50nagsnmzyvr7i5ta/AudioCutter_Tera-Yaar-Hoon-Main.mp3?rlkey=qwxp78iitej7spjsngbh7z4xh&st=b730ve62&dl=1" type="audio/mpeg">
</audio>
<script>
const playBtn=document.getElementById('playBtn');
const bgAudio=document.getElementById('bgAudio');
const letterWrap=document.getElementById('letterWrap');
const letterEl=document.getElementById('letter');
const nextBtn=document.getElementById('nextBtn');
const prevBtn=document.getElementById('prevBtn');
const parts=[
`Dear Doremon ,meri pyari Chimkandi 😄),
Sabse pehle tho mai yahi kehna chahta hu ki haan, maine galti ki hai… aur honestly, ye galti itni badi hai ki agar Angry Bird tumhare haath me hota toh shayad mujhe hawa me uda deta 😅.`,
`But sach me, mera intention kabhi bhi tumhe hurt karne ka nahi tha.

Sweta, tum sirf meri bestie nahi ho, tum meri hasi ki wajah ho, meri pareshaniyon ki partner ho, aur kabhi-kabhi meri personal life ki unofficial therapist bhi 😜.`,

`Aur mai janta hu ki maine kuch aise moments create kiye jisse tumhe bura laga, aur mujhe ab realize hua ki mere chote-chote jokes kabhi kabhi bahut impact kar dete hain.`,

`Mujhe yaad hai kaise tum hamesha meri har stupid baat par hans deti thi, aur meri har sharaarat ko tolerate karti thi. Aur ab wahi sharaarat maine ki jiski wajah se tum naraz ho gayi.`,

`Angry Bird wali tumhari energy aur meri har choti galti ko handle karna honestly mera biggest challenge hai 😅.`,
`Mai janta hu ki sirf “sorry” bolna enough nahi hai, but believe me, ye sorry mera dil se hai.`,

`Mai tumhare bina apni har crazy, funny aur boring din ki imagination bhi nahi kar sakta. Tumhare jokes, tumhari annoying baatein, tumhari hasi ke chote-chote moments… sab mujhe miss ho rahe hain.`,

`Chimkandi, mai promise karta hu ki ab se mai zyada careful rahunga, zyada understanding dikhauga (thodi-thodi 😂), aur kabhi bhi tumhare dil ko hurt karne wala kaam nahi karunga.`,

`Tum meri bestie ho, meri family jaisi, aur mujhe tumhare bina apni life incomplete lagti hai.`,

`Sorry Sweta! Tum meri bestie ho aur hamesha rahogi.
Mai tumhe bahut miss kar raha hu! ❤️

Tumhara bestu,<br>Bhrat`
];
let currentPart=0;
function typeText(text){
  letterEl.innerHTML="";
  let i=0;
  function step(){
    if(i<text.length){
      letterEl.innerHTML+=text[i];
      i++;
      setTimeout(step,15);
    }
  }
  step();
}
playBtn.addEventListener('click',()=>{
  playBtn.style.display='none';
  letterWrap.style.display='block';
  bgAudio.play().catch(()=>{});
  typeText(parts[currentPart]);
});
nextBtn.addEventListener('click',()=>{
  if(currentPart<parts.length-1){
    currentPart++;
    typeText(parts[currentPart]);
  }
});
prevBtn.addEventListener('click',()=>{
  if(currentPart>0){
    currentPart--;
    typeText(parts[currentPart]);
  }
});
</script>
</body>
</html>
