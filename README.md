    95% { opacity: 0; }
  }

  @keyframes glitch-bot {
    0%, 88%, 100% { transform: none; opacity: 0; }
    89% { transform: translate(4px, 2px); opacity: 1; }
    91% { transform: translate(-4px, -2px); opacity: 1; }
    93% { transform: translate(2px, 0); opacity: 1; }
    95% { opacity: 0; }
  }

  .subtitle {
    font-family: 'Share Tech Mono', monospace;
    color: var(--blue-dim);
    font-size: 0.85rem;
    letter-spacing: 0.3em;
    margin-top: 10px;
    text-transform: uppercase;
  }

  /* ── Neon divider ── */
  .neon-line {
    width: 100%;
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--blue-glow), transparent);
    box-shadow: 0 0 8px var(--blue-glow);
    margin: 20px 0;
  }

  /* ── Terminal Panel ── */
  .terminal {
    background: var(--panel);
    border: 1px solid var(--blue-dim);
    border-radius: 4px;
    box-shadow:
      0 0 15px rgba(0, 207, 255, 0.2),
      inset 0 0 30px rgba(0, 150, 200, 0.05);
    overflow: hidden;
    margin-bottom: 30px;
  }

  .terminal-bar {
    background: rgba(0, 50, 80, 0.9);
    padding: 8px 16px;
    display: flex;
    align-items: center;
    gap: 8px;
    border-bottom: 1px solid var(--blue-dim);
  }

  .dot {
    width: 11px; height: 11px;
    border-radius: 50%;
  }
  .dot.r { background: #ff4455; box-shadow: 0 0 5px #ff4455; }
  .dot.y { background: #ffcc00; box-shadow: 0 0 5px #ffcc00; }
  .dot.g { background: #00ff88; box-shadow: 0 0 5px #00ff88; }

  .terminal-title {
    margin-left: auto;
    font-size: 0.7rem;
    color: var(--blue-dim);
    letter-spacing: 0.2em;
  }

  .terminal-body {
    padding: 20px 24px;
    min-height: 240px;
    font-size: 0.88rem;
    line-height: 1.9;
  }

  .line { display: flex; gap: 8px; }
  .prompt { color: var(--blue-glow); user-select: none; }
  .cmd { color: #aaeeff; }
  .out { color: #66bbcc; padding-left: 20px; }
  .out.warn { color: #ffcc00; }
  .out.ok { color: #00ff88; }
  .out.err { color: #ff4455; }

  /* Typing cursor */
  .cursor-line { display: flex; align-items: center; gap: 8px; }
  #typed-text { color: #aaeeff; }
  .cursor {
    display: inline-block;
    width: 9px; height: 16px;
    background: var(--blue-glow);
    box-shadow: 0 0 8px var(--blue-glow);
    animation: blink 0.75s step-end infinite;
    vertical-align: middle;
  }

  @keyframes blink {
    0%, 100% { opacity: 1; }
    50% { opacity: 0; }
  }

  /* ── Neon Stats Grid ── */
  .stats-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
    gap: 16px;
    margin-bottom: 30px;
  }

  .stat-card {
    background: var(--panel);
    border: 1px solid var(--blue-dim);
    border-radius: 4px;
    padding: 18px 20px;
    position: relative;
    overflow: hidden;
    transition: border-color 0.3s, box-shadow 0.3s;
  }

  .stat-card:hover {
    border-color: var(--blue-glow);
    box-shadow: 0 0 20px rgba(0, 238, 255, 0.25);
  }

  .stat-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0;
    width: 3px; height: 100%;
    background: var(--blue-glow);
    box-shadow: 0 0 10px var(--blue-glow);
  }

  .stat-label {
    font-size: 0.65rem;
    letter-spacing: 0.25em;
    color: var(--blue-dim);
    text-transform: uppercase;
    margin-bottom: 6px;
  }

  .stat-value {
    font-family: 'Orbitron', monospace;
    font-size: 1.5rem;
    font-weight: 700;
    color: var(--blue-glow);
    text-shadow: 0 0 10px var(--blue-glow);
  }

  .stat-unit {
    font-size: 0.7rem;
    color: var(--blue-dim);
    margin-left: 4px;
  }

  /* ── Progress bars ── */
  .progress-section {
    background: var(--panel);
    border: 1px solid var(--blue-dim);
    border-radius: 4px;
    padding: 20px 24px;
    margin-bottom: 30px;
    box-shadow: 0 0 10px rgba(0,200,255,0.1);
  }

  .prog-row { margin-bottom: 14px; }
  .prog-label {
    display: flex;
    justify-content: space-between;
    font-size: 0.75rem;
    color: var(--blue-dim);
    margin-bottom: 5px;
    letter-spacing: 0.1em;
  }

  .prog-track {
    height: 6px;
    background: rgba(0,100,150,0.3);
    border-radius: 3px;
    overflow: hidden;
  }

  .prog-fill {
    height: 100%;
    border-radius: 3px;
    background: linear-gradient(90deg, #0088cc, var(--blue-glow));
    box-shadow: 0 0 8px var(--blue-glow);
    width: 0%;
    transition: width 2s cubic-bezier(0.4, 0, 0.2, 1);
  }

  /* ── Footer ── */
  .footer {
    text-align: center;
    font-size: 0.7rem;
    color: var(--blue-dark);
    letter-spacing: 0.2em;
    padding-top: 20px;
    border-top: 1px solid rgba(0,100,150,0.3);
  }

  .blink-text {
    animation: blink 1.2s step-end infinite;
    color: var(--blue-dim);
  }
</style>
</head>
<body>

<canvas id="matrix"></canvas>

<div class="container">

  <!-- Glitch Header -->
  <div class="glitch-wrap">
    <div class="glitch" data-text="CYBER_SHELL">CYBER_SHELL</div>
    <div class="subtitle">[ UNAUTHORIZED ACCESS DETECTED — SYSTEM BREACH v2.0 ]</div>
  </div>

  <div class="neon-line"></div>

  <!-- Stats -->
  <div class="stats-grid">
    <div class="stat-card">
      <div class="stat-label">IP Address</div>
      <div class="stat-value" style="font-size:1rem;" id="ip-val">192.168.0.1</div>
    </div>
    <div class="stat-card">
      <div class="stat-label">Packets</div>
      <div class="stat-value"><span id="pkt-val">0</span><span class="stat-unit">K</span></div>
    </div>
    <div class="stat-card">
      <div class="stat-label">Uptime</div>
      <div class="stat-value"><span id="uptime-val">00:00:00</span></div>
    </div>
    <div class="stat-card">
      <div class="stat-label">Nodes</div>
      <div class="stat-value"><span id="node-val">0</span><span class="stat-unit">/ 256</span></div>
    </div>
  </div>

  <!-- Terminal -->
  <div class="terminal">
    <div class="terminal-bar">
      <div class="dot r"></div>
      <div class="dot y"></div>
      <div class="dot g"></div>
      <div class="terminal-title">root@cybersh3ll:~#</div>
    </div>
    <div class="terminal-body" id="term-body">
      <div class="line"><span class="prompt">$</span><span class="cmd">init --breach-mode --silent</span></div>
      <div class="out ok">✔ Kernel modules loaded</div>
      <div class="out">Establishing encrypted tunnel...</div>
      <div class="out ok">✔ TOR exit node: 185.220.101.47</div>
      <div class="line"><span class="prompt">$</span><span class="cmd">scan --range 0.0.0.0/0 --threads 512</span></div>
      <div class="out warn">⚠ Firewall detected — bypassing...</div>
      <div class="out ok">✔ 2,847 open ports found</div>
      <div class="line"><span class="prompt">$</span><span class="cmd">exploit --target auth_service --payload rce</span></div>
      <div class="out err">✖ Attempt 1 — BLOCKED</div>
      <div class="out ok">✔ Attempt 2 — SUCCESS — root shell obtained</div>
      <div class="line"><span class="prompt">$</span><span class="cmd">exfil --data /etc/shadow --encrypt aes256</span></div>
      <div class="out ok">✔ Transfer complete — 4.2 MB encrypted</div>
      <div class="neon-line" style="margin:12px 0;"></div>
      <div class="cursor-line">
        <span class="prompt">$</span>
        <span id="typed-text"></span>
        <span class="cursor"></span>
      </div>
    </div>
  </div>

  <!-- Progress Bars -->
  <div class="progress-section">
    <div class="prog-row">
      <div class="prog-label"><span>EXPLOIT COVERAGE</span><span id="p1-pct">0%</span></div>
      <div class="prog-track"><div class="prog-fill" id="p1" data-target="87"></div></div>
    </div>
    <div class="prog-row">
      <div class="prog-label"><span>NETWORK SATURATION</span><span id="p2-pct">0%</span></div>
      <div class="prog-track"><div class="prog-fill" id="p2" data-target="63"></div></div>
    </div>
    <div class="prog-row">
      <div class="prog-label"><span>DATA EXTRACTION</span><span id="p3-pct">0%</span></div>
      <div class="prog-track"><div class="prog-fill" id="p3" data-target="74"></div></div>
    </div>
    <div class="prog-row" style="margin-bottom:0">
      <div class="prog-label"><span>TRACE ELIMINATION</span><span id="p4-pct">0%</span></div>
      <div class="prog-track"><div class="prog-fill" id="p4" data-target="95"></div></div>
    </div>
  </div>

  <div class="footer">
    <span class="blink-text">■</span>
    &nbsp; SYS_ACCESS: GRANTED &nbsp;|&nbsp; ENCRYPTION: AES-256 &nbsp;|&nbsp; TRACE: NONE &nbsp;
    <span class="blink-text">■</span>
  </div>

</div>

<script>
// ── Matrix Rain ──
const canvas = document.getElementById('matrix');
const ctx = canvas.getContext('2d');

function resizeCanvas() {
  canvas.width = window.innerWidth;
  canvas.height = window.innerHeight;
}
resizeCanvas();
window.addEventListener('resize', resizeCanvas);

const chars = '0123456789ABCDEF<>[]{}|/\\アイウエオカキクケコサシスセソタチツテト∑∂∫≈≠∞←→↑↓⊕⊗';
const fontSize = 14;
let columns = Math.floor(canvas.width / fontSize);
let drops = Array(columns).fill(1);

function drawMatrix() {
  ctx.fillStyle = 'rgba(0, 5, 15, 0.05)';
  ctx.fillRect(0, 0, canvas.width, canvas.height);

  for (let i = 0; i < drops.length; i++) {
    const brightness = Math.random();
    if (brightness > 0.9) {
      ctx.fillStyle = '#aaeeff';
    } else if (brightness > 0.6) {
      ctx.fillStyle = '#00cfff';
    } else {
      ctx.fillStyle = '#006688';
    }

    ctx.font = fontSize + 'px Share Tech Mono';
    const char = chars[Math.floor(Math.random() * chars.length)];
    ctx.fillText(char, i * fontSize, drops[i] * fontSize);

    if (drops[i] * fontSize > canvas.height && Math.random() > 0.975) {
      drops[i] = 0;
    }
    drops[i]++;
  }
}

setInterval(drawMatrix, 50);
window.addEventListener('resize', () => {
  resizeCanvas();
  columns = Math.floor(canvas.width / fontSize);
  drops = Array(columns).fill(1);
});

// ── Typing Effect ──
const commands = [
  'nmap -sV --script vuln 10.0.0.0/24',
  'hydra -l root -P wordlist.txt ssh://target',
  'sqlmap -u "http://target/id=1" --dbs',
  'msfconsole -q -x "use exploit/multi/handler"',
  'wireshark --capture-filter "tcp port 443"',
  'john --wordlist=rockyou.txt hashes.txt',
];

let cmdIndex = 0, charIndex = 0, deleting = false;
const typedEl = document.getElementById('typed-text');

function typeLoop() {
  const current = commands[cmdIndex];
  if (!deleting) {
    typedEl.textContent = current.slice(0, ++charIndex);
    if (charIndex === current.length) {
      deleting = true;
      setTimeout(typeLoop, 2000);
      return;
    }
  } else {
    typedEl.textContent = current.slice(0, --charIndex);
    if (charIndex === 0) {
      deleting = false;
      cmdIndex = (cmdIndex + 1) % commands.length;
    }
  }
  setTimeout(typeLoop, deleting ? 40 : 65);
}
typeLoop();

// ── Animated Counters ──
function animCount(id, target, suffix = '') {
  let v = 0;
  const step = Math.max(1, Math.floor(target / 60));
  const el = document.getElementById(id);
  const iv = setInterval(() => {
    v = Math.min(v + step, target);
    el.textContent = v + suffix;
    if (v >= target) clearInterval(iv);
  }, 30);
}

setTimeout(() => {
  animCount('pkt-val', 487);
  animCount('node-val', 214);
}, 500);

// ── Uptime Clock ──
let secs = 0;
setInterval(() => {
  secs++;
  const h = String(Math.floor(secs / 3600)).padStart(2, '0');
  const m = String(Math.floor((secs % 3600) / 60)).padStart(2, '0');
  const s = String(secs % 60).padStart(2, '0');
  document.getElementById('uptime-val').textContent = `${h}:${m}:${s}`;
}, 1000);

// ── IP Scramble ──
const ipEl = document.getElementById('ip-val');
function scrambleIP() {
  let count = 0;
  const iv = setInterval(() => {
    const r = () => Math.floor(Math.random() * 256);
    ipEl.textContent = `${r()}.${r()}.${r()}.${r()}`;
    if (++count > 12) {
      ipEl.textContent = '10.13.37.99';
      clearInterval(iv);
    }
  }, 80);
}
setTimeout(scrambleIP, 800);

// ── Progress Bars ──
setTimeout(() => {
  [['p1','p1-pct'], ['p2','p2-pct'], ['p3','p3-pct'], ['p4','p4-pct']].forEach(([barId, pctId]) => {
    const bar = document.getElementById(barId);
    const pctEl = document.getElementById(pctId);
    const target = parseInt(bar.dataset.target);
    bar.style.width = target + '%';
    let v = 0;
    const iv = setInterval(() => {
      v = Math.min(v + 1, target);
      pctEl.textContent = v + '%';
      if (v >= target) clearInterval(iv);
    }, 20);
  });
}, 600);
</script>
</body>
</html>
