<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Jocelyn Semillano - Enchanted Portfolio</title>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700;800&display=swap" rel="stylesheet">
<script src="https://cdn.tailwindcss.com"></script>

<style>
/* ✨ Body & Background */
body {
  font-family: 'Poppins', sans-serif;
  margin: 0;
  color: white;
  overflow-x: hidden;
  min-height: 100vh;
  background: radial-gradient(circle at top, #2b003a, #0a0015 80%);
}

/* ✨ Animated mist */
@keyframes swirl {0%{background-position:0 0;}100%{background-position:1000px 1000px;}}
.mist {
  position: fixed;top:0;left:0;width:100%;height:100%;
  background: radial-gradient(circle, rgba(255,182,193,0.2), transparent 70%), radial-gradient(circle, rgba(255,105,180,0.15), transparent 60%);
  background-size: 2000px 2000px;
  animation: swirl 60s linear infinite;
  z-index:-3;pointer-events:none;
}

/* ✨ Stars + sparkles */
.stars {position:fixed;width:100%;height:100%;background:transparent url('https://www.transparenttextures.com/patterns/stardust.png') repeat;opacity:.7;z-index:-2;}
.sparkles {position:fixed;top:0;left:0;width:100%;height:100%;background:transparent url() repeat;background-size:cover;mix-blend-mode:screen;opacity:.3;animation:drift 20s linear infinite;z-index:-1;}
@keyframes drift{0%{transform:translate(0,0);}50%{transform:translate(-20px,20px);}100%{transform:translate(20px,-20px);}}

/* ✨ Magical frame */
.magic-frame::before {
  content:"";position:fixed;top:0;left:0;width:100%;height:100%;
  border-radius:25px;box-shadow:0 0 40px 10px #ff66cc;
  animation:pulse 6s ease-in-out infinite alternate;
  pointer-events:none;z-index:-1;
}
@keyframes pulse{0%{opacity:.7;box-shadow:0 0 20px 5px #ff66cc;}100%{opacity:1;box-shadow:0 0 60px 20px #ff99ff;}}

/* ✨ Text glow */
.glow-text{text-shadow:0 0 10px #ff99ff,0 0 20px #ff66cc;}
.glow-border{box-shadow:0 0 15px 4px #ff66ff;transition:.3s;}
.glow-border:hover{box-shadow:0 0 30px 10px #ff99ff;transform:scale(1.03);}

/* ✨ Floating animation */
@keyframes float{0%,100%{transform:translateY(0);}50%{transform:translateY(-10px);}}
.float{animation:float 6s ease-in-out infinite;}

/* ✨ Scrollbar */
::-webkit-scrollbar{width:6px;}::-webkit-scrollbar-thumb{background:#ff66ff;border-radius:4px;}
section{scroll-margin-top:80px;}
</style>
</head>

<body>

<div class="mist"></div>
<div class="stars"></div>
<div class="sparkles"></div>
<div class="magic-frame"></div>

<nav class="py-3 px-2 text-center text-white font-bold text-sm sm:text-base flex flex-wrap justify-center gap-3 sticky top-0 z-50 bg-pink-700/40 backdrop-blur-md">
  <a href="#home">Home</a>
  <a href="#about">About</a>
  <a href="#resume">Resume</a>
  <a href="#certificates">Certificates</a>
  <a href="#simulation">Simulation</a>
  <a href="#skills">Skills</a>
  <a href="#experience">Experience</a>
  <a href="#tutorials">Tutorials</a>
  <a href="#contact">Contact</a>
</nav>

<section id="home" class="flex flex-col items-center text-center px-4 py-16">
  <h1 class="text-3xl sm:text-4xl font-bold mb-6 glow-text whitespace-nowrap">Welcome to My Portfolio!</h1>
  <img src="images/Just me.jpg" class="w-40 h-40 rounded-full border-4 border-pink-500 object-cover glow-border float">
</section>

<section id="resume" class="text-center px-4 py-12">
  <h2 class="text-3xl font-bold mb-8 text-pink-400 glow-text">📄 My Resume</h2>
  <div class="max-w-xs mx-auto bg-[#1a0033]/70 border border-pink-500 rounded-2xl p-4 glow-border float">
    <img src="images/resume.jpg" class="w-full rounded-lg mb-4">
    <a href="images/resume.jpg" download class="inline-block py-2 px-6 bg-pink-600 rounded-lg">Download</a>
  </div>
</section>

<section id="certificates" class="text-center px-4 py-12">
  <h2 class="text-3xl font-bold mb-8 text-pink-400 glow-text">📜 Certificates</h2>

  <div class="max-w-2xl mx-auto space-y-6">

    <div class="bg-[#1a0033]/70 p-4 rounded glow-border">
      <p>March 10, 2026</p>
      <img src="images/March 10.jpg" class="w-full rounded">
    </div>

    <div class="bg-[#1a0033]/70 p-4 rounded glow-border">
      <p>March 12, 2026</p>
      <img src="images/March 12.jpg" class="w-full rounded">
    </div>

  </div>
</section>

</body>
</html>
