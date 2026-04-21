<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Jocelyn Semillano - Enchanted Portfolio</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700;800&display=swap" rel="stylesheet">
    <script src="https://cdn.tailwindcss.com"></script>

    <style>
        /* ✨ Magical Background & Animations */
        body {
            font-family: 'Poppins', sans-serif;
            margin: 0;
            color: white;
            overflow-x: hidden;
            min-height: 100vh;
            background: radial-gradient(circle at top, #2b003a, #0a0015 80%);
        }

        .mist {
            position: fixed;top:0;left:0;width:100%;height:100%;
            background: radial-gradient(circle, rgba(255,182,193,0.2), transparent 70%), radial-gradient(circle, rgba(255,105,180,0.15), transparent 60%);
            background-size: 2000px 2000px;
            animation: swirl 60s linear infinite;
            z-index:-3;pointer-events:none;
        }
        @keyframes swirl {0%{background-position:0 0;}100%{background-position:1000px 1000px;}}

        .stars {position:fixed;width:100%;height:100%;background:transparent url('https://www.transparenttextures.com/patterns/stardust.png') repeat;opacity:.7;z-index:-2;}

        .magic-frame::before {
            content:"";position:fixed;top:0;left:0;width:100%;height:100%;
            border-radius:25px;box-shadow:0 0 40px 10px #ff66cc;
            animation:pulse 6s ease-in-out infinite alternate;
            pointer-events:none;z-index:-1;
        }
        @keyframes pulse{0%{opacity:.7;box-shadow:0 0 20px 5px #ff66cc;}100%{opacity:1;box-shadow:0 0 60px 20px #ff99ff;}}

        .glow-text{text-shadow:0 0 10px #ff99ff,0 0 20px #ff66cc;}
        .glow-border{box-shadow:0 0 15px 4px #ff66ff;transition:.3s; overflow: hidden; }
        .glow-border:hover{box-shadow:0 0 30px 10px #ff99ff;transform:scale(1.03);}

        @keyframes float{0%,100%{transform:translateY(0);}50%{transform:translateY(-10px);}}
        .float{animation:float 6s ease-in-out infinite;}

        /* 🤖 Chatbot UI */
        #chat-container {
            position: fixed; bottom: 90px; right: 20px; width: 320px; max-height: 450px;
            background: rgba(26, 0, 51, 0.98); border: 2px solid #ff66cc; border-radius: 15px;
            display: flex; flex-direction: column; z-index: 1000; box-shadow: 0 0 25px #ff66cc; display: none;
        }
        #chat-header {
            background: linear-gradient(to right, #ff66cc, #b026ff); padding: 12px;
            border-radius: 12px 12px 0 0; font-weight: bold; display: flex; justify-content: space-between; align-items: center;
        }
        #chat-messages { flex: 1; padding: 15px; overflow-y: auto; font-size: 0.85rem; display: flex; flex-direction: column; gap: 10px; }
        .bot-msg { background: rgba(255, 102, 204, 0.2); color: #ffccff; padding: 8px 12px; border-radius: 15px 15px 15px 0; align-self: flex-start; max-width: 85%; border-left: 3px solid #ff66cc; }
        .user-msg { background: rgba(255, 255, 255, 0.1); color: #fff; padding: 8px 12px; border-radius: 15px 15px 0 15px; align-self: flex-end; max-width: 85%; }
        #chat-input-area { display: flex; padding: 12px; border-top: 1px solid rgba(255, 102, 204, 0.3); }
        #chat-input { flex: 1; background: rgba(0,0,0,0.3); border: 1px solid #ff66cc; border-radius: 20px; color: white; padding: 8px 15px; outline: none; }
        #chat-toggle {
            position: fixed; bottom: 20px; right: 20px; background: linear-gradient(45deg, #ff66cc, #b026ff);
            width: 60px; height: 60px; border-radius: 50%; display: flex; align-items: center; justify-content: center;
            cursor: pointer; z-index: 1001; box-shadow: 0 0 20px #ff66cc; font-size: 30px;
        }
    </style>
</head>
<body>

<div class="mist"></div>
<div class="stars"></div>
<div class="magic-frame"></div>

<nav class="py-3 px-2 text-center text-white font-bold flex flex-wrap justify-center gap-3 sticky top-0 z-50 bg-pink-700/40 backdrop-blur-md">
    <a href="#home">Home</a>
    <a href="#about">About</a>
    <a href="#resume">Resume</a>
    <a href="#certificates">Certificates</a>
    <a href="#simulation">Simulation</a>
    <a href="#projects">Projects</a>
    <a href="#contact">Contact</a>
</nav>

<section id="home" class="flex flex-col items-center text-center px-4 py-16">
    <h1 class="text-4xl font-bold mb-6 glow-text">Welcome to My Portfolio!</h1>
    <img src="Just me.jpg" alt="Celyn" class="w-40 h-40 rounded-full border-4 border-pink-500 object-cover glow-border float">
</section>

<section id="about" class="text-center px-4 py-12">
    <h2 class="text-3xl font-bold mb-6 text-pink-400 glow-text">✨ About Me ✨</h2>
    <p class="max-w-2xl mx-auto text-gray-200">I am Jocelyn Semillano, a 2nd Year BSIT Student. I specialize in frontend development and creative digital design.</p>
</section>

<section id="simulation" class="text-center px-4 py-12">
    <h2 class="text-3xl font-bold mb-10 text-pink-300 glow-text">🧪 BSIT-2B Attendance System</h2>
    <div class="max-w-4xl mx-auto bg-[#1a0033]/80 border border-pink-500 rounded-3xl p-6 shadow-lg">
        <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-8">
            <div class="bg-white/5 p-4 rounded-2xl border border-pink-400/30">
                <h4 class="text-pink-300 font-bold mb-4">Girls 🌸</h4>
                <div id="girlsList" class="space-y-2 text-left h-64 overflow-y-auto pr-2"></div>
            </div>
            <div class="bg-white/5 p-4 rounded-2xl border border-blue-400/30">
                <h4 class="text-blue-300 font-bold mb-4">Boys 💎</h4>
                <div id="boysList" class="space-y-2 text-left h-64 overflow-y-auto pr-2"></div>
            </div>
        </div>
        <button onclick="generateSummary()" class="px-16 py-3 bg-pink-600 rounded-full font-bold hover:bg-pink-700 transition">DONE ✨</button>
        <div id="summaryPanel" class="hidden mt-8 p-6 bg-black/60 rounded-2xl border border-pink-500 text-left">
            <h3 class="text-xl font-bold text-pink-400 text-center mb-4">Attendance Report</h3>
            <div id="reportContent" class="grid grid-cols-2 gap-4"></div>
        </div>
    </div>
</section>

<div id="chat-toggle" onclick="toggleChat()">🤖</div>
<div id="chat-container">
    <div id="chat-header"><span>Celyn's Bot</span><button onclick="toggleChat()">✖</button></div>
    <div id="chat-messages"><div class="bot-msg">✨ Hi! I am Celyn's automated assistant. Ask me anything about her projects or IT skills!</div></div>
    <div id="chat-input-area"><input type="text" id="chat-input" placeholder="Ask about projects, skills..." onkeypress="handleChat(event)"></div>
</div>

<script>
    // --- ATTENDANCE SYSTEM LOGIC ---
    const girls = ["Jocelyn Semillano","Andrea Jean Occeña","Gene Mae Caramihan","Jessa Erosido","Jessa Hilardino","Kristine Joy Basa","Lena Bahian","Rechelle An Casilangan","Roxan Pracio","Shannon De La Cruz"];
    const boys = ["Archie Vidal","John Rogen Bullag","Mario Nebres Jr.","Anthony Espinosa","Dave Rivera","Kenneth Espinosa"];

    function renderList(list, id) {
        const el = document.getElementById(id);
        list.sort().forEach(n => {
            el.innerHTML += `<div class="flex justify-between p-2 bg-white/5 rounded mb-1"><span>${n}</span><input type="checkbox" class="att-check" data-name="${n}"></div>`;
        });
    }
    renderList(girls, 'girlsList'); renderList(boys, 'boysList');

    function generateSummary() {
        const checks = document.querySelectorAll('.att-check');
        let p = [], a = [];
        checks.forEach(c => { if(c.checked) p.push(c.dataset.name); else a.push(c.dataset.name); });
        document.getElementById('reportContent').innerHTML = `<div><b class="text-green-400">Present: ${p.length}</b><p class="text-xs">${p.join(', ')}</p></div><div><b class="text-red-400">Absent: ${a.length}</b><p class="text-xs">${a.join(', ')}</p></div>`;
        document.getElementById('summaryPanel').classList.remove('hidden');
    }

    // --- AUTOMATED CHATBOT LOGIC ---
    function toggleChat() {
        const chat = document.getElementById('chat-container');
        chat.style.display = (chat.style.display === 'none' || chat.style.display === '') ? 'flex' : 'none';
    }

    function handleChat(e) {
        if (e.key === 'Enter') {
            const input = document.getElementById('chat-input');
            const msg = input.value.trim();
            if (msg) { addMessage(msg, 'user-msg'); input.value = ''; setTimeout(() => botResponse(msg), 600); }
        }
    }

    function addMessage(t, c) {
        const d = document.createElement('div'); d.className = c; d.innerText = t;
        const m = document.getElementById('chat-messages'); m.appendChild(d); m.scrollTop = m.scrollHeight;
    }

    function botResponse(u) {
        let r = "";
        const t = u.toLowerCase();

        // Automated Logic for All Inquiries
        if (t.includes("hi") || t.includes("hello")) r = "Hello! ✨ How can I help you explore Celyn's work?";
        else if (t.includes("project")) r = "Celyn has projects like the Chessboard UI, T-shirt designs, and Figma prototypes. Check the 'Projects' section! 🛠️";
        else if (t.includes("attendance")) r = "The BSIT-2B Attendance System is an automated tool she built. You can test it in the Simulation section! 🧪";
        else if (t.includes("skills")) r = "Celyn is skilled in HTML, CSS, PHP, MySQL, Figma, and Canva. 🪄";
        else if (t.includes("who is") || t.includes("about")) r = "Celyn is a 2nd Year BSIT Student passionate about web development and IT! 👩‍💻";
        else if (t.includes("resume")) r = "You can view or download her full resume in the 'Resume' section. 📄";
        else if (t.includes("what is it") || t.includes("information technology")) r = "IT is the use of systems and telecommunications for storing, retrieving, and sending information. It is Celyn's field of study!";
        else if (t.includes("thank")) r = "You're welcome! Feel free to ask more. ✨";
        else {
            const generic = ["I'm not sure, but I can tell you about Celyn's projects! 🛠️", "Try asking about her 'Skills' or 'Attendance System'. ✨", "That sounds interesting! 🪄"];
            r = generic[Math.floor(Math.random() * generic.length)];
        }
        addMessage(r, 'bot-msg');
    }
</script>
</body>
</html>
