<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Jaspreet — Personal Landing</title>
  <style>
    :root{
      --bg: #f7fbff; /* very light blue */
      --card: #ffffff;
      --muted: #586166;
      --accent-1: #7bd389; /* soft mint */
      --accent-2: #ffd59e; /* warm peach */
      --accent-3: #9ad0ff; /* light sky */
      --glass: rgba(255,255,255,0.7);
      --shadow: 0 8px 20px rgba(24,39,56,0.08);
      --radius: 14px;
      font-family: Inter, system-ui, -apple-system, 'Segoe UI', Roboto, 'Helvetica Neue', Arial;
    }

    html,body{
      height:100%;
      margin:0;
      background: linear-gradient(180deg,var(--bg), #ffffff);
      color:#12212a;
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
    }

    /* top-left photo */
    .photo-wrap{
      position:fixed;
      top:20px;
      left:20px;
      width:96px;
      height:96px;
      border-radius:18px;
      overflow:hidden;
      box-shadow: var(--shadow);
      background: linear-gradient(135deg,var(--accent-3),var(--accent-1));
      display:flex;
      align-items:center;
      justify-content:center;
      border: 3px solid rgba(255,255,255,0.6);
      backdrop-filter: blur(6px);
    }

    .photo-wrap img{
      width:100%;
      height:100%;
      object-fit:cover;
      display:block;
    }

    /* header / hero */
    .container{
      max-width:980px;
      margin:140px auto 60px; /* leave space for top-left photo */
      padding:28px;
      background: linear-gradient(180deg, var(--card), var(--glass));
      border-radius: var(--radius);
      box-shadow: var(--shadow);
    }

    .header{
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap:24px;
    }

    h1{
      margin:0 0 6px 0;
      font-size:28px;
      letter-spacing:-0.2px;
      color:#0f1720;
    }

    p.lead{
      margin:0;
      color:var(--muted);
      font-size:14px;
    }

    /* nav buttons */
    .nav{
      display:flex;
      gap:12px;
    }

    .nav button{
      appearance:none;
      border:0;
      padding:10px 16px;
      border-radius:12px;
      font-weight:600;
      cursor:pointer;
      background:transparent;
      transition:transform .18s ease, box-shadow .18s ease, background-color .18s ease;
      box-shadow: none;
      color: #0f1720;
    }

    /* different base tints for buttons */
    .btn-2{ background: linear-gradient(90deg, rgba(255,213,158,0.18), rgba(154,208,255,0.06)); }

    /* hover — gentle color changes (no dark colors) */
    .nav button:hover{
      transform:translateY(-4px);
      box-shadow: 0 10px 30px rgba(12,40,20,0.06);
    }

    .btn-2:hover{ background: linear-gradient(90deg, #ffd08a, #ffd59e); color:#4a2b00; }

    /* main content grid */
    .grid{
      display:grid;
      grid-template-columns: 1fr;
      gap:22px;
      margin-top:18px;
    }

    .card{
      background:rgba(255,255,255,0.7);
      border-radius:12px;
      padding:18px;
      box-shadow: 0 6px 18px rgba(10,24,40,0.04);
    }

    /* footer */
    footer{ margin-top:24px; text-align:center; color:var(--muted); font-size:13px; }

    /* responsive */
    @media (max-width:900px){
      .container{ margin:110px 18px 40px; }
    }
  </style>
</head>
<body>

  <!-- top-left photo: replace src with your picture path -->
  <div class="photo-wrap" title="Your photo">
    <img src="/path/to/your-photo.jpg" alt="Your photo">
  </div>

  <main class="container" role="main">
    <div class="header">
      <div>
        <h1>Hi — I'm Jaspreet</h1>
        <p class="lead">Infrastructure consultant · Modern Work · AI enthusiast · Writer</p>
      </div>

      <nav class="nav" aria-label="Primary">
        <!-- Only keep Blog button on About page -->
        <button class="btn-2" id="blogBtn" type="button">Blog</button>
      </nav>
    </div>

    <div class="grid">
      <section class="card">
        <h3 style="margin-top:0;">About Me</h3>
        <p class="lead" style="margin-top:6px;"><strong>Driving digital transformation through modern workplace innovation and AI-powered productivity.</strong><br>I specialise in Microsoft 365 Copilot, cloud strategy, and security-first deployments—helping enterprises modernise, scale, and unlock measurable business value.</p>
        <p class="lead">Recognised for hands-on demos, clear storytelling, and fast execution, I bring together technical depth and business context to make complex transformations simple and achievable. As a <strong>Microsoft Certified Trainer</strong> and <strong>Prosci® Change Practitioner</strong>, I blend solution expertise with structured change management to drive real adoption.</p>
        <h4>Core Expertise</h4>
        <ul>
          <li>Modern Work & Copilot Adoption</li>
          <li>Cloud & Security Strategy</li>
          <li>Change Management & Enablement</li>
          <li>Customer Success & Solution Design</li>
        </ul>
      </section>

    </div>

    <footer>
      <div>📧 <a href="mailto:jsjolly76@hotmail.com">jsjolly76@hotmail.com</a></div>
      <div>🔗 <a href="https://www.linkedin.com/in/jaspreetjolly/" target="_blank" rel="noopener noreferrer">LinkedIn</a> · <a href="https://twitter.com/JaspreetJolly1" target="_blank" rel="noopener noreferrer">Twitter</a></div>
      <p style="margin-top:8px;">Made with care · Light palette</p>
    </footer>
  </main>

  <script>
    // Attach listeners only after DOM is ready and only for elements that exist.
    document.addEventListener('DOMContentLoaded', () => {
      const blogBtn = document.getElementById('blogBtn');
      if (blogBtn) {
        blogBtn.addEventListener('click', () => {
          // Navigate to your blog home when clicked; change if different behavior is desired
          window.location.href = 'https://blogs.jaspreetjolly.com';
        });
      }

      // NOTE: archiveBtn and mindmapsBtn are intentionally not referenced here because
      // those elements were removed from this About page. This prevents the
      // "Cannot read properties of null (reading 'addEventListener')" runtime error.
    });
  </script>
</body>
</html>
