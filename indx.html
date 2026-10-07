<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Skyfire: Direct 2-Player Dogfight</title>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/peerjs/1.5.4/peerjs.min.js"></script>
    <style>
        :root {
            --cyan: #00f0ff;
            --rose: #ff3366;
            --amber: #f59e0b;
            --dark-blue: #030814;
            --panel-bg: rgba(6, 16, 32, 0.94);
        }
        * {
            box-sizing: border-box;
            user-select: none;
            -webkit-user-select: none;
            margin: 0;
            padding: 0;
        }
        body {
            background-color: var(--dark-blue);
            color: #d1e4ff;
            font-family: 'Consolas', 'Courier New', monospace;
            overflow: hidden;
            width: 100vw;
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        /* Tactical CRT Scanlines */
        body::before {
            content: "";
            position: absolute;
            inset: 0;
            background: linear-gradient(rgba(18, 26, 36, 0) 50%, rgba(0, 0, 0, 0.35) 50%);
            background-size: 100% 4px;
            pointer-events: none;
            z-index: 100;
        }
        body::after {
            content: "";
            position: absolute;
            inset: 0;
            box-shadow: inset 0 0 100px rgba(0, 10, 25, 0.85);
            pointer-events: none;
            z-index: 101;
        }
        /* Modal & Panels */
        .glass-panel {
            background: var(--panel-bg);
            border: 2px solid rgba(0, 240, 255, 0.4);
            border-radius: 12px;
            box-shadow: 0 0 40px rgba(0, 240, 255, 0.25), inset 0 0 20px rgba(0, 240, 255, 0.08);
            position: relative;
            z-index: 110;
            max-width: 650px;
            width: 90%;
            padding: 28px;
        }
        .hud-bracket {
            position: relative;
        }
        .hud-bracket::before {
            content: "";
            position: absolute;
            top: -4px; left: -4px; width: 12px; height: 12px;
            border-top: 3px solid var(--cyan);
            border-left: 3px solid var(--cyan);
        }
        .hud-bracket::after {
            content: "";
            position: absolute;
            bottom: -4px; right: -4px; width: 12px; height: 12px;
            border-bottom: 3px solid var(--cyan);
            border-right: 3px solid var(--cyan);
        }
        h1 {
            font-size: 28px;
            letter-spacing: 3px;
            color: #fff;
            text-shadow: 0 0 12px rgba(0, 240, 255, 0.8);
            text-align: center;
            margin-bottom: 8px;
            text-transform: uppercase;
        }
        .subtitle {
            text-align: center;
            font-size: 12px;
            letter-spacing: 2px;
            color: var(--amber);
            margin-bottom: 22px;
            text-transform: uppercase;
        }
        /* Mission Briefing Guide */
        .briefing-box {
            background: rgba(2, 8, 20, 0.7);
            border: 1px solid rgba(0, 240, 255, 0.2);
            border-radius: 8px;
            padding: 16px;
            margin-bottom: 20px;
            font-size: 13px;
            line-height: 1.6;
        }
        .briefing-title {
            color: var(--cyan);
            font-weight: bold;
            letter-spacing: 1px;
            margin-bottom: 8px;
            display: flex;
            align-items: center;
            gap: 8px;
        }
        .briefing-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 14px;
            margin-top: 10px;
        }
        .card-p1 {
            border-left: 3px solid var(--cyan);
            padding-left: 10px;
            background: rgba(0, 240, 255, 0.05);
            padding: 8px;
            border-radius: 4px;
        }
        .card-p2 {
            border-left: 3px solid var(--rose);
            padding-left: 10px;
            background: rgba(255, 51, 102, 0.05);
            padding: 8px;
            border-radius: 4px;
        }
        .rule-badge {
            display: inline-block;
            background: rgba(245, 158, 11, 0.15);
            color: var(--amber);
            border: 1px solid var(--amber);
            border-radius: 4px;
            padding: 2px 6px;
            font-size: 11px;
            margin-top: 8px;
        }
        /* Launch Buttons */
        .btn-group {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 16px;
            margin-top: 10px;
        }
        button {
            padding: 14px 20px;
            border-radius: 6px;
            border: 2px solid transparent;
            font-family: inherit;
            font-size: 14px;
            font-weight: bold;
            letter-spacing: 1.5px;
            text-transform: uppercase;
            cursor: pointer;
            transition: all 0.15s ease-in-out;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            gap: 4px;
        }
        .btn-host {
            background: rgba(0, 240, 255, 0.15);
            border-color: var(--cyan);
            color: var(--cyan);
        }
        .btn-host:hover {
            background: rgba(0, 240, 255, 0.35);
            box-shadow: 0 0 20px rgba(0, 240, 255, 0.6);
            transform: translateY(-2px);
        }
        .btn-join {
            background: rgba(255, 51, 102, 0.15);
            border-color: var(--rose);
            color: var(--rose);
        }
        .btn-join:hover {
            background: rgba(255, 51, 102, 0.35);
            box-shadow: 0 0 20px rgba(255, 51, 102, 0.6);
            transform: translateY(-2px);
        }
        .btn-subtext {
            font-size: 10px;
            opacity: 0.8;
            letter-spacing: 0.5px;
        }
        .status-msg {
            margin-top: 16px;
            text-align: center;
            font-size: 13px;
            color: #94a3b8;
            min-height: 20px;
        }
        /* In-Game HUD */
        #gameWrapper {
            display: none;
            position: relative;
            width: 100vw;
            height: 100vh;
        }
        canvas {
            display: block;
            width: 100%;
            height: 100%;
            background: #020713;
        }
        .tactical-hud {
            position: absolute;
            top: 14px;
            left: 20px;
            right: 20px;
            display: flex;
            justify-content: space-between;
            align-items: flex-start;
            pointer-events: none;
            z-index: 50;
        }
        .pilot-card {
            background: rgba(4, 12, 24, 0.85);
            border: 1px solid rgba(0, 240, 255, 0.3);
            border-radius: 6px;
            padding: 10px 16px;
            min-width: 200px;
        }
        .pilot-card.p2 {
            border-color: rgba(255, 51, 102, 0.3);
            text-align: right;
        }
        .pilot-name {
            font-size: 12px;
            font-weight: bold;
            letter-spacing: 1px;
            margin-bottom: 4px;
        }
        .bar-wrap {
            width: 100%;
            height: 8px;
            background: #0b1528;
            border-radius: 2px;
            overflow: hidden;
            border: 1px solid #1e293b;
            margin-top: 4px;
        }
        .hp-bar {
            height: 100%;
            transition: width 0.1s linear;
        }
        .center-hud {
            text-align: center;
            background: rgba(4, 12, 24, 0.85);
            border: 1px solid rgba(245, 158, 11, 0.3);
            padding: 8px 18px;
            border-radius: 6px;
        }
    </style>
