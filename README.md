# viodio
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Ko Ko ♡ Babe — Valentine</title>

  <!-- Cute cartoon font (Google Fonts) -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Baloo+2:wght@400;600;700&display=swap" rel="stylesheet">

  <style>
    :root{
      --pink:#ff77b7;
      --cream:#fff3e6;
      --violet:#7b5cff;
      --violet2:#b49bff;
      --ink:#2b2233;
      --card:#ffffffcc;
      --shadow: 0 18px 40px rgba(43,34,51,.18);
      --stroke: rgba(43,34,51,.18);
    }

    *{ box-sizing:border-box; }
    body{
      margin:0;
      font-family:"Baloo 2", system-ui, -apple-system, Segoe UI, Roboto, Arial, sans-serif;
      color:var(--ink);
      background:
        radial-gradient(1200px 800px at 15% 10%, #ffd3ea 0%, transparent 60%),
        radial-gradient(1100px 700px at 90% 20%, #d6ccff 0%, transparent 55%),
        radial-gradient(900px 650px at 40% 95%, #fff0d7 0%, transparent 60%),
        linear-gradient(180deg, #fff 0%, var(--cream) 100%);
      overflow-x:hidden;
    }

    /* floating hearts background */
    .hearts{
      position:fixed;
      inset:0;
      pointer-events:none;
      overflow:hidden;
      z-index:0;
    }
    .heart{
      position:absolute;
      width:18px; height:18px;
      background: var(--pink);
      transform: rotate(45deg);
      opacity:.22;
      filter: drop-shadow(0 8px 14px rgba(255,119,183,.25));
      animation: floatUp linear infinite;
    }
    .heart::before,.heart::after{
      content:"";
      position:absolute;
      width:18px; height:18px;
      background: var(--pink);
      border-radius:50%;
    }
    .heart::before{ left:-9px; top:0; }
    .heart::after{ top:-9px; left:0; }

    @keyframes floatUp{
      from{ transform: translateY(110vh) rotate(45deg); }
      to{ transform: translateY(-20vh) rotate(45deg); }
    }

    /* top nav */
    header{
      position:sticky;
      top:0;
      z-index:50;
      backdrop-filter: blur(10px);
      background: rgba(255,255,255,.6);
      border-bottom: 1px solid rgba(0,0,0,.06);
    }
    .nav{
      max-width:1100px;
      margin:0 auto;
      padding:12px 16px;
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap:10px;
    }
    .logo{
      display:flex;
      align-items:center;
      gap:10px;
      font-weight:800;
      letter-spacing:.3px;
    }
    .badge{
      background: linear-gradient(135deg, var(--pink), var(--violet));
      color:white;
      padding:6px 10px;
      border-radius:999px;
      box-shadow: 0 10px 18px rgba(123,92,255,.18);
      font-size:14px;
      white-space:nowrap;
    }
    .nav a{
      color:var(--ink);
      text-decoration:none;
      font-weight:700;
      padding:8px 10px;
      border-radius:999px;
      transition:.2s ease;
    }
    .nav a:hover{
      background: rgba(123,92,255,.10);
      transform: translateY(-1px);
    }

    /* main layout */
    main{
      position:relative;
      z-index:1;
      max-width:1100px;
      margin:0 auto;
      padding:26px 16px 70px;
    }

    .hero{
      display:grid;
      grid-template-columns: 1.15fr .85fr;
      gap:18px;
      align-items:stretch;
    }
    @media (max-width:900px){
      .hero{ grid-template-columns:1fr; }
    }

    .panel{
      background: var(--card);
      border:1px solid rgba(0,0,0,.06);
      border-radius:26px;
      box-shadow: var(--shadow);
      padding:18px;
      position:relative;
      overflow:hidden;
    }
    .panel::after{
      content:"";
      position:absolute;
      inset:-2px;
      border-radius:26px;
      pointer-events:none;
      border:2px dashed rgba(255,119,183,.18);
    }

    .title{
      font-size: clamp(30px, 4vw, 50px);
      margin:4px 0 6px;
      line-height:1.05;
    }
    .subtitle{
      margin:0 0 12px;
      font-size:18px;
      opacity:.9;
    }
    .pillRow{
      display:flex;
      flex-wrap:wrap;
      gap:10px;
      margin:14px 0 12px;
    }
    .pill{
      background: #fff;
      border:1px solid rgba(0,0,0,.07);
      border-radius:999px;
      padding:10px 12px;
      display:flex;
      align-items:center;
      gap:8px;
      font-weight:700;
      box-shadow: 0 10px 18px rgba(0,0,0,.06);
    }
    .dot{
      width:10px; height:10px; border-radius:50%;
      background: linear-gradient(135deg, var(--pink), var(--violet));
      box-shadow: 0 10px 18px rgba(255,119,183,.15);
    }

    .buttons{
      display:flex;
      flex-wrap:wrap;
      gap:10px;
      margin-top:12px;
    }
    button{
      font-family:inherit;
      border:none;
      cursor:pointer;
      font-weight:800;
      border-radius:16px;
      padding:12px 14px;
      transition:.18s ease;
    }
    .btnPrimary{
      background: linear-gradient(135deg, var(--pink), var(--violet));
      color:white;
      box-shadow: 0 14px 24px rgba(123,92,255,.22);
    }
    .btnPrimary:hover{ transform: translateY(-2px); }
    .btnGhost{
      background: rgba(255,255,255,.85);
      color: var(--ink);
      border:1px solid rgba(0,0,0,.08);
    }
    .btnGhost:hover{ transform: translateY(-2px); }

    /* photo polaroids */
    .polaroids{
      display:grid;
      grid-template-columns: 1fr;
      gap:14px;
      height:100%;
    }
    .polaroid{
      background: #fff;
      border-radius:22px;
      padding:12px;
      box-shadow: 0 16px 30px rgba(0,0,0,.10);
      border: 1px solid rgba(0,0,0,.06);
      transform: rotate(-1.5deg);
      position:relative;
    }
    .polaroid:nth-child(2){
      transform: rotate(1.5deg);
    }
    .photo{
      width:100%;
      aspect-ratio: 4 / 3;
      object-fit: cover;
      border-radius:18px;
      border:2px solid rgba(0,0,0,.06);
      background: #f3f3f3;
    }
    .caption{
      padding:10px 6px 2px;
      font-weight:800;
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap:10px;
    }
    .sparkle{
      background: rgba(123,92,255,.12);
      padding:6px 10px;
      border-radius:999px;
      font-size:13px;
      font-weight:900;
    }

    /* sections */
    .grid2{
      display:grid;
      grid-template-columns: 1fr 1fr;
      gap:18px;
      margin-top:18px;
    }
    @media (max-width:900px){
      .grid2{ grid-template-columns:1fr; }
    }

    .sectionTitle{
      margin:0 0 10px;
      font-size:22px;
    }
    .storyLine{
      display:grid;
      gap:10px;
      font-weight:700;
      line-height:1.4;
    }
    .chip{
      display:inline-flex;
      gap:8px;
      align-items:center;
      background: rgba(255,119,183,.10);
      border:1px solid rgba(255,119,183,.18);
      padding:10px 12px;
      border-radius:16px;
    }

    /* love letter modal */
    .modalBackdrop{
      position:fixed;
      inset:0;
      background: rgba(0,0,0,.40);
      display:none;
      align-items:center;
      justify-content:center;
      padding:16px;
      z-index:200;
    }
    .modal{
      width:min(720px, 100%);
      background: #fff;
      border-radius:26px;
      box-shadow: 0 30px 90px rgba(0,0,0,.35);
      border: 1px solid rgba(0,0,0,.10);
      overflow:hidden;
    }
    .modalHead{
      padding:14px 16px;
      display:flex;
      align-items:center;
      justify-content:space-between;
      background: linear-gradient(135deg, rgba(255,119,183,.18), rgba(123,92,255,.16));
      border-bottom:1px solid rgba(0,0,0,.06);
    }
    .modalHead strong{
      font-size:18px;
    }
    .modalBody{
      padding:16px;
      line-height:1.6;
      font-weight:700;
    }
    .closeBtn{
      background: rgba(255,255,255,.9);
      border:1px solid rgba(0,0,0,.10);
      padding:8px 12px;
      border-radius:999px;
      font-weight:900;
    }

    /* music player */
    .player{
      display:flex;
      gap:10px;
      align-items:center;
      flex-wrap:wrap;
      margin-top:10px;
    }
    .meter{
      flex:1;
      min-width:180px;
      height:12px;
      border-radius:999px;
      background: rgba(0,0,0,.08);
      overflow:hidden;
      border:1px solid rgba(0,0,0,.06);
    }
    .fill{
      width:0%;
      height:100%;
      border-radius:999px;
      background: linear-gradient(90deg, var(--pink), var(--violet));
      transition: width .2s linear;
    }
    .tiny{
      font-size:13px;
      opacity:.85;
      font-weight:800;
    }

    /* C++ cute box */
    pre{
      margin:0;
      padding:14px;
      background: #111018;
      color:#fff;
      border-radius:18px;
      overflow:auto;
      border:1px solid rgba(255,255,255,.08);
      box-shadow: 0 18px 34px rgba(0,0,0,.20);
    }
    .codeTag{
      display:inline-flex;
      align-items:center;
      gap:8px;
      background: rgba(123,92,255,.12);
      border:1px solid rgba(123,92,255,.18);
      padding:8px 10px;
      border-radius:999px;
      font-weight:900;
      margin-bottom:10px;
    }

    footer{
      margin-top:18px;
      text-align:center;
      opacity:.85;
      font-weight:800;
    }
  </style>
</head>

<body>
  <!-- floating hearts -->
  <div class="hearts" id="hearts"></div>

  <header>
    <div class="nav">
      <div class="logo">
        <span class="badge">Valentine • Ko Ko ♡ Babe</span>
      </div>
      <nav style="display:flex; gap:6px; flex-wrap:wrap; justify-content:flex-end;">
        <a href="#story">Our Story</a>
        <a href="#memories">Memories</a>
        <a href="#letter">Love Letter</a>
        <a href="#code">C++ Love</a>
      </nav>
    </div>
  </header>

  <main>
    <!-- HERO -->
    <section class="hero">
      <div class="panel">
        <h1 class="title">Hey Babe 💖</h1>
        <p class="subtitle">
          This little pink website is my Valentine gift to you —
          cute, soft, and full of us.
        </p>

        <div class="pillRow">
          <div class="pill"><span class="dot"></span> Forever-ish vibes</div>
          <div class="pill"><span class="dot"></span> Cartoon + pastel</div>
          <div class="pill"><span class="dot"></span> Just you & me</div>
        </div>

        <div class="pillRow">
          <div class="pill">
            <span class="dot"></span>
            Days together: <span id="daysTogether" style="font-weight:900; margin-left:6px;">0</span>
          </div>
          <div class="pill">
            <span class="dot"></span>
            Next Valentine: <span id="countdown" style="font-weight:900; margin-left:6px;">—</span>
          </div>
        </div>

        <div class="buttons">
          <button class="btnPrimary" id="openLetterBtn">Open My Love Letter 💌</button>
          <button class="btnGhost" id="confettiBtn">Make It Cute ✨</button>
          <button class="btnGhost" id="musicBtn">Play “Perfect” 🎵</button>
        </div>

        <div class="player">
          <div class="meter" aria-label="song progress">
            <div class="fill" id="progressFill"></div>
          </div>
          <div class="tiny" id="songStatus">Tip: add <b>perfect.mp3</b> in the same folder.</div>
        </div>

        <!-- Put your own audio file named perfect.mp3 -->
        <audio id="song" preload="metadata">
          <source src="perfect.mp3" type="audio/mpeg">
        </audio>
      </div>

      <div class="polaroids">
        <div class="polaroid" id="memories">
          <img class="photo" src="IMG_8345.jpeg" alt="Our hands photo" />
          <div class="caption">
            <span>Our hands 🤍</span>
            <span class="sparkle">memory #1</span>
          </div>
        </div>

        <div class="polaroid">
          <img class="photo" src="IMG_8372.jpeg" alt="Our selfie photo" />
          <div class="caption">
            <span>Our moment 🥹</span>
            <span class="sparkle">memory #2</span>
          </div>
        </div>
      </div>
    </section>

    <!-- STORY + PROMISES -->
    <section class="grid2" id="story">
      <div class="panel">
        <h2 class="sectionTitle">Our Story (the cute version) 🧸</h2>
        <div class="storyLine">
          <div class="chip">🌸 <span>We met… and my world got softer.</span></div>
          <div class="chip">📞 <span>Every call feels like home.</span></div>
          <div class="chip">🌙 <span>Even distance can’t shrink my love.</span></div>
          <div class="chip">🫶 <span>One day… no more screens. Just us.</span></div>
        </div>
        <p class="tiny" style="margin-top:10px;">
          (You can edit these lines in the HTML to match your real story.)
        </p>
      </div>

      <div class="panel" id="letter">
        <h2 class="sectionTitle">Tiny Promises 💜</h2>
        <div class="storyLine">
          <div class="chip">💖 <span>I will always choose you.</span></div>
          <div class="chip">🧁 <span>I’ll make you laugh when you’re tired.</span></div>
          <div class="chip">🎁 <span>More surprises… not just Valentine.</span></div>
          <div class="chip">🌷 <span>Next time: real flowers, in person.</span></div>
        </div>
      </div>
    </section>

    <!-- C++ LOVE -->
    <section class="grid2" id="code">
      <div class="panel">
        <h2 class="sectionTitle">C++ Love Algorithm (for Babe) 💻💗</h2>
        <div class="codeTag">👨‍💻 Written with love in C++</div>
        <pre id="cppBox"></pre>
        <p class="tiny" style="margin-top:10px;">
          This doesn’t run in the browser — it’s just a cute “love code” memory 💞
        </p>
      </div>

      <div class="panel">
        <h2 class="sectionTitle">Reasons I Love You 🌹</h2>
        <div class="storyLine" id="reasons">
          <!-- JS will fill -->
        </div>
        <div class="buttons" style="margin-top:12px;">
          <button class="btnPrimary" id="newReasonBtn">Give Me One More Reason 💘</button>
          <button class="btnGhost" id="copyLinkBtn">Copy Website Message 🔗</button>
        </div>
        <p class="tiny" id="copyHint" style="margin-top:8px;"></p>
      </div>
    </section>

    <footer>
      Made by Ko Ko for Babe 💗 • Happy Valentine’s Day 🌸
    </footer>
  </main>

  <!-- LOVE LETTER MODAL -->
  <div class="modalBackdrop" id="modalBackdrop" role="dialog" aria-modal="true">
    <div class="modal">
      <div class="modalHead">
        <strong>My Love Letter to Babe 💌</strong>
        <button class="closeBtn" id="closeModalBtn">Close ✖</button>
      </div>
      <div class="modalBody" id="letterBody">
        Babe…<br><br>
        If I could, I’d hold your hand right now and tell you this softly:
        you’re my favorite person. Even when we’re far apart,
        you still feel close to my heart.<br><br>
        I made this little website so you can open it anytime you miss me.
        I want you to remember: you are loved, you are precious,
        and I’m proud of you.<br><br>
        One day, we won’t be long distance anymore.
        Until then… I’m yours. Always. 💖
        <br><br>
        — Ko Ko
      </div>
    </div>
  </div>

  <script>
    // ========= Floating hearts =========
    const hearts = document.getElementById("hearts");
    const HEART_COUNT = 24;

    function makeHeart() {
      const h = document.createElement("div");
      h.className = "heart";
      const left = Math.random() * 100;
      const size = 12 + Math.random() * 18;
      const dur = 10 + Math.random() * 16;
      const delay = Math.random() * 6;

      h.style.left = left + "vw";
      h.style.width = size + "px";
      h.style.height = size + "px";
      h.style.animationDuration = dur + "s";
      h.style.animationDelay = delay + "s";
      h.style.opacity = (0.12 + Math.random() * 0.22).toFixed(2);

      // random hue twist between pink/violet
      const hue = 320 + Math.random() * 60;
      h.style.background = `hsl(${hue}, 90%, 72%)`;
      hearts.appendChild(h);

      // remove after animation to keep DOM light
      setTimeout(() => h.remove(), (dur + delay) * 1000);
    }

    for(let i=0;i<HEART_COUNT;i++) makeHeart();
    setInterval(() => makeHeart(), 900);

    // ========= Days together + Valentine countdown =========
    // CHANGE this date to your relationship start date:
    const startDate = new Date("2024-01-01T00:00:00"); // <-- EDIT ME

    const daysTogetherEl = document.getElementById("daysTogether");
    const countdownEl = document.getElementById("countdown");

    function daysBetween(a,b){
      const ms = 24*60*60*1000;
      return Math.max(0, Math.floor((b - a) / ms));
    }

    function nextValentine(now){
      const year = now.getFullYear();
      const vThis = new Date(`${year}-02-14T00:00:00`);
      if(now <= vThis) return vThis;
      return new Date(`${year+1}-02-14T00:00:00`);
    }

    function tickCounters(){
      const now = new Date();
      daysTogetherEl.textContent = daysBetween(startDate, now);

      const v = nextValentine(now);
      const diff = v - now;

      const d = Math.max(0, Math.floor(diff / (24*60*60*1000)));
      const h = Math.max(0, Math.floor((diff / (60*60*1000)) % 24));
      const m = Math.max(0, Math.floor((diff / (60*1000)) % 60));
      countdownEl.textContent = `${d}d ${h}h ${m}m`;
    }
    tickCounters();
    setInterval(tickCounters, 1000);

    // ========= Modal =========
    const modalBackdrop = document.getElementById("modalBackdrop");
    document.getElementById("openLetterBtn").addEventListener("click", () => {
      modalBackdrop.style.display = "flex";
    });
    document.getElementById("closeModalBtn").addEventListener("click", () => {
      modalBackdrop.style.display = "none";
    });
    modalBackdrop.addEventListener("click", (e) => {
      if(e.target === modalBackdrop) modalBackdrop.style.display = "none";
    });

    // ========= Confetti hearts =========
    document.getElementById("confettiBtn").addEventListener("click", () => {
      for(let i=0;i<18;i++){
        const h = document.createElement("div");
        h.className = "heart";
        const size = 10 + Math.random() * 16;
        h.style.width = size + "px";
        h.style.height = size + "px";
        h.style.left = (10 + Math.random()*80) + "vw";
        h.style.top = (10 + Math.random()*40) + "vh";
        h.style.opacity = "0.5";
        h.style.animationDuration = (5 + Math.random()*5) + "s";
        h.style.animationDelay = "0s";
        const hue = 300 + Math.random() * 80;
        h.style.background = `hsl(${hue}, 92%, 72%)`;
        hearts.appendChild(h);
        setTimeout(() => h.remove(), 9000);
      }
    });

    // ========= Music: play local perfect.mp3 =========
    const song = document.getElementById("song");
    const musicBtn = document.getElementById("musicBtn");
    const fill = document.getElementById("progressFill");
    const songStatus = document.getElementById("songStatus");

    function fmtTime(s){
      if(!isFinite(s)) return "0:00";
      const m = Math.floor(s / 60);
      const r = Math.floor(s % 60).toString().padStart(2,"0");
      return `${m}:${r}`;
    }

    musicBtn.addEventListener("click", async () => {
      try{
        if(song.paused){
          await song.play();
          musicBtn.textContent = "Pause “Perfect” ⏸";
        }else{
          song.pause();
          musicBtn.textContent = "Play “Perfect” 🎵";
        }
      }catch(err){
        // Most common: file missing or browser autoplay blocked until user interaction
        songStatus.innerHTML = "Couldn’t play. Add <b>perfect.mp3</b> in this folder (your own copy), then click again 💗";
      }
    });

    song.addEventListener("timeupdate", () => {
      if(song.duration){
        const pct = (song.currentTime / song.duration) * 100;
        fill.style.width = pct + "%";
        songStatus.innerHTML = `Playing… <b>${fmtTime(song.currentTime)}</b> / <b>${fmtTime(song.duration)}</b>`;
      }
    });
    song.addEventListener("ended", () => {
      musicBtn.textContent = "Play “Perfect” 🎵";
      fill.style.width = "0%";
      songStatus.innerHTML = "Song ended 💞 Click play again.";
    });

    // ========= C++ code typing effect =========
    const cpp = `#include <bits/stdc++.h>
using namespace std;

int main() {
  string me = "Ko Ko";
  string you = "Babe";
  int forever = 1;

  // Love grows every day:
  long long love = 0;
  while (forever) {
    love++;
    cout << me << " loves " << you << " x" << love << "\\n";
    if (love == 214) { // Feb 14 🥹
      cout << "Happy Valentine's Day, " << you << " 💖\\n";
      break;
    }
  }
  return 0;
}`;
    const cppBox = document.getElementById("cppBox");
    let i = 0;
    function typeCpp(){
      cppBox.textContent = cpp.slice(0, i++);
      if(i <= cpp.length) requestAnimationFrame(typeCpp);
    }
    typeCpp();

    // ========= Reasons generator =========
    const reasons = [
      "You make my heart feel calm. 🥺",
      "Your smile is my favorite view. 🌸",
      "Even far away, you feel like home. 🏡",
      "You’re cute in a way I can’t explain. 💗",
      "I love how you exist… that’s enough. ✨",
      "I’m proud of you, always. 💜",
      "You are my best choice. 🫶",
      "You make my future feel bright. 🌷"
    ];
    const reasonsBox = document.getElementById("reasons");
    function renderReasons(){
      reasonsBox.innerHTML = "";
      reasons.slice(0,4).forEach(t => {
        const d = document.createElement("div");
        d.className = "chip";
        d.innerHTML = `💞 <span>${t}</span>`;
        reasonsBox.appendChild(d);
      });
    }
    renderReasons();

    document.getElementById("newReasonBtn").addEventListener("click", () => {
      const t = reasons[Math.floor(Math.random()*reasons.length)];
      const d = document.createElement("div");
      d.className = "chip";
      d.innerHTML = `💞 <span>${t}</span>`;
      reasonsBox.prepend(d);
      // keep it tidy
      while(reasonsBox.children.length > 6) reasonsBox.lastChild.remove();
    });

    // ========= Copy a sweet message =========
    document.getElementById("copyLinkBtn").addEventListener("click", async () => {
      const msg = "Babe 💗 I made a little Valentine website for you — open it and remember I’m always with you. — Ko Ko";
      try{
        await navigator.clipboard.writeText(msg);
        document.getElementById("copyHint").textContent = "Copied! Now paste it in chat/email to her 💌";
      }catch{
        document.getElementById("copyHint").textContent = "Copy blocked by browser — just manually copy from the code 😊";
      }
    });
  </script>
</body>
</html>
