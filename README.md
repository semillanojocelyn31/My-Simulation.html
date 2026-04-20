<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>BSIT-2B Attendance System</title>

<style>
body {
    margin: 0;
    font-family: 'Poppins', sans-serif;
    background: radial-gradient(circle at top, #3a0a3f, #0f0015 70%);
    overflow-x: hidden;
    color: white;
    display: flex;
    flex-direction: column;
    align-items: center;
    min-height: 100vh;
    padding: 20px;
    position: relative;
}

/* BACKGROUND EFFECTS */
body::before {
    content: "";
    position: fixed;
    width: 200%;
    height: 200%;
    background: linear-gradient(-45deg, #ff00cc, #ff66cc, #6a00ff, #ff00cc);
    background-size: 400% 400%;
    animation: gradientMove 12s ease infinite;
    opacity: 0.25;
    z-index: -2;
}

@keyframes gradientMove {
    0% { transform: translate(0,0); }
    50% { transform: translate(-25%, -25%); }
    100% { transform: translate(0,0); }
}

/* FLOATING BLOBS */
body::after {
    content: "";
    position: fixed;
    width: 100%;
    height: 100%;
    background:
        radial-gradient(circle, rgba(255,0,200,0.4) 0%, transparent 60%) 20% 30%,
        radial-gradient(circle, rgba(255,102,204,0.3) 0%, transparent 60%) 70% 60%,
        radial-gradient(circle, rgba(106,0,255,0.3) 0%, transparent 60%) 50% 80%;
    animation: floatBlobs 15s infinite alternate ease-in-out;
    z-index: -1;
}

@keyframes floatBlobs {
    0% { transform: translateY(0px); }
    50% { transform: translateY(-40px); }
    100% { transform: translateY(20px); }
}

/* SPARKLES */
.sparkle {
    position: fixed;
    width: 2px;
    height: 2px;
    background: white;
    box-shadow: 0 0 8px white, 0 0 12px #ff66cc;
    animation: sparkleAnim 3s infinite ease-in-out;
}

@keyframes sparkleAnim {
    0%,100% { opacity: 0.2; transform: scale(1); }
    50% { opacity: 1; transform: scale(2); }
}

h1 {
    text-shadow: 0 0 20px #ff7eb3, 0 0 40px #ff00cc;
}

/* TOP CONTROLS */
.controls-top {
    display: flex;
    gap: 15px;
    margin-bottom: 25px;
    background: rgba(255,255,255,0.12);
    padding: 15px;
    border-radius: 20px;
}

input[type="date"], .subject-input {
    background: rgba(0,0,0,0.5);
    border: 1px solid #ff00cc;
    color: white;
    padding: 10px;
    border-radius: 10px;
}

/* LIST */
.container {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
    justify-content: center;
}

.section {
    width: 350px;
    padding: 20px;
    border-radius: 25px;
    background: rgba(255,255,255,0.08);
}

.member-row {
    display: flex;
    justify-content: space-between;
    padding: 10px;
    margin: 8px 0;
    border-radius: 12px;
}

.switch { position: relative; width: 40px; height: 20px; }
.switch input { display: none; }

.slider {
    position: absolute;
    background: #555;
    width: 100%;
    height: 100%;
    border-radius: 20px;
}

.slider:before {
    content: "";
    position: absolute;
    width: 14px;
    height: 14px;
    left: 3px;
    bottom: 3px;
    background: white;
    border-radius: 50%;
    transition: 0.3s;
}

input:checked + .slider {
    background: #ff00cc;
}

input:checked + .slider:before {
    transform: translateX(20px);
}

/* DONE BUTTON FIXED */
.done-container {
    margin-top: 40px;
    margin-bottom: 70px;
    width: 100%;
    display: flex;
    justify-content: center;
}

.done-btn {
    width: 90%;
    max-width: 350px;
    background: linear-gradient(90deg, #ff00cc, #ff66cc);
    padding: 16px;
    border-radius: 50px;
    border: none;
    color: white;
    font-size: 1.3rem;
    font-weight: bold;
}

/* SUMMARY */
#summaryPanel {
    display: none;
    margin-top: 20px;
}
</style>
</head>

<body>

<h1>BSIT-2B Attendance</h1>

<div class="controls-top">
    <input type="date" id="attendanceDate">
    <input type="text" class="subject-input" id="subjectName" placeholder="Subject">
</div>

<div class="container">
    <div class="section">
        <h2>Girls 🌸</h2>
        <div id="girlsList"></div>
    </div>

    <div class="section">
        <h2>Boys 💎</h2>
        <div id="boysList"></div>
    </div>
</div>

<div class="done-container">
    <button class="done-btn" onclick="generateSummary()">DONE ✨</button>
</div>

<div id="summaryPanel">
    <h2>Summary</h2>
    <p id="reportMeta"></p>
</div>

<script>
const girls = ["Jocelyn Semillano","Andrea Jean Occeña","Gene Mae Caramihan"];
const boys = ["Archie Vidal","Anthony Espinosa","Mark Angelou Banatasa"];

document.getElementById('attendanceDate').valueAsDate = new Date();

function renderList(list, id){
    const el = document.getElementById(id);
    list.forEach(name=>{
        el.innerHTML += `
        <div class="member-row">
            <span>${name}</span>
            <label class="switch">
                <input type="checkbox" class="att-check">
                <span class="slider"></span>
            </label>
        </div>`;
    });
}

renderList(girls,'girlsList');
renderList(boys,'boysList');

function generateSummary(){
    document.getElementById("summaryPanel").style.display="block";
}
</script>

</body>
</html>