</head>
<body>

<div id="briefingModal" class="glass-panel hud-bracket">
    <h1>Skyfire: Dogfight</h1>
    <div class="subtitle">// Direct 2-Computer Aerial Engagement //</div>

    <!-- HOW TO PLAY SECTION -->
    <div class="briefing-box">
        <div class="briefing-title">
            <span>✈️</span> <span>MISSION BRIEFING & HOW TO PLAY</span>
        </div>
        <p>Take flight in a 1-on-1 aerial dogfight. Outmaneuver your opponent, manage forward thrust momentum, and score air-to-air kills with high-velocity cannons.</p>

        <div class="briefing-grid">
            <div class="card-p1">
                <strong style="color: var(--cyan);">HOST (PLAYER 1 - BLUE)</strong><br>
                • <strong>W</strong>: Engine Afterburner<br>
                • <strong>A / D</strong>: Steer Left / Right<br>
                • <strong>SPACEBAR</strong>: Fire Cannons
            </div>
            <div class="card-p2">
                <strong style="color: var(--rose);">JOIN (PLAYER 2 - RED)</strong><br>
                • <strong>UP ARROW</strong>: Engine Afterburner<br>
                • <strong>LEFT / RIGHT</strong>: Steer Left / Right<br>
                • <strong>ENTER</strong>: Fire Cannons
            </div>
        </div>

        <div class="rule-badge">
            ⚡ NO ROOM CODES: Direct P2P link. One person clicks Host, the other clicks Join!
        </div>
    </div>

    <!-- ONE-CLICK CONNECTION BUTTONS -->
    <div class="btn-group">
        <button class="btn-host" onclick="startAsHost()">
            <span>START AS HOST</span>
            <span class="btn-subtext">Player 1 (Blue Falcon)</span>
        </button>
        <button class="btn-join" onclick="startAsGuest()">
            <span>CONNECT AS GUEST</span>
            <span class="btn-subtext">Player 2 (Red Viper)</span>
        </button>
    </div>

    <div id="connectionStatus" class="status-msg">
        Select your role above to initialize tactical radar link...
    </div>
