<!doctype html>
<html lang="hi">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>💌 Sorry Letter to You 💌</title>

<link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@600&family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">

<style>
:root{
  --accent1:#ff9ccf;
  --accent2:#9b5de5;
  --card-bg: rgba(255,255,255,0.95);
  --muted:#6b7280;
  --text:#2b2b2b;
}
*{box-sizing:border-box}
html,body{height:100%;margin:0;font-family:'Poppins',sans-serif;-webkit-font-smoothing:antialiased;-moz-osx-font-smoothing:grayscale;}
body{
  display:flex;
  align-items:center;
  justify-content:center;
  padding:20px;
  background: linear-gradient(120deg,#ffd1dc 0%, #d7c1ff 50%, #b6f0ff 100%);
  background-size:400% 400%;
  animation: bgAnim 12s ease infinite;
}
@keyframes bgAnim{
  0%{background-position:0% 50%}
  50%{background-position:100% 50%}
  100%{background-position:0% 50%}
}

/* Card */
.card{
  width:100%;
  max-width:760px;
  border-radius:18px;
  background: linear-gradient(180deg, rgba(255,255,255,0.98), rgba(255,250,255,0.98));
  box-shadow: 0 24px 60px rgba(20,18,40,0.12);
  padding:20px;
  position:relative;
}

/* Header */
.header{
  text-align:center;
  margin-top:6px;
}
.title{
  font-family:'Dancing Script',cursive;
  font-size:34px;
  color:var(--accent2);
  margin:6px 0;
}
.subtitle{
  color:var(--muted);
  font-size:13px;
  margin-bottom:8px;
}

/* Layout */
.container{
  display:flex;
  gap:18px;
  align-items:flex-start;
  margin-top:6px;
}
.avatar{
  min-width:82px;
  width:82px;
  height:82px;
  border-radius:12px;
  background:linear-gradient(180deg,#fff,#fff6ff);
  display:flex;
  align-items:center;
  justify-content:center;
  box-shadow: 0 10px 30px rgba(15,23,42,0.08);
}
.avatar img{ width:70px;height:70px;border-radius:10px;object-fit:cover; }

/* Content */
.content{ flex:1; }
.meta{
  display:flex;
  justify-content:space-between;
  align-items:center;
  gap:12px;
  margin-bottom:8px;
}
.part-indicator{ color:var(--muted); font-size:13px; }
.hint{ color:var(--muted); font-size:13px; }

/* Letter box */
.letter-box{
  background:var(--card-bg);
  border-radius:12px;
  padding:16px;
  max-height:56vh;
  overflow:auto;
  scroll-behavior:smooth;
  box-shadow: inset 0 1px 0 rgba(255,255,255,0.7), 0 10px 30px rgba(12,18,35,0.06);
  border:1px solid rgba(16,24,40,0.03);
}
.letter{
  font-family:'Dancing Script',cursive;
  font-size:18px;
  color:var(--text);
  line-height:1.6;
  white-space:pre-wrap;
  min-height:110px;
}

/* Controls */
.controls{
  display:flex;
  justify-content:center;
  gap:10px;
  margin-top:12px;
  flex-wrap:wrap;
}
.btn{
  border:0;
  padding:10px 16px;
  border-radius:999px;
  cursor:pointer;
  font-weight:600;
  font-family:'Poppins',sans-serif;
  transition: transform .16s ease, opacity .16s;
}
.btn.primary{
  background: linear-gradient(90deg,#ff7aa3,#9b5de5);
  color:white;
  box-shadow: 0 10px 26px rgba(155,93,229,0.18);
}
.btn.ghost{
  background:transparent;
  color:var(--accent2);
  border:2px solid rgba(155,93,229,0.12);
}
.btn.small{ padding:8px 12px; font-size:14px; }
.btn:active{ transform:translateY(1px); }
.btn[disabled]{ opacity:0.5; cursor:default; transform:none; }

/* Start area */
.start-wrap{ display:flex; justify-content:center; margin-top:10px; }
.start-btn{ padding:12px 22px; border-radius:999px; font-size:16px; }

/* Responsive */
@media (max-width:640px){
  .container{ flex-direction:column; align-items:center; }
  .avatar{ margin-bottom:8px; }
  .title{ font-size:30px; }
  .letter{ font-size:16px; }
  .letter-box{ max-height:62vh; }
}
</style>
</head>
<body>

  <div class="card" role="region" aria-label="Sorry letter card">
    <div class="header">
      <div class="title">💌 Sorry Letter to You 💌</div>
      <div class="subtitle">A heartfelt note — tap Play to begin</div>
    </div>

    <div class="container">
      <div class="avatar" aria-hidden="true">
        <!-- small decorative (kept simple) -->
        <svg width="48" height="48" viewBox="0 0 24 24" fill="none" aria-hidden="true">
          <path d="M12 21s-6-4.35-9-7.28C-1 8.5 5.5 4 12 8c6.5-4 13 0.5 9 5.72C18 16.65 12 21 12 21z" fill="#ffd1e6"/>
        </svg>
      </div>

      <div class="content">
        <div class="meta">
          <div class="part-indicator" id="partIndicator">Part 1 / 10</div>
          <div class="hint">Use Next / Previous or ← → keys</div>
        </div>

        <div class="letter-box" id="letterBox" tabindex="0" aria-live="polite">
          <div class="letter" id="letterText"></div>
        </div>

        <div class="controls" id="controls" style="display:flex;">
          <button class="btn ghost small" id="prevBtn" disabled>◀ Previous</button>
          <button class="btn primary small" id="nextBtn">Next ▶</button>
          <button class="btn ghost small" id="replayBtn">Replay 🔄</button>
        </div>

        <div class="start-wrap" id="startWrap">
          <button class="btn primary start-btn" id="startBtn" aria-label="Play song and start">🎵 Play & Start</button>
        </div>
      </div>
    </div>
  </div>

  <!-- Audio element: first tries relative GitHub path (music/terayaar.mp3) -->
  <audio id="bgAudio" preload="auto" loop>
    <source src="music/terayaar.mp3" type="audio/mpeg">
    <!-- Fallback to your Dropbox raw link (may be blocked by CORS on some hosts) -->
    <source src="https://www.dropbox.com/scl/fi/pqsq50nagsnmzyvr7i5ta/AudioCutter_Tera-Yaar-Hoon-Main.mp3?raw=1" type="audio/mpeg">
  </audio>

<script>
/* ---------- Letter parts (10 equal-ish parts) ---------- */
const parts = [
`Dear Doremon (aka meri pyari Chimkandi 😄),\n\nSabse pehle tho mai yahi kehna chahta hu ki haan, maine galti ki hai…`,

`Aur honestly, ye galti itni badi hai ki agar Angry Bird tumhare haath me hota toh shayad mujhe hawa me uda deta 😅.`,

`But sach me, mera intention kabhi bhi tumhe hurt karne ka nahi tha. Main galti se kiya tha, jaan bhoojh kar nahi.`,

`Sweta, tum sirf meri bestie nahi ho — tum meri hasi ki wajah ho, meri pareshaniyon ki partner ho, aur kabhi-kabhi meri personal life ki unofficial therapist bhi 😜.`,

`Mai janta hu ki maine kuch aise moments create kiye jisse tumhe bura laga. Aur ab mujhe realize hua ki mere chote-chote jokes ya funny moments kabhi kabhi bahut impact kar dete hain.`,

`Mujhe yaad hai kaise tum hamesha meri har stupid baat par hans deti thi, aur meri har sharaarat ko tolerate karti thi. Ab jo hua uske liye mujhe bahut afsos hai.`,

`Angry Bird wali tumhari energy aur meri har choti galti ko handle karna mera biggest challenge hai 😅. Par iska matlab ye nahi ki tumhe hurt karna theek hai.`,

`Mai janta hu ki sirf “sorry” bolna enough nahi hai — par believe me, ye sorry mera dil se hai. Tumhare bina mera din adhoora lagta hai.`,

`Chimkandi, mai promise karta hu ki ab se mai zyada careful rahunga, zyada understanding dikhauga (thodi-thodi 😂), aur kabhi bhi tumhare dil ko hurt karne wala kaam nahi karunga.`,

`Toh please, mujhe forgive kar do. Mujhe wapas apni crazy, funny aur loving bestie chahiye. Sorry Sweta! Tum meri bestie ho aur hamesha rahogi.\n\nMai tumhe bahut miss kar raha hu! ❤️\n\nTumhara bestu,\nBhrat`
];

const total = parts.length;

/* ---------- DOM ---------- */
const letterText = document.getElementById('letterText');
const partIndicator = document.getElementById('partIndicator');
const prevBtn = document.getElementById('prevBtn');
const nextBtn = document.getElementById('nextBtn');
const replayBtn = document.getElementById('replayBtn');
const startBtn = document.getElementById('startBtn');
const startWrap = document.getElementById('startWrap');
const bgAudio = document.getElementById('bgAudio');
const letterBox = document.getElementById('letterBox');

let current = 0;
let typingTimer = null;
const SPEED = 18; // ms per char

/* Render HTML-aware: converts \n to <br> then types HTML tags whole */
function typePart(raw, cb){
  clearTimeout(typingTimer);
  letterText.innerHTML = '';
  const html = raw.replace(/\n/g, '<br>');
  let i = 0;
  function step(){
    if(i >= html.length){
      if(cb) cb();
      return;
    }
    if(html[i] === '<'){
      const close = html.indexOf('>', i);
      if(close === -1){
        letterText.innerHTML += html.slice(i);
        i = html.length;
      } else {
        letterText.innerHTML += html.slice(i, close + 1);
        i = close + 1;
      }
    } else {
      letterText.innerHTML += html.charAt(i);
      i++;
    }
    letterBox.scrollTop = letterBox.scrollHeight;
    typingTimer = setTimeout(step, SPEED);
  }
  step();
}

/* UI updates */
function updateUI(){
  partIndicator.textContent = `Part ${current + 1} / ${total}`;
  prevBtn.disabled = (current === 0);
  nextBtn.disabled = (current === total - 1);
}

/* Navigation */
function goTo(idx){
  if(idx < 0 || idx >= total) return;
  current = idx;
  updateUI();
  typePart(parts[current], ()=>{
    letterBox.scrollTop = letterBox.scrollHeight;
  });
}

/* Buttons */
prevBtn.addEventListener('click', ()=>{ if(current>0) goTo(current-1); letterBox.focus(); });
nextBtn.addEventListener('click', ()=>{ if(current<total-1) goTo(current+1); letterBox.focus(); });
replayBtn.addEventListener('click', ()=>{ goTo(0); letterBox.focus(); });

/* Keyboard support */
document.addEventListener('keydown', (e)=>{
  if(e.key === 'ArrowRight'){ if(current < total -1) goTo(current+1); }
  if(e.key === 'ArrowLeft'){ if(current > 0) goTo(current-1); }
});

/* Start: user tap required for GitHub Pages compatibility */
startBtn.addEventListener('click', async ()=>{
  // set safe volume
  try{
    bgAudio.volume = 0.4;
    await bgAudio.play();
  }catch(err){
    console.warn('Audio play failed:', err);
  }
  // hide start area
  startWrap.style.display = 'none';
  // reveal controls and first part
  goTo(0);
});

/* On load: initial state */
window.addEventListener('load', ()=>{
  updateUI();
  letterText.innerHTML = ''; // empty until start
  // keep controls visible (user wanted nav present)
});

/* If user touches letter box, stop auto-scroll so they can scroll manually */
letterBox.addEventListener('touchstart', ()=>{
  clearTimeout(typingTimer);
});

/* Optional: If audio fails to play from relative path (404), browser will use fallback source (Dropbox) */
bgAudio.addEventListener('error', (e)=>{
  console.warn('Audio element error', e);
});
</script>
</body>
</html>
