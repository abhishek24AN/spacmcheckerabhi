# spacmcheckerabhi
IN THIS EMILS,PDF,URL,PHOTO ARE CHECK
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>SECURE-AI Cyber Dashboard</title>
<meta name="viewport" content="width=device-width, initial-scale=1">

<style>
:root{
  --bg:#060b16;
  --panel:#0e1933;
  --accent:#22e6a7;
  --blue:#3aa9ff;
  --danger:#ff4d4d;
  --warn:#ffc857;
  --text:#e6f0ff;
  --muted:#8ea2c6;
}

*{box-sizing:border-box}

body{
  margin:0;
  font-family:Segoe UI, Inter, Arial;
  background:radial-gradient(circle at top,#13203a,#060b16);
  color:var(--text);
  overflow:hidden;
}

.app{display:flex;height:100vh}

/* SIDEBAR */
.sidebar{
  width:270px;
  background:linear-gradient(180deg,#0e1933,#081126);
  padding:18px;
  overflow:auto;
}

.brand{
  display:flex;
  align-items:center;
  gap:10px;
  margin-bottom:20px;
}

.logo{
  width:36px;height:36px;
  border-radius:10px;
  background:linear-gradient(135deg,#21f3b6,#3aa9ff);
  display:flex;
  align-items:center;
  justify-content:center;
  font-weight:900;
  color:#001b2e;
  animation:pulse 2s infinite;
}

@keyframes pulse{
  0%,100%{box-shadow:0 0 0 rgba(34,230,167,0.6)}
  50%{box-shadow:0 0 15px rgba(34,230,167,0.9)}
}

.menu a{
  display:block;
  padding:10px 12px;
  margin-bottom:6px;
  border-radius:10px;
  text-decoration:none;
  color:var(--muted);
  font-size:14px;
  cursor:pointer;
}

.menu a.active,
.menu a:hover{
  background:linear-gradient(90deg,#1fe6a8,#2a7cff);
  color:#041b2e;
  font-weight:600;
}

/* TOOLBOX */
.toolbox h4{
  margin:12px 0 6px;
  font-size:14px;
  color:#9fb7ff;
}

.toolbox textarea,
.toolbox input{
  width:100%;
  background:#081126;
  border:1px solid rgba(255,255,255,0.08);
  color:white;
  border-radius:8px;
  padding:8px;
  margin-bottom:6px;
  font-size:13px;
}

.toolbox button{
  width:100%;
  padding:8px;
  border:none;
  border-radius:8px;
  background:linear-gradient(90deg,#1fe6a8,#2a7cff);
  font-weight:700;
  cursor:pointer;
  margin-bottom:12px;
}

/* MAIN */
.main{
  flex:1;
  padding:22px;
  overflow:auto;
}

.topbar{
  display:flex;
  justify-content:space-between;
  align-items:center;
  margin-bottom:14px;
}

.status{
  padding:8px 14px;
  border-radius:20px;
  background:rgba(34,230,167,0.15);
  color:var(--accent);
  font-weight:600;
}

.section{display:none}
.section.active{display:block}

/* CARDS */
.cards{
  display:grid;
  grid-template-columns:repeat(3,1fr);
  gap:16px;
  margin-bottom:18px;
}

.card{
  background:linear-gradient(180deg,#0f1a32,#0b1427);
  border-radius:16px;
  padding:16px;
  border:1px solid rgba(255,255,255,0.05);
  position:relative;
  overflow:hidden;
}

.card::after{
  content:"";
  position:absolute;
  inset:0;
  background:linear-gradient(120deg,transparent,rgba(58,169,255,0.2),transparent);
  animation:scan 4s infinite;
}

@keyframes scan{
  from{transform:translateX(-100%)}
  to{transform:translateX(100%)}
}

.big{font-size:30px;font-weight:800}
.green{color:var(--accent)}
.red{color:var(--danger)}
.yellow{color:var(--warn)}

.panel{
  background:linear-gradient(180deg,#0f1a32,#0b1427);
  border-radius:16px;
  padding:16px;
  border:1px solid rgba(255,255,255,0.05);
  margin-bottom:16px;
}

.graph{
  height:180px;
  border-radius:12px;
  background:
    linear-gradient(180deg,transparent,rgba(58,169,255,0.2)),
    repeating-linear-gradient(
      to right,
      rgba(255,255,255,0.05) 0,
      rgba(255,255,255,0.05) 1px,
      transparent 1px,
      transparent 40px
    );
}

.feed p{font-size:13px;margin:8px 0;color:var(--muted)}
.feed span{color:var(--danger);font-weight:600}

a.gov{
  color:#7dc4ff;
  font-weight:600;
  text-decoration:none;
}
</style>
</head>

<body>

<div class="app">

<!-- SIDEBAR -->
<aside class="sidebar">
  <div class="brand">
    <div class="logo">SG</div>
    <strong>SECURE-AI</strong>
  </div>

  <div class="menu">
    <a class="active" onclick="showSection('overview',this)">Overview</a>
    <a onclick="showSection('map',this)">Threat Map</a>
    <a onclick="showSection('logs',this)">AI Logs</a>
    <a onclick="showSection('victim',this)">Victim Help</a>
    <a onclick="showSection('settings',this)">Settings</a>
  </div>

  <div class="toolbox">
    <h4>Email Scam Checker</h4>
    <textarea id="emailInput" placeholder="Paste email text"></textarea>
    <button onclick="checkEmail()">Analyze Email</button>

    <h4>Link Scam Checker</h4>
    <input id="linkInput" placeholder="https://example.com">
    <button onclick="checkLink()">Check Link</button>

    <h4>PDF Inspector</h4>
    <input id="pdfInput" type="file">
    <button onclick="checkPDF()">Inspect PDF</button>

    <h4>Image Checker</h4>
    <input id="imageInput" type="file">
    <button onclick="checkImage()">Verify Image</button>
  </div>
</aside>

<!-- MAIN -->
<main class="main">

<div class="topbar">
  <h2>Dashboard</h2>
  <div class="status">AI ACTIVE</div>
</div>

<!-- OVERVIEW -->
<div id="overview" class="section active">

  <div class="cards">
    <div class="card">
      <h4>Risk Score</h4>
      <div class="big green" id="risk">12%</div>
    </div>
    <div class="card">
      <h4>Active Threats</h4>
      <div class="big red" id="threats">3</div>
    </div>
    <div class="card">
      <h4>AI Prediction</h4>
      <div class="big yellow" id="prediction">Normal</div>
    </div>
  </div>

  <div class="panel">
    <h4>Security Health</h4>
    <p>Overall Protection Level: <strong class="green">88% (Good)</strong></p>
    <p>↓ Risk increased due to phishing attempts</p>
  </div>

  <div class="panel">
    <h4>Top Threats Today</h4>
    <p>• Phishing Emails – 42%</p>
    <p>• Malicious Links – 31%</p>
    <p>• Fake Job Offers – 18%</p>
    <p>• Malware PDFs – 9%</p>
  </div>

  <div class="panel">
    <h4>User Impact Summary</h4>
    <p>Users Protected: 124</p>
    <p>Potential Loss Prevented: ₹3,45,000</p>
    <p>Average Response Time: 2.4 seconds</p>
  </div>
</div>

<!-- THREAT MAP -->
<div id="map" class="section">
  <div class="panel" style="height:300px">
    Global Threat Map (Demo)<br><br>
    • India – Banking Phishing<br>
    • USA – Bot Activity<br>
    • Singapore – Normal
  </div>
</div>

<!-- LOGS -->
<div id="logs" class="section">
  <div class="panel feed">
    <p><span>[HIGH]</span> Phishing email blocked</p>
    <p><span>[MED]</span> Suspicious URL detected</p>
    <p><span>[LOW]</span> New device login</p>
  </div>
</div>

<!-- VICTIM HELP -->
<div id="victim" class="section">
  <div class="panel">
    <h4>Victim Help / Response Center</h4>
    <p>If you are a victim of cyber fraud:</p>
    <p>1. Do not share OTP or passwords</p>
    <p>2. Preserve emails, screenshots, logs</p>
    <p>3. Call Cyber Crime Helpline <strong>1930</strong></p>
    <p>4. File complaint on official portal</p>

    <a class="gov" href="https://cybercrime.gov.in" target="_blank">
      ➜ National Cyber Crime Reporting Portal
    </a>
  </div>
</div>

<!-- SETTINGS -->
<div id="settings" class="section">
  <div class="panel">
    <p>✔ Enable Real-Time Monitoring</p>
    <p>✔ Auto Incident Logging</p>
    <p>✔ Government Reporting Integration</p>
    <p>✔ Email & SMS Alerts</p>
  </div>
</div>

</main>
</div>

<script>
let currentRisk = 12;

function showSection(id,el){
  document.querySelectorAll('.section')
    .forEach(s=>s.classList.remove('active'));
  document.getElementById(id).classList.add('active');

  document.querySelectorAll('.menu a')
    .forEach(a=>a.classList.remove('active'));
  el.classList.add('active');
}

function updateDisplay(){
  document.getElementById('risk').innerText = currentRisk + '%';
  
  if(currentRisk < 30) {
    document.getElementById('risk').className = 'big green';
    document.getElementById('prediction').innerText = 'Safe';
    document.getElementById('threats').innerText = '0';
  } else if(currentRisk < 60) {
    document.getElementById('risk').className = 'big yellow';
    document.getElementById('prediction').innerText = 'Medium Risk';
    document.getElementById('threats').innerText = '2';
  } else {
    document.getElementById('risk').className = 'big red';
    document.getElementById('prediction').innerText = 'High Risk';
    document.getElementById('threats').innerText = '5';
  }
}

function checkEmail(){
  const text = document.getElementById('emailInput').value;
  if(!text) {
    alert('Please paste email text');
    return;
  }
  currentRisk = Math.min(100, currentRisk + 15);
  updateDisplay();
  alert('✓ Email analyzed. Risk increased by 15%');
  document.getElementById('emailInput').value = '';
}

function checkLink(){
  const link = document.getElementById('linkInput').value;
  if(!link) {
    alert('Please enter a URL');
    return;
  }
  currentRisk = Math.min(100, currentRisk + 20);
  updateDisplay();
  alert('⚠ Suspicious URL detected. Risk increased by 20%');
  document.getElementById('linkInput').value = '';
}

function checkPDF(){
  const file = document.getElementById('pdfInput').value;
  if(!file) {
    alert('Please select a PDF');
    return;
  }
  currentRisk = Math.min(100, currentRisk + 18);
  updateDisplay();
  alert('⚠ Malicious signature found. Risk increased by 18%');
  document.getElementById('pdfInput').value = '';
}

function checkImage(){
  const file = document.getElementById('imageInput').value;
  if(!file) {
    alert('Please select an image');
    return;
  }
  currentRisk = Math.min(100, currentRisk + 12);
  updateDisplay();
  alert('✓ EXIF data detected. Risk increased by 12%');
  document.getElementById('imageInput').value = '';
}

// Initialize display on load
window.onload = function() {
  updateDisplay();
};
</script>

</body>
</html>