</div>

<div id="gameWrapper">
    <div class="tactical-hud">
        <!-- P1 Stats -->
        <div class="pilot-card">
            <div class="pilot-name" style="color: var(--cyan);">[P1] BLUE FALCON</div>
            <div style="font-size: 11px;">KILLS: <strong id="p1Score" style="color: #fff;">0</strong> | HULL: <span id="p1HpTxt">100%</span></div>
            <div class="bar-wrap">
                <div id="p1Bar" class="hp-bar" style="width: 100%; background: var(--cyan);"></div>
            </div>
        </div>

        <!-- Center Status -->
        <div class="center-hud">
            <div style="font-size: 11px; color: var(--amber); letter-spacing: 1px;">DIRECT RADAR LINKED</div>
            <div id="hudNotice" style="font-size: 13px; font-weight: bold; color: #fff; margin-top: 2px;">ENGAGE AT WILL</div>
        </div>

        <!-- P2 Stats -->
        <div class="pilot-card p2">
            <div class="pilot-name" style="color: var(--rose);">RED VIPER [P2]</div>
            <div style="font-size: 11px;">HULL: <span id="p2HpTxt">100%</span> | KILLS: <strong id="p2Score" style="color: #fff;">0</strong></div>
            <div class="bar-wrap">
                <div id="p2Bar" class="hp-bar" style="width: 100%; background: var(--rose); margin-left: auto;"></div>
            </div>
        </div>
    </div>

    <canvas id="gameCanvas"></canvas>
</div>

<script>
class SoundFX {
    constructor() {
        this.ctx = null;
    }
    init() {
        if (!this.ctx) {
            const AudioContext = window.AudioContext || window.webkitAudioContext;
            this.ctx = new AudioContext();
        }
        if (this.ctx.state === 'suspended') {
            this.ctx.resume();
        }
    }
    cannon() {
        if (!this.ctx) return;
        const now = this.ctx.currentTime;
        const osc = this.ctx.createOscillator();
        const gain = this.ctx.createGain();
        osc.type = 'sawtooth';
        osc.frequency.setValueAtTime(160, now);
        osc.frequency.exponentialRampToValueAtTime(35, now + 0.08);
        gain.gain.setValueAtTime(0.2, now);
        gain.gain.exponentialRampToValueAtTime(0.01, now + 0.08);
        osc.connect(gain);
        gain.connect(this.ctx.destination);
        osc.start(now);
        osc.stop(now + 0.09);
    }
    explosion() {
        if (!this.ctx) return;
        const now = this.ctx.currentTime;
        const bufferSize = this.ctx.sampleRate * 0.4;
        const buffer = this.ctx.createBuffer(1, bufferSize, this.ctx.sampleRate);
        const data = buffer.getChannelData(0);
        for (let i = 0; i < bufferSize; i++) {
            data[i] = (Math.random() * 2 - 1) * Math.exp(-i / (this.ctx.sampleRate * 0.1));
        }
        const noise = this.ctx.createBufferSource();
        noise.buffer = buffer;
        const filter = this.ctx.createBiquadFilter();
        filter.type = 'lowpass';
        filter.frequency.setValueAtTime(500, now);
        filter.frequency.exponentialRampToValueAtTime(50, now + 0.4);
        const gain = this.ctx.createGain();
        gain.gain.setValueAtTime(0.5, now);
        gain.gain.exponentialRampToValueAtTime(0.01, now + 0.4);
        noise.connect(filter);
        filter.connect(gain);
        gain.connect(this.ctx.destination);
        noise.start(now);
    }
}
const sfx = new SoundFX();

// Fixed direct channel identifier - zero codes required
const DIRECT_PEER_CHANNEL = 'skyfire-pvp-dogfight-v1';

let peer = null;
let conn = null;
let isHost = false;
let gameStarted = false;

const canvas = document.getElementById('gameCanvas');
const ctx = canvas.getContext('2d');

