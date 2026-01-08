<html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="TRAP MOVIES " content="MOVIES, initial-scale=1.0">
<title>TRAP MOVIES | Welcome</title>
<link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600;700&display=swap" rel="stylesheet">
<style>
/* -------------------- BASE -------------------- */
body {
  margin: 0;
  font-family: 'Montserrat', sans-serif;
  color: #fff;
  background: #0d0d0d;
  transition: 0.3s;
}
body.modal-open { overflow: hidden; }

header {
  background: linear-gradient(90deg, #b30000, #2a0d2a);
  padding: 1.5rem;
  text-align: center;
  font-size: 2rem;
  font-weight: 700;
  letter-spacing: 2px;
  color: #fff;
  text-shadow: 1px 1px 3px #000;
}

/* -------------------- HERO -------------------- */
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
.hero-content { position: relative; z-index: 1; max-width: 900px; }
.hero-content h1 {
  font-size: 2rem;
  font-weight: 700;
  line-height: 1.4;
  margin-bottom: 3rem;
}
.btn-group { display: flex; flex-wrap: wrap; justify-content: center; gap: 1.5rem; }
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
.btn-group a:hover { background: #ff4d4d; transform: translateY(-3px); }
@keyframes fadeInUp { to { opacity: 1; transform: translateY(0); } }

/* -------------------- MOVIES GRID -------------------- */
.movies {
  display: grid;
  grid-template-columns: repeat(auto-fill,minmax(180px,1fr));
  gap: 1.2rem;
  padding: 1.5rem;
}
.movie-card {
  background: #1f1f1f;
  border-radius: 10px;
  overflow: hidden;
  text-align: center;
  box-shadow: 0 0 12px rgba(179,0,0,0.5);
  transition: transform 0.3s, box-shadow 0.3s;
  cursor: pointer;
}
.movie-card:hover { transform: scale(1.05); box-shadow: 0 0 20px rgba(255,0,128,0.7); }
.movie-card img { width: 100%; aspect-ratio: 2/3; object-fit: cover; }
.movie-card h3 { font-size: 1rem; margin: 0.5rem 0; color: #fff; }

/* -------------------- SEARCH -------------------- */
.search-bar { display: flex; justify-content: center; margin: 1.5rem 0; }
.search-bar input {
  width: 70%;
  max-width: 400px;
  padding: 0.8rem;
  border: 2px solid #b30000;
  border-radius: 25px;
  background: #111;
  color: white;
  font-size: 1rem;
  text-align: center;
  outline: none;
}

/* -------------------- FOOTER -------------------- */
footer {
  text-align: center;
  padding: 1rem;
  font-size: 0.9rem;
  color: #aaa;
  border-top: 2px solid #b30000;
}

/* -------------------- MODAL -------------------- */
.modal { display: none; position: fixed; z-index: 10; left: 0; top: 0; width: 100%; height: 100%; background: rgba(10,10,10,0.95); justify-content: center; align-items: center; }
.modal-content { position: relative; width: 80%; max-width: 800px; }
.modal-content iframe { width: 100%; height: 450px; border-radius: 8px; }
.close { position: absolute; top: -30px; right: 0; font-size: 2rem; color: #fff; cursor: pointer; }
.close:hover { color: #ff33ff; }

@media (max-width: 768px){
  .hero-content h1 { font-size: 1.5rem; }
  .btn-group a { padding: 0.8rem 1.5rem; font-size: 1rem; }
}
@media (max-width: 480px){
  .hero-content h1 { font-size: 1.2rem; }
  .btn-group a { padding: 0.6rem 1.2rem; font-size: 0.9rem; }
}
</style>
</head>
<body>

<header>TRAP MOVIES</header>

<!-- HERO -->
<section class="hero">
  <div class="hero-content">
    <h1>WELCOME TO TRAP MOVIES — YOUR GATEWAY TO TRENDING MOVIES AND HOTTEST SERIES</h1>
    <div class="btn-group">
      <a href="About.html">About</a>
      <a href="Contact.html">Contact</a>
      <a href="Home.html">Home</a>
      <a href="Movies.html">Movies</a>
      <a href="Series.html">Series</a>
    </div>
  </div>
</section>
<!-- MOVIES GRID -->
<section class="movies" id="movieContainer"></section>

<!-- TRAILER MODAL -->
<div id="trailerModal" class="modal">
  <div class="modal-content">
    <span class="close">&times;</span>
    <iframe id="trailerFrame" src="" frameborder="0" allowfullscreen></iframe>
  </div>
</div>

<footer>© 2025 TRAP MOVIES — Created by TRAP GAD 🔥</footer>
</body>
</html>