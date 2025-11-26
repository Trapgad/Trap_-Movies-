<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
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

<!-- SEARCH -->
<div class="search-bar">
  <input type="text" id="searchInput" placeholder="Search for movies...">
</div>

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

<!-- -------------------- SCRIPTS -------------------- -->
<script>
// TMDB MOVIES API
const TOKEN = "eyJhbGciOiJIUzI1NiJ9.eyJhdWQiOiIxN2ExODM0ZTI3MzMyMGVlZjhhMmEzNmIzOGExMTk2NCIsInN1YiI6IjY4ZWE2MDY4ZmJjYjQxOTVlYjlmZDg2ZCIsInNjb3BlcyI6WyJhcGlfcmVhCJdLCJ2ZXJzaW9uIjoxfQ.iFV2N9KUPakJb_HWWY3eZbB3cUq_gMhM1H9hcnEWD7Q";
const IMG_PATH = "https://image.tmdb.org/t/p/w500";
const movieContainer = document.getElementById("movieContainer");
const searchInput = document.getElementById("searchInput");

async function getMovies(url="https://api.themoviedb.org/3/trending/movie/week"){
  try{ const res=await fetch(url,{headers:{Authorization:`Bearer ${TOKEN}`}}); const data=await res.json(); displayMovies(data.results);}
  catch(err){ console.error(err);}
}
function displayMovies(movies){
  movieContainer.innerHTML="";
  if(!movies||movies.length===0){ movieContainer.innerHTML=`<p style="text-align:center;color:#ff33ff;">No movies found 😢</p>`; return;}
  movies.forEach(movie=>{
    const card=document.createElement("div"); card.classList.add("movie-card");
    card.innerHTML=`<img src="${movie.poster_path?IMG_PATH+movie.poster_path:'https://via.placeholder.com/500x750?text=No+Image'}"><h3>${movie.title}</h3>`;
    card.addEventListener("click",()=>openTrailer(movie.id));
    movieContainer.appendChild(card);
  });
}
let debounceTimer;
searchInput.addEventListener("keyup",(e)=>{ clearTimeout(debounceTimer); debounceTimer=setTimeout(async()=>{
  const query=e.target.value.trim();
  if(query.length>0){
    const res=await fetch(`https://api.themoviedb.org/3/search/movie?query=${query}`,{headers:{Authorization:`Bearer ${TOKEN}`}});
    const data=await res.json(); displayMovies(data.results);
  }else getMovies();
},500);});
async function openTrailer(movieId){
  try{ const res=await fetch(`https://api.themoviedb.org/3/movie/${movieId}/videos`,{headers:{Authorization:`Bearer ${TOKEN}`}});
    const data=await res.json();
    const trailer=data.results.find(v=>v.type==="Trailer"&&v.site==="YouTube");
    if(trailer){ document.getElementById("trailerFrame").src=`https://www.youtube.com/embed/${trailer.key}?autoplay=1`; document.getElementById("trailerModal").style.display="flex"; document.body.classList.add("modal-open"); }
  }catch(err){console.error(err);}
}
document.querySelector(".close").onclick=()=>{ document.getElementById("trailerModal").style.display="none"; document.getElementById("trailerFrame").src=""; document.body.classList.remove("modal-open"); };
window.addEventListener("keydown",e=>{ if(e.key==="Escape"){ document.getElementById("trailerModal").style.display="none"; document.getElementById("trailerFrame").src=""; document.body.classList.remove("modal-open"); }});
getMovies();
</script>

<!-- FIREBASE AUTH -->
<script type="module">
import { initializeApp } from "https://www.gstatic.com/firebasejs/12.6.0/firebase-app.js";
import { getAuth, signOut, onAuthStateChanged } from "https://www.gstatic.com/firebasejs/12.6.0/firebase-auth.js";

const firebaseConfig = {
  apiKey: "AIzaSyBLHlSlMPvwSS5MB8JqG2JB1R-ANIopQZU",
  authDomain: "trap-270792.firebaseapp.com",
  projectId: "trap-270792",
  storageBucket: "trap-270792.firebasestorage.app",
  messagingSenderId: "248838190395",
  appId: "1:248838190395:web:0dd11c0e4427f79470331e",
  measurementId: "G-PG6GXVVKL9"
};

const app = initializeApp(firebaseConfig);
const auth = getAuth(app);
const logoutBtn = document.createElement("button");
logoutBtn.id = "logoutBtn";
logoutBtn.textContent = "Sign Out";
logoutBtn.style.display = "none";
document.body.appendChild(logoutBtn);

function updateAuthButtons(user){
  const buttons = document.querySelectorAll(".btn-group a");
  if(user){ buttons.forEach(btn=>btn.style.display="none"); logoutBtn.style.display="inline-block"; }
  else{ buttons.forEach(btn=>btn.style.display="inline-block"); logoutBtn.style.display="none"; }
}

onAuthStateChanged(auth,(user)=>updateAuthButtons(user));
logoutBtn.onclick=()=>{ signOut(auth).then(()=>{ alert("Signed Out Successfully!"); window.location.href="signin.html"; }).catch(err=>alert(err.message)); }
</script>

</body>
</html>