function setStatus(text, color = "#94a3b8") {
    const el = document.getElementById('connectionStatus');
    el.innerText = text;
    el.style.color = color;
}

function startAsHost() {
    sfx.init();
    setStatus("INITIALIZING HOST BEACON... WAITING FOR WINGMAN", "#00f0ff");
    isHost = true;

    if (peer) peer.destroy();
    peer = new Peer(DIRECT_PEER_CHANNEL, {
        debug: 1,
        config: {
            iceServers: [
                { urls: 'stun:stun.l.google.com:19302' },
                { urls: 'stun:global.stun.twilio.com:3478' }
            ]
        }
    });

    peer.on('open', () => {
        setStatus("HOST ONLINE. TELL PLAYER 2 TO CLICK 'CONNECT AS GUEST'!", "#00ff66");
    });

    peer.on('connection', (c) => {
        conn = c;
        setupDirectLink();
    });

    peer.on('error', (err) => {
        console.warn("Peer error:", err);
        if (err.type === 'unavailable-id') {
            setStatus("A HOST IS ALREADY LIVE ON THIS NETWORK! Click 'Connect as Guest' instead.", "#f59e0b");
        } else {
            setStatus("NETWORK ERROR: " + (err.message || "RETRYING..."), "#ff3366");
        }
    });
}

function startAsGuest() {
    sfx.init();
    setStatus("SEARCHING FOR HOST RADAR SIGNAL...", "#ff3366");
    isHost = false;

    if (peer) peer.destroy();
    peer = new Peer({
        debug: 1,
        config: {
            iceServers: [
                { urls: 'stun:stun.l.google.com:19302' },
                { urls: 'stun:global.stun.twilio.com:3478' }
            ]
        }
    });

    peer.on('open', () => {
        conn = peer.connect(DIRECT_PEER_CHANNEL, { reliable: true });
        setupDirectLink();
    });

    peer.on('error', (err) => {
        console.warn("Peer error:", err);
        setStatus("COULD NOT FIND HOST. Make sure Player 1 clicked 'Start as Host' first!", "#f59e0b");
    });
}

function setupDirectLink() {
    conn.on('open', () => {
        document.getElementById('briefingModal').style.display = 'none';
        document.getElementById('gameWrapper').style.display = 'block';
        resizeCanvas();
        gameStarted = true;

        if (isHost) {
            setInterval(hostPhysicsTick, 1000 / 60);
        } else {
            setInterval(clientInputSendTick, 1000 / 60);
        }

        conn.on('data', (data) => {
            if (isHost) {
                // Host receives guest inputs
                applyFlightControls(world.p2, data);
            } else {
                // Guest updates state directly from Host
                world.p1 = data.p1;
                world.p2 = data.p2;
                world.bullets = data.bullets;
                world.particles = data.particles;
                if (data.sfxCannon) sfx.cannon();
                if (data.sfxBoom) sfx.explosion();
                updateHudDisplays();
            }
        });

        requestAnimationFrame(renderGame);
    });

    conn.on('close', () => {
        alert("Wingman connection lost.");
        location.reload();
    });
}

const world = {
    p1: { x: 200, y: 350, a: 0, vx: 0, vy: 0, hp: 100, score: 0, cd: 0, thrust: false },
    p2: { x: 900, y: 350, a: Math.PI, vx: 0, vy: 0, hp: 100, score: 0, cd: 0, thrust: false },
    bullets: [],
    particles: []
};

const keys = {};
window.addEventListener('keydown', (e) => { keys[e.code] = true; });
window.addEventListener('keyup', (e) => { keys[e.code] = false; });

function resizeCanvas() {
    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;
}
window.addEventListener('resize', resizeCanvas);

function applyFlightControls(jet, input) {
    if (input.left) jet.a -= 0.075;
    if (input.right) jet.a += 0.075;
    jet.thrust = !!input.thrust;
    if (input.thrust) {
        jet.vx += Math.cos(jet.a) * 0.24;
        jet.vy += Math.sin(jet.a) * 0.24;
    }
    jet.fire = !!input.fire;
}

