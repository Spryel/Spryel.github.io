 <!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>For You ❤️</title>

<style>
body {
  margin: 0;
  height: 100vh;
  overflow: hidden;
  font-family: Arial, sans-serif;
  position: relative;
}

/* Background container that will blur */
.bg-container {
  position: absolute;
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 40px;
  flex-wrap: wrap;
  transition: filter 0.5s ease;
}

/* Blur only background */
.bg-container.blur {
  filter: blur(8px);
}

/* Envelope box */
.envelope-box {
  text-align: center;
  cursor: pointer;
  perspective: 1000px;
}

/* Envelope */
.envelope {
  width: 120px;
  height: 80px;
  background: #ff4d6d;
  position: relative;
  border-radius: 5px;
  transition: transform 0.6s;
}

/* Flap starts folded down */
.flap {
  position: absolute;
  width: 120px;
  height: 60px;
  background: #ff758c;
  top: -60px;
  clip-path: polygon(0 100%, 50% 0, 100% 100%);
  transform-origin: bottom;
  transition: transform 0.6s;
  transform: rotateX(180deg); /* flap starts closed */
}

/* Flap opens when envelope has "open" */
.envelope.open .flap {
  transform: rotateX(0deg);
}

/* Name under envelope */
.name {
  margin-top: 10px;
  color: white;
  font-weight: bold;
  text-shadow: 0 0 5px black;
}

/* Letters */
.letter-box {
  display: none;
  position: fixed;
  background: white;
  padding: 30px;
  border-radius: 20px;
  box-shadow: 0 10px 40px rgba(0,0,0,0.4);
  max-width: 400px;
  z-index: 10;
  animation: fadeIn 0.6s ease forwards;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
}

/* Fade in letters */
@keyframes fadeIn {
  0% { opacity: 0; transform: scale(0.8) translate(-50%, -50%); }
  100% { opacity: 1; transform: scale(1) translate(-50%, -50%); }
}

/* Close button */
.closeBtn {
  margin-top: 15px;
  padding: 8px 15px;
  border: none;
  border-radius: 10px;
  background: #ff4d6d;
  color: white;
  cursor: pointer;
}

/* Hearts animation */
.heart {
  position: fixed;
  color: #ff4d6d;
  font-size: 20px;
  animation: floatUp 2s linear forwards;
}

@keyframes floatUp {
  0% { opacity: 1; transform: translateY(0); }
  100% { opacity: 0; transform: translateY(-150px); }
}

/* Mobile responsive adjustments */
@media (max-width: 600px) {
  .bg-container { gap: 20px; }
  .envelope { width: 90px; height: 60px; }
  .flap { width: 90px; height: 45px; }
  .letter-box { max-width: 90%; padding: 20px; }
  .heart { font-size: 16px; }
}

