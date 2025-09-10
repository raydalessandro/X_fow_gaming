# X_fow_gaming
Web site demo
<!DOCTYPE html>
<html lang="it">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="xFoW Gaming - 15 anni di eccellenza nel gaming competitivo italiano. Team professionale di Call of Duty, Clash Royale e altro.">
    <title>xFoW Gaming - Flags of War | Team eSports Italiano</title>
    
    <!-- Font Awesome per icone -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary-dark: #0a0a0a;
            --secondary-dark: #1a1a1a;
            --accent-blue: #00d4ff;
            --accent-green: #00ff88;
            --accent-red: #ff0040;
            --text-primary: #ffffff;
            --text-secondary: #b0b0b0;
            --italy-green: #009246;
            --italy-red: #ce2b37;
        }

        body {
            font-family: 'Arial', sans-serif;
            background: var(--primary-dark);
            color: var(--text-primary);
            overflow-x: hidden;
        }

        /* Navbar */
        .navbar {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(10, 10, 10, 0.95);
            backdrop-filter: blur(10px);
            z-index: 1000;
            padding: 1rem 0;
            transition: all 0.3s ease;
        }

        .nav-container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            display: flex;
            align-items: center;
            font-size: 1.8rem;
            font-weight: bold;
            text-decoration: none;
            color: var(--text-primary);
        }

        .logo-icon {
            width: 50px;
            height: 50px;
            margin-right: 1rem;
            background: linear-gradient(135deg, var(--italy-green), white, var(--italy-red));
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            color: var(--primary-dark);
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            color: var(--text-secondary);
            text-decoration: none;
            transition: all 0.3s ease;
            position: relative;
            padding: 0.5rem 0;
        }

        .nav-links a:hover {
            color: var(--accent-blue);
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--accent-blue);
            transition: width 0.3s ease;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .mobile-menu {
            display: none;
            color: var(--text-primary);
            font-size: 1.5rem;
            cursor: pointer;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            position: relative;
            display: flex;
            align-items: center;
            justify-content: center;
            background: linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.7)), url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1920 1080"><rect fill="%230a0a0a"/><g opacity="0.1"><path fill="%2300d4ff" d="M0 540L80 520L160 560L240 530L320 550L400 540L480 520L560 560L640 530L720 550L800 540L880 520L960 560L1040 530L1120 550L1200 540L1280 520L1360 560L1440 530L1520 550L1600 540L1680 520L1760 560L1840 530L1920 550V1080H0V540Z"/></g></svg>');
            background-size: cover;
            background-position: center;
            overflow: hidden;
        }

        .hero-content {
            text-align: center;
            z-index: 2;
            animation: fadeInUp 1s ease;
        }

        .hero-title {
            font-size: 4rem;
            margin-bottom: 1rem;
            background: linear-gradient(45deg, var(--accent-blue), var(--accent-green));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            text-shadow: 0 0 30px rgba(0, 212, 255, 0.5);
        }

        .hero-subtitle {
            font-size: 1.5rem;
            color: var(--text-secondary);
            margin-bottom: 2rem;
        }

        .hero-stats {
            display: flex;
            justify-content: center;
            gap: 3rem;
            margin: 2rem 0;
        }

        .stat-item {
            text-align: center;
        }

        .stat-number {
            font-size: 2.5rem;
            font-weight: bold;
            color: var(--accent-blue);
        }

        .stat-label {
            color: var(--text-secondary);
            font-size: 0.9rem;
            text-transform: uppercase;
        }

        .cta-buttons {
            display: flex;
            gap: 1rem;
            justify-content: center;
            margin-top: 2rem;
        }

        .btn {
            padding: 1rem 2rem;
            border: none;
            border-radius: 5px;
            font-size: 1rem;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
            display: inline-block;
        }

        .btn-primary {
            background: linear-gradient(45deg, var(--accent-blue), var(--accent-green));
            color: var(--primary-dark);
        }

        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 30px rgba(0, 212, 255, 0.3);
        }

        .btn-secondary {
            background: transparent;
            color: var(--text-primary);
            border: 2px solid var(--accent-blue);
        }

        .btn-secondary:hover {
            background: var(--accent-blue);
            color: var(--primary-dark);
        }

        /* Games Section */
        .games-section {
            padding: 5rem 2rem;
            background: var(--secondary-dark);
        }

        .container {
            max-width: 1400px;
            margin: 0 auto;
        }

        .section-title {
            text-align: center;
            font-size: 3rem;
            margin-bottom: 3rem;
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 3px;
            background: linear-gradient(90deg, var(--italy-green), white, var(--italy-red));
        }

        .games-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .game-card {
            background: var(--primary-dark);
            border-radius: 10px;
            overflow: hidden;
            transition: all 0.3s ease;
            border: 1px solid rgba(0, 212, 255, 0.1);
        }

        .game-card:hover {
            transform: translateY(-10px);
            border-color: var(--accent-blue);
            box-shadow: 0 20px 40px rgba(0, 212, 255, 0.2);
        }

        .game-image {
            width: 100%;
            height: 200px;
            background: linear-gradient(135deg, #1a1a1a, #2a2a2a);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3rem;
            color: var(--accent-blue);
        }

        .game-info {
            padding: 1.5rem;
        }

        .game-title {
            font-size: 1.5rem;
            margin-bottom: 0.5rem;
            color: var(--accent-blue);
        }

        .game-description {
            color: var(--text-secondary);
            line-height: 1.6;
            margin-bottom: 1rem;
        }

        .game-stats {
            display: flex;
            gap: 1rem;
            font-size: 0.9rem;
            color: var(--text-secondary);
        }

        /* Achievements Section */
        .achievements {
            padding: 5rem 2rem;
            background: var(--primary-dark);
        }

        .achievements-timeline {
            position: relative;
            max-width: 1000px;
            margin: 0 auto;
            padding: 2rem 0;
        }

        .timeline-item {
            display: flex;
            margin-bottom: 3rem;
            align-items: center;
            opacity: 0;
            animation: fadeInLeft 1s ease forwards;
        }

        .timeline-item:nth-child(even) {
            flex-direction: row-reverse;
            animation: fadeInRight 1s ease forwards;
        }

        .timeline-date {
            flex: 0 0 150px;
            text-align: center;
            font-size: 1.2rem;
            color: var(--accent-blue);
            font-weight: bold;
        }

        .timeline-content {
            flex: 1;
            background: var(--secondary-dark);
            padding: 1.5rem;
            border-radius: 10px;
            border-left: 3px solid var(--accent-blue);
            margin: 0 2rem;
        }

        .timeline-title {
            font-size: 1.3rem;
            margin-bottom: 0.5rem;
            color: var(--text-primary);
        }

        .timeline-description {
            color: var(--text-secondary);
        }

        /* Partners Section */
        .partners {
            padding: 5rem 2rem;
            background: var(--secondary-dark);
        }

        .partners-grid {
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 4rem;
            margin-top: 3rem;
        }

        .partner-card {
            background: var(--primary-dark);
            padding: 2rem;
            border-radius: 10px;
            text-align: center;
            transition: all 0.3s ease;
            border: 1px solid rgba(0, 212, 255, 0.1);
        }

        .partner-card:hover {
            transform: scale(1.05);
            border-color: var(--accent-blue);
        }

        .partner-logo {
            font-size: 3rem;
            color: var(--accent-blue);
            margin-bottom: 1rem;
        }

        .partner-name {
            font-size: 1.5rem;
            margin-bottom: 0.5rem;
        }

        /* News Section */
        .news {
            padding: 5rem 2rem;
            background: var(--primary-dark);
        }

        .news-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .news-card {
            background: var(--secondary-dark);
            border-radius: 10px;
            overflow: hidden;
            transition: all 0.3s ease;
        }

        .news-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 30px rgba(0, 212, 255, 0.1);
        }

        .news-image {
            width: 100%;
            height: 200px;
            background: linear-gradient(135deg, #2a2a2a, #1a1a1a);
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--accent-blue);
        }

        .news-content {
            padding: 1.5rem;
        }

        .news-date {
            color: var(--accent-blue);
            font-size: 0.9rem;
            margin-bottom: 0.5rem;
        }

        .news-title {
            font-size: 1.3rem;
            margin-bottom: 1rem;
            color: var(--text-primary);
        }

        .news-excerpt {
            color: var(--text-secondary);
            line-height: 1.6;
        }

        /* Footer */
        .footer {
            background: var(--primary-dark);
            padding: 3rem 2rem 1rem;
            border-top: 1px solid rgba(0, 212, 255, 0.1);
        }

        .footer-content {
            max-width: 1400px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 3rem;
            margin-bottom: 2rem;
        }

        .footer-section h3 {
            color: var(--accent-blue);
            margin-bottom: 1rem;
        }

        .footer-section ul {
            list-style: none;
        }

        .footer-section li {
            margin-bottom: 0.5rem;
        }

        .footer-section a {
            color: var(--text-secondary);
            text-decoration: none;
            transition: color 0.3s ease;
        }

        .footer-section a:hover {
            color: var(--accent-blue);
        }

        .social-links {
            display: flex;
            gap: 1rem;
            margin-top: 1rem;
        }

        .social-links a {
            width: 40px;
            height: 40px;
            background: var(--secondary-dark);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--text-secondary);
            transition: all 0.3s ease;
        }

        .social-links a:hover {
            background: var(--accent-blue);
            color: var(--primary-dark);
            transform: translateY(-3px);
        }

        .footer-bottom {
            text-align: center;
            padding-top: 2rem;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            color: var(--text-secondary);
        }

        /* Animations */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes fadeInLeft {
            from {
                opacity: 0;
                transform: translateX(-30px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        @keyframes fadeInRight {
            from {
                opacity: 0;
                transform: translateX(30px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        /* Responsive */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }

            .mobile-menu {
                display: block;
            }

            .hero-title {
                font-size: 2.5rem;
            }

            .hero-subtitle {
                font-size: 1.2rem;
            }

            .hero-stats {
                flex-direction: column;
                gap: 1rem;
            }

            .cta-buttons {
                flex-direction: column;
            }

            .btn {
                width: 100%;
            }

            .timeline-item,
            .timeline-item:nth-child(even) {
                flex-direction: column;
            }

            .timeline-date {
                margin-bottom: 1rem;
            }

            .partners-grid {
                flex-direction: column;
                gap: 2rem;
            }
        }
    </style>
</head>
<body>
    <!-- Navbar -->
    <nav class="navbar">
        <div class="nav-container">
            <a href="index.html" class="logo">
                <div class="logo-icon">xFoW</div>
                <span>xFoW Gaming</span>
            </a>
            <ul class="nav-links">
                <li><a href="index.html">Home</a></li>
                <li><a href="about.html">Chi Siamo</a></li>
                <li><a href="teams.html">Teams</a></li>
                <li><a href="news.html">News</a></li>
                <li><a href="community.html">Community</a></li>
                <li><a href="contact.html">Contatti</a></li>
            </ul>
            <div class="mobile-menu">
                <i class="fas fa-bars"></i>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-content">
            <h1 class="hero-title">xFoW Gaming</h1>
            <p class="hero-subtitle">15 anni di eccellenza nel gaming competitivo italiano</p>
            
            <div class="hero-stats">
                <div class="stat-item">
                    <div class="stat-number">15+</div>
                    <div class="stat-label">Anni di Storia</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">500+</div>
                    <div class="stat-label">Membri Community</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">5</div>
                    <div class="stat-label">Giochi Competitivi</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">100+</div>
                    <div class="stat-label">Tornei Giocati</div>
                </div>
            </div>

            <div class="cta-buttons">
                <a href="contact.html" class="btn btn-primary">Unisciti a Noi</a>
                <a href="about.html" class="btn btn-secondary">Scopri di Più</a>
            </div>
        </div>
    </section>

    <!-- Games Section -->
    <section class="games-section">
        <div class="container">
            <h2 class="section-title">I Nostri Giochi</h2>
            
            <div class="games-grid">
                <div class="game-card">
                    <div class="game-image">
                        <i class="fas fa-crosshairs"></i>
                    </div>
                    <div class="game-info">
                        <h3 class="game-title">Call of Duty</h3>
                        <p class="game-description">
                            Il nostro gioco principale dal 2010. Competiamo nei principali tornei nazionali e internazionali con team dedicati per ogni modalità.
                        </p>
                        <div class="game-stats">
                            <span><i class="fas fa-users"></i> 20+ Giocatori</span>
                            <span><i class="fas fa-trophy"></i> 50+ Vittorie</span>
                        </div>
                    </div>
                </div>

                <div class="game-card">
                    <div class="game-image">
                        <i class="fas fa-crown"></i>
                    </div>
                    <div class="game-info">
                        <h3 class="game-title">Clash Royale</h3>
                        <p class="game-description">
                            Clan top italiano con oltre 75,000 trofei. Partecipiamo attivamente alle guerre tra clan e tornei competitivi.
                        </p>
                        <div class="game-stats">
                            <span><i class="fas fa-users"></i> 46/50 Membri</span>
                            <span><i class="fas fa-trophy"></i> 75,782 Trofei</span>
                        </div>
                    </div>
                </div>

                <div class="game-card">
                    <div class="game-image">
                        <i class="fas fa-shield-alt"></i>
                    </div>
                    <div class="game-info">
                        <h3 class="game-title">Destiny 2</h3>
                        <p class="game-description">
                            Clan attivo su PlayStation con focus su Raid, Trials of Osiris e contenuti endgame. Community unita e sempre pronta ad aiutare.
                        </p>
                        <div class="game-stats">
                            <span><i class="fas fa-users"></i> 30+ Guardiani</span>
                            <span><i class="fas fa-star"></i> Livello Max</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Achievements Section -->
    <section class="achievements">
        <div class="container">
            <h2 class="section-title">La Nostra Storia</h2>
            
            <div class="achievements-timeline">
                <div class="timeline-item">
                    <div class="timeline-date">2010</div>
                    <div class="timeline-content">
                        <h3 class="timeline-title">Fondazione xFoW Gaming</h3>
                        <p class="timeline-description">Nasce xFoW Gaming, inizia l'avventura nel gaming competitivo italiano.</p>
                    </div>
                </div>

                <div class="timeline-item">
                    <div class="timeline-date">2015</div>
                    <div class="timeline-content">
                        <h3 class="timeline-title">Espansione Mobile</h3>
                        <p class="timeline-description">Entriamo nel mondo del mobile gaming con Clash Royale e Clash of Clans.</p>
                    </div>
                </div>

                <div class="timeline-item">
                    <div class="timeline-date">2020</div>
                    <div class="timeline-content">
                        <h3 class="timeline-title">500+ Membri</h3>
                        <p class="timeline-description">La community raggiunge oltre 500 membri attivi su tutte le piattaforme.</p>
                    </div>
                </div>

                <div class="timeline-item">
                    <div class="timeline-date">2024</div>
                    <div class="timeline-content">
                        <h3 class="timeline-title">Partnership Brescia eSports</h3>
                        <p class="timeline-description">Stringiamo una partnership strategica con Brescia eSports per il futuro competitivo.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Partners Section -->
    <section class="partners">
        <div class="container">
            <h2 class="section-title">I Nostri Partner</h2>
            
            <div class="partners-grid">
                <div class="partner-card">
                    <div class="partner-logo">
                        <i class="fas fa-handshake"></i>
                    </div>
                    <h3 class="partner-name">Brescia eSports</h3>
                    <p>Partner strategico per competizioni e sviluppo</p>
                </div>
            </div>
        </div>
    </section>

    <!-- News Section -->
    <section class="news">
        <div class="container">
            <h2 class="section-title">Ultime News</h2>
            
            <div class="news-grid">
                <div class="news-card">
                    <div class="news-image">
                        <i class="fas fa-newspaper fa-3x"></i>
                    </div>
                    <div class="news-content">
                        <div class="news-date">10 Settembre 2025</div>
                        <h3 class="news-title">Nuovo Sito Web Online!</h3>
                        <p class="news-excerpt">
                            Siamo entusiasti di presentare il nostro nuovo sito web, completamente ridisegnato per offrire la migliore esperienza alla nostra community.
                        </p>
                    </div>
                </div>

                <div class="news-card">
                    <div class="news-image">
                        <i class="fas fa-trophy fa-3x"></i>
                    </div>
                    <div class="news-content">
                        <div class="news-date">5 Settembre 2025</div>
                        <h3 class="news-title">Secondo Posto al Torneo Nazionale</h3>
                        <p class="news-excerpt">
                            Il nostro team di Call of Duty conquista un incredibile secondo posto al torneo nazionale, dimostrando ancora una volta il nostro valore competitivo.
                        </p>
                    </div>
                </div>

                <div class="news-card">
                    <div class="news-image">
                        <i class="fas fa-users fa-3x"></i>
                    </div>
                    <div class="news-content">
                        <div class="news-date">1 Settembre 2025</div>
                        <h3 class="news-title">Recruitment Aperto!</h3>
                        <p class="news-excerpt">
                            Stiamo cercando nuovi talenti per i nostri roster di Call of Duty e Clash Royale. Unisciti a noi e diventa parte della famiglia xFoW!
                        </p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="footer">
        <div class="footer-content">
            <div class="footer-section">
                <h3>xFoW Gaming</h3>
                <p>15 anni di eccellenza nel gaming competitivo italiano. Unisciti alla famiglia Flags of War!</p>
                <div class="social-links">
                    <a href="https://www.facebook.com/xFoWGaminG" target="_blank">
                        <i class="fab fa-facebook"></i>
                    </a>
                    <a href="https://www.instagram.com/xfow_gaming" target="_blank">
                        <i class="fab fa-instagram"></i>
                    </a>
                    <a href="#" target="_blank">
                        <i class="fab fa-discord"></i>
                    </a>
                    <a href="#" target="_blank">
                        <i class="fab fa-twitch"></i>
                    </a>
                </div>
            </div>

            <div class="footer-section">
                <h3>Link Rapidi</h3>
                <ul>
                    <li><a href="about.html">Chi Siamo</a></li>
                    <li><a href="teams.html">I Nostri Team</a></li>
                    <li><a href="news.html">News & Aggiornamenti</a></li>
                    <li><a href="contact.html">Contattaci</a></li>
                </ul>
            </div>

            <div class="footer-section">
                <h3>Giochi</h3>
                <ul>
                    <li><a href="#">Call of Duty</a></li>
                    <li><a href="#">Clash Royale</a></li>
                    <li><a href="#">Destiny 2</a></li>
                    <li><a href="#">Warzone</a></li>
                </ul>
            </div>

            <div class="footer-section">
                <h3>Community</h3>
                <ul>
                    <li><a href="#">Discord Server</a></li>
                    <li><a href="#">Forum</a></li>
                    <li><a href="#">Regolamento</a></li>
                    <li><a href="#">FAQ</a></li>
                </ul>
            </div>
        </div>

        <div class="footer-bottom">
            <p>&copy; 2025 xFoW Gaming - Flags of War. Tutti i diritti riservati. | In partnership con Brescia eSports 🇮🇹</p>
        </div>
    </footer>

    <script>
        // Mobile menu toggle
        document.querySelector('.mobile-menu').addEventListener('click', function() {
            const navLinks = document.querySelector('.nav-links');
            navLinks.style.display = navLinks.style.display === 'flex' ? 'none' : 'flex';
            navLinks.style.position = 'absolute';
            navLinks.style.top = '100%';
            navLinks.style.left = '0';
            navLinks.style.right = '0';
            navLinks.style.background = 'var(--primary-dark)';
            navLinks.style.flexDirection = 'column';
            navLinks.style.padding = '1rem';
        });

        // Navbar scroll effect
        window.addEventListener('scroll', function() {
            const navbar = document.querySelector('.navbar');
            if (window.scrollY > 100) {
                navbar.style.background = 'rgba(10, 10, 10, 0.98)';
                navbar.style.boxShadow = '0 5px 20px rgba(0, 0, 0, 0.5)';
            } else {
                navbar.style.background = 'rgba(10, 10, 10, 0.95)';
                navbar.style.boxShadow = 'none';
            }
        });

        // Animate elements on scroll
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver(function(entries) {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        document.querySelectorAll('.game-card, .news-card, .partner-card').forEach(el => {
            el.style.opacity = '0';
            el.style.transform = 'translateY(20px)';
            el.style.transition = 'all 0.6s ease';
            observer.observe(el);
        });
    </script>
</body>
</html>