function clientInputSendTick() {
    if (!conn || !conn.open) return;
    conn.send({
        thrust: keys['ArrowUp'] || keys['KeyW'],
        left: keys['ArrowLeft'] || keys['KeyA'],
        right: keys['ArrowRight'] || keys['KeyD'],
        fire: keys['Enter'] || keys['Space']
    });
}

function hostPhysicsTick() {
    let playCannon = false;
    let playBoom = false;

    // Apply Host local inputs (P1)
    applyFlightControls(world.p1, {
        thrust: keys['KeyW'] || keys['ArrowUp'],
        left: keys['KeyA'] || keys['ArrowLeft'],
        right: keys['KeyD'] || keys['ArrowRight'],
        fire: keys['Space'] || keys['Enter']
    });

    // Update both jets
    [world.p1, world.p2].forEach((jet, idx) => {
        jet.vx *= 0.985;
        jet.vy *= 0.985;
        jet.x += jet.vx;
        jet.y += jet.vy;

        // Screen wrap
        if (jet.x < 0) jet.x += canvas.width;
        if (jet.x > canvas.width) jet.x -= canvas.width;
        if (jet.y < 0) jet.y += canvas.height;
        if (jet.y > canvas.height) jet.y -= canvas.height;

        // Thruster afterburner trail particles
        if (jet.thrust && Math.random() < 0.8) {
            world.particles.push({
                x: jet.x - Math.cos(jet.a) * 16,
                y: jet.y - Math.sin(jet.a) * 16,
                vx: -Math.cos(jet.a) * 2 + (Math.random() - 0.5),
                vy: -Math.sin(jet.a) * 2 + (Math.random() - 0.5),
                color: idx === 0 ? '#00f0ff' : '#ff3366',
                life: 18,
                max: 18
            });
        }

        // Firing cannon
        jet.cd = (jet.cd || 0) - 1;
        if (jet.fire && jet.cd <= 0) {
            world.bullets.push({
                x: jet.x + Math.cos(jet.a) * 20,
                y: jet.y + Math.sin(jet.a) * 20,
                vx: Math.cos(jet.a) * 13 + jet.vx * 0.4,
                vy: Math.sin(jet.a) * 13 + jet.vy * 0.4,
                owner: idx + 1,
                life: 60
            });
            jet.cd = 12;
            playCannon = true;
            sfx.cannon();
        }
    });

    // Update bullets
    for (let i = world.bullets.length - 1; i >= 0; i--) {
        const b = world.bullets[i];
        b.x += b.vx;
        b.y += b.vy;
        b.life--;

        // Collision check
        const target = b.owner === 1 ? world.p2 : world.p1;
        if (Math.hypot(b.x - target.x, b.y - target.y) < 18) {
            target.hp -= 10;
            world.bullets.splice(i, 1);

            // Hit sparks
            for (let k = 0; k < 6; k++) {
                world.particles.push({
                    x: b.x, y: b.y,
                    vx: (Math.random() - 0.5) * 6,
                    vy: (Math.random() - 0.5) * 6,
                    color: '#fde047',
                    life: 14, max: 14
                });
            }

            if (target.hp <= 0) {
                if (b.owner === 1) world.p1.score++; else world.p2.score++;
                target.hp = 100;
                target.x = Math.random() * (canvas.width - 200) + 100;
                target.y = Math.random() * (canvas.height - 200) + 100;
                target.vx = 0; target.vy = 0;
                playBoom = true;
                sfx.explosion();

                // Explosion shockwave particles
                for (let k = 0; k < 30; k++) {
                    const ang = Math.random() * Math.PI * 2;
                    const spd = 1 + Math.random() * 6;
                    world.particles.push({
                        x: target.x, y: target.y,
                        vx: Math.cos(ang) * spd,
                        vy: Math.sin(ang) * spd,
                        color: Math.random() < 0.5 ? '#f59e0b' : '#ff3366',
                        life: 30, max: 30
                    });
                }
            }
            continue;
        }

        if (b.life <= 0) world.bullets.splice(i, 1);
    }

    // Update particles
    for (let i = world.particles.length - 1; i >= 0; i--) {
        const p = world.particles[i];
        p.x += p.vx;
        p.y += p.vy;
        p.life--;
        if (p.life <= 0) world.particles.splice(i, 1);
    }

    updateHudDisplays();

    // Broadcast Authoritative Frame to Guest
    if (conn && conn.open) {
        conn.send({
            p1: world.p1,
            p2: world.p2,
            bullets: world.bullets,
            particles: world.particles,
            sfxCannon: playCannon,
            sfxBoom: playBoom
        });
    }
}

