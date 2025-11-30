<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Koradiya Krutin — Portfolio</title>

  <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;600&display=swap" rel="stylesheet">

  <style>
    :root{
      --bg:#0b0b0c;
      --muted:#bdbdbd;
      --accent:#ff5858;
      --container:1100px;
    }
    *{box-sizing:border-box}
    body{
      margin:0;
      font-family: 'Montserrat', system-ui, -apple-system, 'Segoe UI', Roboto, Arial;
      background:var(--bg);
      color:#fff;
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
      line-height:1.6;
    }
    a{color:inherit;text-decoration:none}
    .wrap{max-width:var(--container);margin:0 auto;padding:40px 24px}

    /* nav */
    nav{position:fixed;right:24px;top:20px;z-index:50;display:flex;gap:18px}
    nav a{color:rgba(255,255,255,0.92);font-weight:600}

    /* hero */
    .hero{
      min-height:68vh;
      display:flex;align-items:center;
      padding-left:6vw;position:relative;overflow:hidden;
    }
    .hero::before{
      content:'';position:absolute;inset:0;z-index:0;
      background-image:url('https://images.unsplash.com/photo-1501785888041-af3ef285b470?q=80&w=2000&auto=format&fit=crop&crop=faces');
      background-size:cover;background-position:center;
      filter:grayscale(30%) brightness(35%);
    }
    .hero .content{position:relative;z-index:2;max-width:800px}
    h1{font-size:56px;margin:0 0 12px;font-weight:300}
    .sub{color:var(--muted);font-size:18px;margin-bottom:22px}
    .btn{background:var(--accent);padding:12px 20px;border-radius:6px;color:#fff;font-weight:700}

    /* sections */
    section{padding:72px 0;border-top:1px solid rgba(255,255,255,0.03)}
    h2{font-size:34px;margin:0 0 8px}
    .line{height:4px;width:64px;background:var(--accent);border-radius:4px;margin-bottom:18px}

    /* two-column project layout */
    .projects{display:grid;gap:36px}
    .project{display:grid;grid-template-columns:1fr 540px;gap:28px;align-items:center}
    .project .meta h3{margin:0 0 8px;font-size:24px}
    .project .meta p{color:var(--muted);margin:0 0 12px}
    .tech{color:var(--muted);margin-bottom:12px}
    .screenshot{background:#0f0f0f;padding:16px;border-radius:6px}
    .screenshot img{display:block;width:100%;height:auto}

    /* about */
    .about{display:flex;gap:40px;align-items:center}
    .avatar{width:220px;height:220px;border-radius:50%;overflow:hidden;border:8px solid rgba(255,255,255,0.04)}
    .avatar img{width:100%;height:100%;object-fit:cover}
    .about p{color:var(--muted);max-width:640px}

    /* contact form */
    form input, form textarea{width:100%;padding:12px;border-radius:8px;border:1px solid rgba(255,255,255,0.06);background:transparent;color:#fff}
    .muted{color:var(--muted)}

    /* responsive */
    @media (max-width:980px){
      h1{font-size:44px}
      .project{grid-template-columns:1fr 1fr}
    }
    @media (max-width:760px){
      nav{right:12px;top:12px}
      .project{grid-template-columns:1fr}
      .screenshot{order:-1}
      .about{flex-direction:column;align-items:flex-
