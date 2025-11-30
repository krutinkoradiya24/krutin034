<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Krutin Koradiya — Portfolio</title>
  <meta name="description" content="Portfolio of Krutin Koradiya" />
  <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;600;700&display=swap" rel="stylesheet">

  <style>
    /* ========================
       Color variables (edit to change palette)
       ======================== */
    :root{
      --bg: #0f1724;           /* page background - dark */
      --surface: #0b1220;      /* cards */
      --text: #e6eef8;         /* main text */
      --muted: #98a4b3;        /* secondary text */
      --accent: #00b4d8;       /* primary accent */
      --accent-2: #90e0ef;     /* secondary accent */
      --glass: rgba(255,255,255,0.03);
      --shadow: 0 10px 30px rgba(2,6,23,0.6);
      --radius: 14px;
      --max-width: 1100px;
    }

    /* Light theme overrides */
    .theme-light {
      --bg: #f7fafc;
      --surface: #ffffff;
      --text: #0b1530;
      --muted: #55607a;
      --accent: #1f6feb;
      --accent-2: #06b981;
      --glass: rgba(11,21,48,0.03);
      --shadow: 0 8px 18px rgba(9,30,66,0.06);
    }

    /* ========================
       Basic reset + typography
       ======================== */
    * { box-sizing: border-box; }
    html,body { height:100%; margin:0; font-family:"Montserrat",system-ui,-apple-system,Segoe UI,Roboto,Helvetica,Arial; background:var(--bg); color:var(--text); -webkit-font-smoothing:antialiased; -moz-osx-font-smoothing:grayscale; }
    a { color: inherit; text-decoration:none; }
    img { max-width:100%; display:block; }

    /* Container */
    .wrap{ max-width:var(--max-width); margin:40px auto; padding:24px; }

    /* Header */
    header.site-header{
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap:16px;
      margin-bottom:28px;
    }
    .brand{
      display:flex;
      align-items:center;
      gap:12px;
    }
    .logo{
      width:52px; height:52px; border-radius:12px;
      background:linear-gradient(135deg,var(--accent),var(--accent-2));
      display:flex; align-items:center; justify-content:center;
      font-weight:700; color:white; font-size:18px; box-shadow:var(--shadow);
    }
    .brand h1{ font-size:1.05rem; margin:0; letter-spacing:0.2px; }
    .brand p{ margin:0; font-size:0.82rem; color:var(--muted); }

    /* Header actions */
    .actions{ display:flex; gap:10px; align-items:center; }
    .btn{ cursor:pointer; border:0; padding:.55rem .9rem; border-radius:10px; font-weight:600; background:linear-gradient(90deg,var(--accent),var(--accent-2)); color:white; box-shadow:var(--shadow); }
    .ghost{ background:transparent; border:1px solid rgba(255,255,255,0.05); padding:.45rem .7rem; color:var(--text); border-radius:10px; }

    /* Hero */
    .hero{
      display:grid;
      grid-template-columns: 1fr 360px;
      gap:28px;
      align-items:center;
    }
    .intro{
      background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
      border-radius:var(--radius); padding:28px; box-shadow:var(--shadow); border:1px solid rgba(255,255,255,0.03);
    }
    .intro h2{ margin:0 0 8px 0; font-size:1.8rem; }
    .intro p.lead{ margin:0 0 16px 0; color:var(--muted); font-size:1rem; line-height:1.5; }
    .cta-row{ display:flex; gap:12px; margin-top:12px; }

    /* Card */
    .card{
      background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
      border-radius:12px; padding:16px; box-shadow:var(--shadow); border:1px solid rgba(255,255,255,0.03);
    }

    /* Right column */
    .profile{
      text-align:center;
    }
    .avatar{
      width:200px; height:200px; border-radius:18px; overflow:hidden; display:inline-block; box-shadow:var(--shadow); border:1px solid rgba(255,255,255,0.04);
      background:linear-gradient(180deg,var(--accent),var(--accent-2));
      display:flex; align-items:center; justify-content:center; font-size:36px; color:white; font-weight:700;
    }
    .contact{
      margin-top:12px; font-size:0.95rem; color:var(--muted);
    }

    /* Sections */
    section { margin-top:20px; display:grid; gap:12px; }
    .grid-2{ display:grid; grid-template-columns: repeat(2,1fr); gap:18px; }
    .projects-list{ display:flex; flex-direction:column; gap:12px; }
    .project{
      display:flex; gap:12px; align-items:center;
    }
    .project .thumb{ width:84px; height:60px; border-radius:10px; flex:0 0 84px; background:linear-gradient(90deg,var(--accent),var(--accent-2)); color:white; display:flex; align-items:center; justify-content:center; font-weight:700; }
    .project h4{ margin:0 0 6px 0; font-size:1rem; }
    .project p{ margin:0; color:var(--muted); font-size:0.88rem; }

    /* Contact form */
    .form-row{ display:grid; grid-template-columns: 1fr 1fr; gap:12px; }
    input, textarea{
      width:100%; padding:10px 12px; border-radius:10px; border:1px solid rgba(255,255,255,0.04);
      background:transparent; color:var(--text); outline:none; resize:vertical;
    }
    textarea{ min-height:120px; }

    /* Footer */
    footer{ margin-top:36px; text-align:center; color:var(--muted); font-size:0.92rem; padding:18px 0; }

    /* Responsive */
    @media (max-width:920px){
      .hero{ grid-template-columns: 1fr; }
      .wrap{ padding:16px; }
      .grid-2{ grid-template-columns: 1fr; }
      .profile .avatar{ width:160px; height:160px; }
    }

    /* Smooth theme transitions */
    *{ transition: background-color .22s ease, color .18s ease, border-color .16s ease, box-shadow .18s ease; }
  </style>