function updateHudDisplays() {
    document.getElementById('p1Score').innerText = world.p1.score;
    document.getElementById('p2Score').innerText = world.p2.score;

    const p1Hp = Math.max(0, world.p1.hp);
    const p2Hp = Math.max(0, world.p2.hp);

    document.getElementById('p1HpTxt').innerText = p1Hp + '%';
    document.getElementById('p2HpTxt').innerText = p2Hp + '%';

    document.getElementById('p1Bar').style.width = p1Hp + '%';
    document.getElementById('p2Bar').style.width = p2Hp + '%';
}

function drawDeltaJet(x, y, angle, color, isThrusting) {
    ctx.save();
    ctx.translate(x, y);
    ctx.rotate(angle);

    // Vector Jet Outline
    ctx.fillStyle = '#081426';
    ctx.strokeStyle = color;
    ctx.lineWidth = 2;
    ctx.shadowBlur = 10;
    ctx.shadowColor = color;

    ctx.beginPath();
    ctx.moveTo(22, 0);       // Nose
    ctx.lineTo(-14, 15);     // Right Wing
    ctx.lineTo(-8, 0);       // Engine Notch
    ctx.lineTo(-14, -15);    // Left Wing
    ctx.closePath();
    ctx.fill();
    ctx.stroke();

    // Canopy Glass
    ctx.fillStyle = color;
    ctx.beginPath();
    ctx.ellipse(3, 0, 7, 2.5, 0, 0, Math.PI * 2);
    ctx.fill();

    // Thruster flame
    if (isThrusting) {
        ctx.fillStyle = '#f59e0b';
        ctx.beginPath();
        ctx.moveTo(-8, 0);
        ctx.lineTo(-20, 4);
        ctx.lineTo(-16, 0);
        ctx.lineTo(-20, -4);
        ctx.closePath();
        ctx.fill();
    }

    ctx.restore();
}

function renderGame() {
    if (!gameStarted) return;

    // Tactical Radar Backdrop
    ctx.fillStyle = '#020713';
    ctx.fillRect(0, 0, canvas.width, canvas.height);

    // Grid Coordinates
    ctx.strokeStyle = 'rgba(0, 240, 255, 0.05)';
    ctx.lineWidth = 1;
    const grid = 60;
    for (let x = 0; x < canvas.width; x += grid) {
        ctx.beginPath(); ctx.moveTo(x, 0); ctx.lineTo(x, canvas.height); ctx.stroke();
    }
    for (let y = 0; y < canvas.height; y += grid) {
        ctx.beginPath(); ctx.moveTo(0, y); ctx.lineTo(canvas.width, y); ctx.stroke();
    }

    // Range Rings
    ctx.strokeStyle = 'rgba(0, 240, 255, 0.03)';
    ctx.lineWidth = 1.5;
    ctx.beginPath();
    ctx.arc(canvas.width / 2, canvas.height / 2, 280, 0, Math.PI * 2);
    ctx.arc(canvas.width / 2, canvas.height / 2, 540, 0, Math.PI * 2);
    ctx.stroke();

    // Particles
    world.particles.forEach(p => {
        ctx.save();
        ctx.globalAlpha = p.life / p.max;
        ctx.fillStyle = p.color;
        ctx.beginPath();
        ctx.arc(p.x, p.y, 2.5, 0, Math.PI * 2);
        ctx.fill();
        ctx.restore();
    });

    // Bullets
    ctx.fillStyle = '#fde047';
    ctx.shadowBlur = 8;
    ctx.shadowColor = '#fde047';
    world.bullets.forEach(b => {
        ctx.beginPath();
        ctx.arc(b.x, b.y, 3, 0, Math.PI * 2);
        ctx.fill();
    });
    ctx.shadowBlur = 0;

    // Fighter Jets
    drawDeltaJet(world.p1.x, world.p1.y, world.p1.a, '#00f0ff', world.p1.thrust);
    drawDeltaJet(world.p2.x, world.p2.y, world.p2.a, '#ff3366', world.p2.thrust);

    requestAnimationFrame(renderGame);
}
</script>
</body>
</html>
