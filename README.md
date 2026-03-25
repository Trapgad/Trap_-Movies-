<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TRAP MOVIES | Welcome</title>
    
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;600;700;800&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        :root {
            --accent: #E50914;
            --bg-dark: #080808;
            --bg-surface: #121212;
            --border: rgba(255, 255, 255, 0.1);
            --text-main: #FFFFFF;
            --text-dim: #999999;
            --transition: all 0.6s cubic-bezier(0.23, 1, 0.32, 1);
        }

        * { margin: 0; padding: 0; box-sizing: border-box; }

        body {
            font-family: 'Plus Jakarta Sans', sans-serif;
            color: var(--text-main);
            background: var(--bg-dark);
            overflow-x: hidden;
            line-height: 1.6;
        }

        /* --- NAVBAR --- */
        .navbar {
            position: fixed;
            top: 0; width: 100%; z-index: 1000;
            padding: 1.2rem 6%;
            display: flex; justify-content: space-between; align-items: center;
            background: rgba(8, 8, 8, 0.8);
            backdrop-filter: blur(20px);
            border-bottom: 1px solid var(--border);
        }

        .logo {
            font-size: 1.5rem; font-weight: 800; text-transform: uppercase;
            letter-spacing: 2px; color: var(--text-main); text-decoration: none;
        }
        .logo span { color: var(--accent); }

        .nav-links a {
            text-decoration: none; color: var(--text-dim);
            font-size: 0.8rem; font-weight: 700; text-transform: uppercase;
            margin-left: 1.5rem; transition: var(--transition);
        }
        .nav-links a:hover, .nav-links a.active { color: white; }

        /* --- ANIMATIONS --- */
        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(40px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .reveal { opacity: 0; transform: translateY(30px); transition: var(--transition); }
        .reveal.active { opacity: 1; transform: translateY(0); }

        /* --- HERO --- */
        .hero {
            height: 90vh;
            display: flex; align-items: center; justify-content: center;
            text-align: center;
            background: linear-gradient(rgba(0,0,0,0.6), #080808), 
                        url('https://images.unsplash.com/photo-1626814026160-2237a95fc5a0?q=80&w=2000') no-repeat center center/cover;
            padding: 0 6%;
        }

        .hero-content h1 {
            font-size: clamp(2.5rem, 8vw, 4.5rem);
            font-weight: 800; line-height: 1.1;
            margin-bottom: 1.5rem;
            animation: fadeInUp 1s ease-out forwards;
        }

        .hero-content p {
            font-size: 1.1rem; color: var(--text-dim);
            margin-bottom: 2.5rem;
            animation: fadeInUp 1s ease-out 0.2s forwards;
            opacity: 0;
        }

        .btn-group { 
            display: flex; gap: 1rem; justify-content: center; 
            animation: fadeInUp 1s ease-out 0.4s forwards; opacity: 0;
        }

        .btn {
            padding: 1rem 2.5rem; border-radius: 50px; text-decoration: none;
            font-weight: 700; text-transform: uppercase; font-size: 0.9rem;
            transition: var(--transition);
        }
        .btn-primary { background: var(--accent); color: white; }
        .btn-primary:hover { background: #ff1a1a; transform: scale(1.05); box-shadow: 0 10px 20px rgba(229, 9, 20, 0.4); }

        /* --- MOVIE CARDS --- */
        .section-title { padding: 4rem 6% 1rem; font-size: 2rem; font-weight: 800; }

        .movies-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
            gap: 25px; padding: 2rem 6%;
        }

        .movie-card {
            background: var(--bg-surface);
            border-radius: 20px; overflow: hidden;
            border: 1px solid var(--border);
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            cursor: pointer;
        }

        .movie-card:hover {
            transform: translateY(-10px) scale(1.02);
            border-color: var(--accent);
            box-shadow: 0 20px 40px rgba(0,0,0,0.6);
        }

        .movie-card img { width: 100%; aspect-ratio: 2/3; object-fit: cover; transition: 0.5s; }
        .movie-card:hover img { transform: scale(1.1); }

        .movie-info { padding: 15px; background: var(--bg-surface); }
        .movie-info h3 { font-size: 0.95rem; font-weight: 700; }

        footer { text-align: center; padding: 5rem; color: var(--text-dim); border-top: 1px solid var(--border); }

        @media (max-width: 768px) { .nav-links { display: none; } }
    </style>
</head>
<body>

<header class="navbar">
    <a href="index.html" class="logo">TRAP<span>MOVIES</span></a>
    <nav class="nav-links">
        <a href="index.html" class="active">Home</a>
        <a href="Movies.html">Movies</a>
        <a href="Series.html">Series</a>
        <a href="About.html">About</a>
        <a href="Contact.html">Contact</a>
        <a href="Account.html">Account</a>
    </nav>
</header>

<section class="hero">
    <div class="hero-content">
        <h1>Unlimited Cinema.<br>Anywhere.</h1>
        <p>Stream the latest blockbusters and exclusive series in 4K.</p>
        <div class="btn-group">
            <a href="Movies.html" class="btn btn-primary">Browse Library</a>
            <a href="Series.html" class="btn" style="background: rgba(255,255,255,0.1); backdrop-filter: blur(10px); color: white;">Premium Series</a>
        </div>
    </div>
</section>

<div class="section-title reveal">Trending Now</div>
<section class="movies-grid" id="movieContainer"></section>

<footer>© 2026 TRAP MOVIES — CREATED BY TRAP GAD 🔥</footer>

<script>
    // Sample Data
    const movies = [
        { title: "One Piece", img: "https://m.media-amazon.com/images/M/MV5BMmtmZThjMmItNDRkYS00YTM4LTk2MzQtYjk3Y2Y5YmU1YmQyXkEyXkFqcGc@._V1_FMjpg_UX1000_.jpg" },
        { title: "Invincible", img: "https://m.media-amazon.com/images/M/MV5BMmU1N2QxYjMtMDU4OC00YzE2LWFmZTUtMTExMDQ0YmY5ZmYyXkEyXkFqcGc@._V1_FMjpg_UX1000_.jpg" },
        { title: "Jurassic Park", img: "https://m.media-amazon.com/images/M/MV5BMjM2MDgxMDg0Nl5BMl5BanBnXkFtZTgwNTM2OTM5NDE@._V1_.jpg" },
        { title: "Ace Ventura", img: "https://m.media-amazon.com/images/M/MV5BYWExNzg4YzEtNzVjYi00YzU5LWI2ZjgtZDJhYmE0NWIyZDAwXkEyXkFqcGc@._V1_FMjpg_UX1000_.jpg" },
        { title: "Stranger Things", img: "https://m.media-amazon.com/images/M/MV5BMDZkYmVhNjMtNWU4MC00MDQxLWE3MjYtZGJlZDE0N2IyZGEzXkEyXkFqcGc@._V1_FMjpg_UX1000_.jpg" },
        { title: "The Dark Knight", img: "https://m.media-amazon.com/images/M/MV5BMTMxNTMwODM0NF5BMl5BanBnXkFtZTcwODAyMTk2Mw@@._V1_.jpg" }
    ];

    const container = document.getElementById('movieContainer');

    // Create Cards
    movies.forEach((movie, index) => {
        const card = document.createElement('div');
        card.className = 'movie-card reveal';
        // Add staggered delay
        card.style.transitionDelay = (index * 0.1) + 's'; 
        card.innerHTML = `
            <img src="${movie.img}" alt="${movie.title}">
            <div class="movie-info">
                <h3>${movie.title}</h3>
            </div>
        `;
        container.appendChild(card);
    });

    // Scroll Reveal Logic
    const revealElements = () => {
        const elements = document.querySelectorAll('.reveal');
        elements.forEach(el => {
            const windowHeight = window.innerHeight;
            const elementTop = el.getBoundingClientRect().top;
            if (elementTop < windowHeight - 100) {
                el.classList.add('active');
            }
        });
    };

    window.addEventListener('scroll', revealElements);
    window.addEventListener('load', revealElements); // Run on load too
</script>

</body>
</html>
