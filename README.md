<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>TRAP MOVIES | Welcome</title>

<!-- ✅ SEO Meta -->
<meta name="description" content="Trap Movies — Your gateway to trending movies and the hottest series. Stream trailers, explore categories, build your watchlist and more.">
<meta name="keywords" content="movies, series, trap movies, streaming, trailers, trending movies, hot series, watchlist">
<meta name="author" content="Trap Gad">
<meta name="robots" content="index, follow">

<!-- ✅ Canonical -->
<link rel="canonical" href="https://trapgad.github.io/Trap_-Movies-/Welcome.html">

<!-- ✅ Open Graph (Social Share Preview) -->
<meta property="og:title" content="TRAP MOVIES">
<meta property="og:description" content="Your gateway to trending movies and hottest series.">
<meta property="og:type" content="website">
<meta property="og:url" content="https://trapgad.github.io/Trap_-Movies-/Welcome.html">
<meta property="og:image" content="https://images.unsplash.com/photo-1517602302552-471fe67acf66?auto=format&fit=crop&w=1950&q=80">

<!-- ✅ Favicon -->
<link rel="icon" href="favicon.png">

<!-- ✅ Preload Google Font (faster performance) -->
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;700&display=swap" rel="stylesheet">

<style>
  body {
    margin: 0;
    font-family: 'Montserrat', sans-serif;
    color: #fff;
    background: #000;
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
    height: 90vh;
    padding: 0 1rem;
    background: url('https://images.unsplash.com/photo-1517602302552-471fe67acf66?auto=format&fit=crop&w=1950&q=80') no-repeat center center/cover;
    position: relative;
  }

  .hero::after {
    content: '';
    position: absolute;
    top:0; left:0; right:0; bottom:0;
    background: rgba(0,0,0,0.6);
  }

  .hero-content {
    position: relative;
    z-index: 1;
    max-width: 900px;
  }

  /* ===== Changed headline color to white ===== */
  .hero-content h1 {
    font-size: 2rem;
    font-weight: 700;
    color: #ffffff;  /* White color */
    line-height: 1.4;
    margin-bottom: 3rem;
  }

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
    transition: background 0.3s, transform 0.3s;
    opacity: 0;
    transform: translateY(20px);
    animation: fadeInUp 0.6s forwards;
  }

  .btn-group a:nth-child(1) { animation-delay: 0.3s; }
  .btn-group a:nth-child(2) { animation-delay: 0.6s; }
  .btn-group a:nth-child(3) { animation-delay: 0.9s; }
  .btn-group a:nth-child(4) { animation-delay: 1.2s; }

  .btn-group a:hover {
    background: #ff4d4d;
    transform: translateY(-3px);
  }

  @keyframes fadeInUp {
    to { opacity: 1; transform: translateY(0); }
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
    <h1>WELCOME TO TRAP MOVIES 
 YOUR GATEWAY TO TRENDING MOVIES AND HOTTEST SERIES</h1>
    <div class="btn-group">
      <a href="Movies.html">Movies</a>
      <a href="Series.html">Series</a>
      <a href="About.html">About</a>
      <a href="Contact.html">Contact</a>
    </div>
  </div>
</section>

<footer>© 2025 TRAP MOVIES — Created by TRAP GAD</footer>

</body>
</html>