/* Background gradient */
body::before {
  content: '';
  position: absolute;
  width: 100%;
  height: 100%;
  background: linear-gradient(to bottom right, #ff758c, #ff7eb3, #ffd1dc);
  z-index: -1;
}
</style>
</head>

<body>

<!-- Background music -->
<audio id="bgMusic" loop playsinline>
  <source src="aphrodite.mp3" type="audio/mpeg">
</audio>

<!-- Background container -->
<div class="bg-container" id="bgContainer">

  <div class="envelope-box" data-num="1" data-pass="Lysiee">
    <div class="envelope" id="env1">
      <div class="flap"></div>
    </div>
    <div class="name">Lysiee</div>
  </div>

  <div class="envelope-box" data-num="2" data-pass="Lyle">
    <div class="envelope" id="env2">
      <div class="flap"></div>
    </div>
    <div class="name">Vodi</div>
  </div>

  <div class="envelope-box" data-num="3" data-pass="Twin bitches">
    <div class="envelope" id="env3">
      <div class="flap"></div>
    </div>
    <div class="name">Kiers</div>
  </div>

  <div class="envelope-box" data-num="4" data-pass="dudung clark">
    <div class="envelope" id="env4">
      <div class="flap"></div>
    </div>
    <div class="name">Clark</div>
  </div>

</div>

<!-- LETTERS -->
<div id="letter1" class="letter-box">
<h2>To Lysiee 💗</h2>
<p>I just wanted you to know that sorry kaayu sa akong na buhat and i will try every possible way to not do it again and ma aware nas akong words you know i'm still learning the way how humors work in your place. ik mali akong gibuhat i walang ko nag expect na ingato ilang reaction because na anad ko diris amoa na dili ingana ang reactions. so sorry kaayu i hope okay nani akong gi buhat na effort para sa apology letters.</p>
<button class="closeBtn" onclick="closeLetter()">Close</button>
</div>

<div id="letter2" class="letter-box">
<h2>To Vodi 💗</h2>
<p>Hi or hello vodi i just wanted to let you know na sorry sa akong gipang ingun about ato na bae i'll take it back ik mali ko wala lang jud ko na aware na ingatu diay mahitabu and ik bad akong gipang ingun. peru naanad naman kos amoa diri na normal nana so sorry kaayu hope you understand and maka forgive pabaka nako ma friend or dili na and i'll accept it i'm the one who did a mistake that hurts someone. sorry kaay usa tanan (sorry sa english bisaya ko na tao).</p>
<button class="closeBtn" onclick="closeLetter()">Close</button>
</div>

<div id="letter3" class="letter-box">
<h2>To Kiers 💗</h2>
<p>Heloo kiers akong twin bitches gibuhat tani para sainyu na morelikely apology letter bani or unsa ba gi tibu nalang nako. sorry diay sa akong nabuhat og na nalain mo nako hate bana, untag mahimaut na di na nako ma utro og mag bantay nakus mga words nako na nakasakit ato na tao so sorry kaayu sa akong na buhat og maka forgive baka nako (sorry sa english bisaya ko na tao)</p>
<button class="closeBtn" onclick="closeLetter()">Close</button>
</div>

<div id="letter4" class="letter-box">
<h2>To Clark 💗</h2>
<p>Halo baiiiiiiiii dudung clark sorry og naka nasakitan ka sa akong nabuhat or ambut lang nasakitan baka or nalain nako sorry sa akong nabuhat papart clark untag goods nata sunod perug di ako nalay mo layu peace &lt;3 Sorry sa akonng nabuhat bai mahimaut or mahintunudan nato na di na unta nako. madawat pabako nimo na amigo (bisan dili migo) sa akong nabuhat. untag enough nani akong effort.</p>
<button class="closeBtn" onclick="closeLetter()">Close</button>
</div>

<script>
// Password check with toggle
function checkPassword(num, correctPass) {
  let userPass = prompt("Enter password:");
  const envelope = document.getElementById("env"+num);
  const bg = document.getElementById("bgContainer");

  if(userPass === correctPass){
    envelope.classList.toggle("open"); // toggle open/close

    if(envelope.classList.contains("open")){
      bg.classList.add("blur");
      explodeHearts();
      openLetter(num);
    } else {
      bg.classList.remove("blur");
      closeLetter();
    }
  } else {
    alert("Wrong password 💔");
  }
}

// Open letter
function openLetter(num){
  document.getElementById("letter"+num).style.display="block";
  const music = document.getElementById("bgMusic");
  if(music.paused){
    music.play();
  }
}

// Close all letters
function closeLetter(){
  document.querySelectorAll(".letter-box").forEach(l=>l.style.display="none");
  document.getElementById("bgContainer").classList.remove("blur");
}

// Heart animation
function explodeHearts(){
  for(let i=0;i<20;i++){
    const heart = document.createElement("div");
    heart.classList.add("heart");
    heart.innerHTML="💖";
    heart.style.left=Math.random()*100+"vw";
    heart.style.top=Math.random()*100+"vh";
    document.body.appendChild(heart);
    setTimeout(()=>heart.remove(),2000);
  }
}

// Mobile-friendly click events
document.querySelectorAll('.envelope-box').forEach(box => {
  box.addEventListener('click', e => {
    const num = box.dataset.num;
    const pass = box.dataset.pass;
    checkPassword(num, pass);
  });
});
</script>

</body>
</html>
