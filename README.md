<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>TRAP MOVIES | Welcome</title>
<link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;700&display=swap" rel="stylesheet">
<style>
  body {
    margin: 0;
    font-family: 'Montserrat', sans-serif;
    background: linear-gradient(180deg, #0d0d0d 0%, #1a1a1a 100%);
    color: #fff;
  }

  header {
    background: linear-gradient(90deg, #b30000, #333);
    padding: 1.5rem;
    text-align: center;
    font-size: 2rem;
    font-weight: 700;
    letter-spacing: 2px;
    color: #fff;
  }

  .hero {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    height: 80vh;
    padding: 0 1rem;
    background: url('https://images.unsplash.com/photo-1602524818670-3cf828b5e7f3?auto=format&fit=crop&w=1950&q=80') no-repeat center center/cover;
    position: relative;
  }

  .hero::after {
    content: '';
    position: absolute;
    top:0; left:0; right:0; bottom:0;
    background: rgba(0,0,0,0.7);
  }

  .hero-content {
    position: relative;
    z-index: 1;
    color: #fff;
    max-width: 900px;
  }

  .hero-content h1 {
    font-size: 2rem;
    font-weight: 700;
    color: #ff3333;
    line-height: 1.4;
    margin-bottom: 3rem;
  }

  /* ===== Centered Buttons (Tabs) ===== */
  .btn-group {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 1.5rem;
  }

  .btn-group a {
    display: inline-block;
    text-decoration: none;
    background: #b30000;
    color: #fff;
    padding: 1rem 2rem;
    font-size: 1.1rem;
    font-weight: 600;
    border-radius: 40px;
    transition: all 0.3s;
  }

  .btn-group a:hover {
    background: #ff3333;
    transform: scale(1.05);
  }

  footer {
    text-align: center;
    padding: 1rem;
    font-size: 0.9rem;
    color: #aaa;
    border-top: 2px solid #b30000;
  }

  @media (max-width: 768px) {
    .hero-content h1 { font-size: 1.5rem; }
    .btn-group a { padding: 0.8rem 1.5rem; font-size: 1rem; }
  }

  @media (max-width: 480px) {
    .hero-content h1 { font-size: 1.2rem; }
    .btn-group a { padding: 0.6rem 1.2rem; font-size: 0.9rem; }
  }
</style>
</head>
<body>

<header>WELCOME TO TRAP MOVIES</header>

<section class="hero">
  <div class="hero-content">
    <h1>WELCOME TO TRAP MOVIES  YOUR GATEWAY TO TRENDING MOVIES AND HOTTEST SERIES</h1>

    <div class="btn-group">
      <a href="Movies.html">Movies</a>
      <a href="Series.html">Series</a>
      <a href="About.html">About</a>
      <a href="Contact.html">Contact</a>
    </div>
  </div>
</section>

<footer>Â© 2025 TRAP MOVIES Created by TRAP GAD </footer>

</body>
</html>