</head>
<body>
  <div class="wrap">

    <header class="site-header">
      <div class="brand">
        <div class="logo">KK</div>
        <div>
          <h1>Krutin Koradiya</h1>
          <p>Frontend / Embedded developer • Portfolio</p>
        </div>
      </div>

      <div class="actions">
        <a class="ghost" href="#projects">Projects</a>
        <button id="theme-toggle" class="btn" title="Toggle theme">Toggle theme</button>
      </div>
    </header>

    <main>
      <!-- HERO -->
      <div class="hero">
        <div class="intro card">
          <h2>Hello — I'm Krutin</h2>
          <p class="lead">I build modern web interfaces and embedded systems. I enjoy turning ideas into responsive websites and efficient IoT projects. I focus on clean UI, performance and maintainable code.</p>

          <div class="cta-row">
            <a class="btn" href="#projects">See my work</a>
            <a class="ghost" href="#contact">Contact me</a>
          </div>

          <section aria-label="About me" style="margin-top:18px;">
            <div style="display:flex; gap:12px; align-items:center;">
              <div style="flex:1">
                <h3 style="margin:0 0 8px 0;">Quick facts</h3>
                <ul style="margin:0; padding-left:18px; color:var(--muted);">
                  <li>Frontend development (HTML/CSS/JS)</li>
                  <li>Embedded systems (ESP32, sensors)</li>
                  <li>Portfolio & projects hosting on GitHub Pages</li>
                </ul>
              </div>
              <div style="min-width:120px;">
                <div class="card" style="text-align:center;">
                  <p style="margin:0; font-weight:700; font-size:20px;">Open to work</p>
                  <p style="margin:6px 0 0 0; color:var(--muted); font-size:13px;">Freelance & remote</p>
                </div>
              </div>
            </div>
          </section>
        </div>

        <aside class="profile card">
          <div class="avatar">KK</div>
          <div class="contact">
            <p style="margin:10px 0 0 0; font-weight:700;">Krutin Koradiya</p>
            <p style="margin:4px 0 0 0; color:var(--muted)"><a href="mailto:krutinkoradiya24@gmail.com">krutinkoradiya24@gmail.com</a></p>
            <p style="margin:10px 0 0 0; color:var(--muted); font-size:13px;">Location: India</p>
            <div style="margin-top:12px; display:flex; gap:8px; justify-content:center;">
              <a class="btn" href="#contact">Hire me</a>
              <a class="ghost" href="#projects">My work</a>
            </div>
          </div>
        </aside>
      </div>

      <!-- PROJECTS + SKILLS -->
      <section id="projects" style="margin-top:28px;">
        <h3 style="margin:0 0 8px 0;">Selected Projects</h3>

        <div class="grid-2">
          <div class="projects-list card">
            <!-- Project 1 -->
            <div class="project">
              <div class="thumb">P1</div>
              <div>
                <h4>Portfolio Redesign</h4>
                <p>A responsive single-page portfolio built with vanilla HTML/CSS/JS and CSS variables for themeing.</p>
                <small style="color:var(--muted)">HTML • CSS • JS</small>
              </div>
            </div>

            <!-- Project 2 -->
            <div class="project">
              <div class="thumb">P2</div>
              <div>
                <h4>ESP32 Sensor Hub</h4>
                <p>Data logger using ESP32, sending sensor values to an HTTP endpoint; visualized with a small web dashboard.</p>
                <small style="color:var(--muted)">ESP32 • C • MQTT</small>
              </div>
            </div>

            <!-- Project 3 -->
            <div class="project">
              <div class="thumb">P3</div>
              <div>
                <h4>Mini IoT Parking Aid</h4>
                <p>Ultrasonic distance sensor to control buzzer speed based on proximity (embedded systems project).</p>
                <small style="color:var(--muted)">Electronics • Arduino</small>
              </div>
            </div>

            <!-- Add more projects similarly -->
          </div>

          <div class="card">
            <h4 style="margin:0 0 10px 0;">Skills & Tools</h4>
            <div style="display:flex; flex-wrap:wrap; gap:8px;">
              <span class="ghost" style="padding:.35rem .6rem; border-radius:8px;">HTML</span>
              <span class="ghost" style="padding:.35rem .6rem; border-radius:8px;">CSS</span>
              <span class="ghost" style="padding:.35rem .6rem; border-radius:8px;">JavaScript</span>
              <span class="ghost" style="padding:.35rem .6rem; border-radius:8px;">ESP32</span>
              <span class="ghost" style="padding:.35rem .6rem; border-radius:8px;">GitHub</span>
            </div>

            <hr style="margin:14px 0; border:none; border-top:1px solid rgba(255,255,255,0.03);" />

            <h4 style="margin:0 0 8px 0;">About this template</h4>
            <p style="margin:0; color:var(--muted);">This single-file template is easy to customize: change the CSS variables at the top to update colors, or replace project entries below with real screenshots and links.</p>
          </div>
        </div>
      </section>

      <!-- CONTACT -->
      <section id="contact">
        <h3 style="margin:18px 0 8px 0;">Contact</h3>
        <div class="card">
          <div style="display:flex; gap:18px; flex-direction:column;">
            <p style="margin:0 0 6px 0; color:var(--muted);">Want to work together? Send a message or email me directly at <a href="mailto:krutinkoradiya24@gmail.com">krutinkoradiya24@gmail.com</a>.</p>

            <form onsubmit="event.preventDefault(); sendMessage();">
              <div class="form-row" style="margin-bottom:10px;">
                <input type="text" id="name" placeholder="Your name" required />
                <input type="email" id="email" placeholder="Your email" required />
              </div>
              <textarea id="message" placeholder="Your message..." required></textarea>
              <div style="margin-top:10px; display:flex; gap:10px;">
                <button type="submit" class="btn">Send message</button>
                <button type="button" onclick="document.getElementById('name').value='';document.getElementById('email').value='';document.getElementById('message').value='';" class="ghost">Reset</button>
              </div>
            </form>

            <div id="send-status" style="color:var(--muted); font-size:0.95rem; margin-top:8px;"></div>
          </div>
        </div>
      </section>

      <footer>
        <div>© <span id="year"></span> Krutin Koradiya — <a href="mailto:krutinkoradiya24@gmail.com">krutinkoradiya24@gmail.com</a></div>
      </footer>
    </main>

  </div>

  <script>
    // -----------------------------
    // Theme toggle (persist in localStorage)
    // -----------------------------
    (function(){
      const btn = document.getElementById('theme-toggle');
      const storageKey = 'site-theme';
      const root = document.documentElement;

      function applyTheme(theme){
        if(theme === 'light') root.classList.add('theme-light');
        else root.classList.remove('theme-light');
      }

      const saved = localStorage.getItem(storageKey) || 'dark';
      applyTheme(saved);

      btn.addEventListener('click', () => {
        const current = localStorage.getItem(storageKey) || 'dark';
        const next = current === 'light' ? 'dark' : 'light';
        localStorage.setItem(storageKey, next);
        applyTheme(next);
      });
    })();

    // -----------------------------
    // Simple "send message" simulation (no backend)
    // -----------------------------
    function sendMessage(){
      const status = document.getElementById('send-status');
      const name = document.getElementById('name').value.trim();
      const email = document.getElementById('email').value.trim();
      const message = document.getElementById('message').value.trim();

      if(!name || !email || !message){
        status.textContent = 'Please fill all fields.';
        return;
      }

      // Simulate sending — replace this with real backend / email API if you have one
      status.textContent = 'Sending...';
      setTimeout(() => {
        status.textContent = 'Thanks! Your message was not really sent (this is a demo). Email directly to krutinkoradiya24@gmail.com';
        document.getElementById('name').value='';
        document.getElementById('email').value='';
        document.getElementById('message').value='';
      }, 800);
    }

    // Set current year
    document.getElementById('year').textContent = new Date().getFullYear();
  </script>
</body>
</html>
