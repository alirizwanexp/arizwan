<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Arizwan - Computer Science & AI Portfolio">
    <meta name="keywords" content="Arizwan, Computer Science, AI, Portfolio, Developer">
    <meta name="author" content="Arizwan">
    <title>Arizwan - AI & Computer Science Portfolio</title>
    
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Roboto:wght@300;400;500;700&display=swap" rel="stylesheet">
    
    <!-- Font Awesome -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        :root {
            --bg-primary: #0a0e27;
            --bg-secondary: #151933;
            --bg-card: #1a1f3a;
            --text-primary: #ffffff;
            --text-secondary: #a8b2d1;
            --accent-cyan: #00d9ff;
            --accent-purple: #9d50bb;
            --accent-blue: #0066ff;
            --glow-cyan: 0 0 10px #00d9ff, 0 0 20px #00d9ff, 0 0 30px #00d9ff;
            --glow-purple: 0 0 10px #9d50bb, 0 0 20px #9d50bb, 0 0 30px #9d50bb;
            --transition: all 0.3s ease;
        }
        
        [data-theme="light"] {
            --bg-primary: #f5f7fa;
            --bg-secondary: #e9ecef;
            --bg-card: #ffffff;
            --text-primary: #212529;
            --text-secondary: #495057;
            --accent-cyan: #00b4d8;
            --accent-purple: #7209b7;
            --accent-blue: #0066ff;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        html {
            scroll-behavior: smooth;
        }
        
        body {
            font-family: 'Roboto', sans-serif;
            background-color: var(--bg-primary);
            color: var(--text-primary);
            line-height: 1.6;
            overflow-x: hidden;
            transition: var(--transition);
        }
        
        h1, h2, h3, h4, h5, h6 {
            font-family: 'Orbitron', monospace;
            font-weight: 700;
            margin-bottom: 1rem;
        }
        
        a {
            text-decoration: none;
            color: var(--accent-cyan);
            transition: var(--transition);
        }
        
        a:hover {
            color: var(--accent-purple);
        }
        
        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* Header/Navbar */
        header {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(10, 14, 39, 0.9);
            backdrop-filter: blur(10px);
            z-index: 1000;
            padding: 1rem 0;
            transition: var(--transition);
            border-bottom: 1px solid rgba(0, 217, 255, 0.3);
        }
        
        [data-theme="light"] header {
            background: rgba(245, 247, 250, 0.9);
            border-bottom: 1px solid rgba(0, 180, 216, 0.3);
        }
        
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            font-family: 'Orbitron', monospace;
            font-size: 1.8rem;
            font-weight: 900;
            background: linear-gradient(45deg, var(--accent-cyan), var(--accent-purple));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }
        
        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }
        
        .nav-links a {
            color: var(--text-secondary);
            font-weight: 500;
            position: relative;
            transition: var(--transition);
        }
        
        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--accent-cyan);
            transition: width 0.3s ease;
        }
        
        .nav-links a:hover::after,
        .nav-links a.active::after {
            width: 100%;
        }
        
        .nav-links a:hover,
        .nav-links a.active {
            color: var(--text-primary);
        }
        
        .theme-toggle {
            background: none;
            border: none;
            color: var(--text-primary);
            font-size: 1.2rem;
            cursor: pointer;
            transition: var(--transition);
        }
        
        .theme-toggle:hover {
            color: var(--accent-cyan);
            transform: rotate(180deg);
        }
        
        /* Mobile Menu */
        .mobile-menu {
            display: none;
            flex-direction: column;
            cursor: pointer;
        }
        
        .mobile-menu span {
            width: 25px;
            height: 3px;
            background: var(--text-primary);
            margin: 3px 0;
            transition: var(--transition);
        }
        
        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            overflow: hidden;
            padding-top: 80px;
        }
        
        .hero-bg {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            opacity: 0.3;
        }
        
        .hero-content {
            display: flex;
            align-items: center;
            justify-content: space-between;
            width: 100%;
            gap: 3rem;
        }
        
        .hero-text {
            flex: 1;
            animation: fadeInLeft 1s ease;
        }
        
        .hero-text h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            background: linear-gradient(45deg, var(--accent-cyan), var(--accent-purple));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }
        
        .hero-text p {
            font-size: 1.2rem;
            color: var(--text-secondary);
            margin-bottom: 2rem;
        }
        
        .btn {
            display: inline-block;
            padding: 12px 30px;
            background: linear-gradient(45deg, var(--accent-cyan), var(--accent-purple));
            color: white;
            border: none;
            border-radius: 50px;
            font-weight: 500;
            cursor: pointer;
            transition: var(--transition);
            position: relative;
            overflow: hidden;
            z-index: 1;
        }
        
        .btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: rgba(255, 255, 255, 0.2);
            transition: left 0.5s ease;
            z-index: -1;
        }
        
        .btn:hover::before {
            left: 100%;
        }
        
        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(0, 217, 255, 0.3);
        }
        
        .hero-image {
            flex: 0 0 40%;
            position: relative;
            animation: fadeInRight 1s ease;
        }
        
        .hero-image img {
            width: 100%;
            border-radius: 20px;
            border: 3px solid var(--accent-cyan);
            box-shadow: var(--glow-cyan);
        }
        
        /* Circuit Animation */
        .circuit {
            position: absolute;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            z-index: -1;
            opacity: 0.1;
        }
        
        .circuit-line {
            position: absolute;
            background: var(--accent-cyan);
            opacity: 0.5;
        }
        
        .circuit-node {
            position: absolute;
            width: 8px;
            height: 8px;
            background: var(--accent-cyan);
            border-radius: 50%;
            box-shadow: var(--glow-cyan);
        }
        
        /* Section Styles */
        section {
            padding: 80px 0;
            position: relative;
        }
        
        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 3rem;
            position: relative;
            display: inline-block;
            width: 100%;
        }
        
        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 3px;
            background: linear-gradient(90deg, var(--accent-cyan), var(--accent-purple));
        }
        
        /* About Section */
        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
            align-items: center;
        }
        
        .about-text p {
            color: var(--text-secondary);
            margin-bottom: 2rem;
        }
        
        .skills {
            display: flex;
            flex-wrap: wrap;
            gap: 1rem;
            margin-bottom: 2rem;
        }
        
        .skill-tag {
            padding: 8px 16px;
            background: var(--bg-card);
            border: 1px solid var(--accent-cyan);
            border-radius: 20px;
            font-size: 0.9rem;
            color: var(--accent-cyan);
            transition: var(--transition);
        }
        
        .skill-tag:hover {
            background: var(--accent-cyan);
            color: var(--bg-primary);
            transform: translateY(-3px);
        }
        
        .timeline {
            position: relative;
            padding-left: 30px;
        }
        
        .timeline::before {
            content: '';
            position: absolute;
            left: 0;
            top: 0;
            width: 2px;
            height: 100%;
            background: var(--accent-cyan);
        }
        
        .timeline-item {
            position: relative;
            padding-bottom: 2rem;
        }
        
        .timeline-item::before {
            content: '';
            position: absolute;
            left: -34px;
            top: 5px;
            width: 10px;
            height: 10px;
            background: var(--accent-cyan);
            border-radius: 50%;
            box-shadow: var(--glow-cyan);
        }
        
        .timeline-date {
            color: var(--accent-purple);
            font-weight: 500;
            margin-bottom: 0.5rem;
        }
        
        /* Projects Section */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 2rem;
        }
        
        .project-card {
            background: var(--bg-card);
            border-radius: 15px;
            overflow: hidden;
            transition: var(--transition);
            border: 1px solid rgba(0, 217, 255, 0.2);
        }
        
        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 217, 255, 0.3);
            border-color: var(--accent-cyan);
        }
        
        .project-image {
            height: 200px;
            background: linear-gradient(45deg, var(--bg-secondary), var(--bg-card));
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3rem;
            color: var(--accent-cyan);
        }
        
        .project-content {
            padding: 1.5rem;
        }
        
        .project-title {
            font-size: 1.3rem;
            margin-bottom: 0.5rem;
        }
        
        .project-description {
            color: var(--text-secondary);
            margin-bottom: 1rem;
        }
        
        .project-tech {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin-bottom: 1rem;
        }
        
        .tech-icon {
            width: 30px;
            height: 30px;
            background: var(--bg-secondary);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 0.9rem;
            color: var(--accent-cyan);
        }
        
        /* Achievements Section */
        .achievements-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 2rem;
        }
        
        .achievement-card {
            background: var(--bg-card);
            border-radius: 15px;
            padding: 2rem;
            text-align: center;
            transition: var(--transition);
            border: 1px solid rgba(157, 80, 187, 0.2);
        }
        
        .achievement-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(157, 80, 187, 0.3);
            border-color: var(--accent-purple);
        }
        
        .achievement-icon {
            font-size: 3rem;
            color: var(--accent-purple);
            margin-bottom: 1rem;
        }
        
        /* Studies Section */
        .studies-timeline {
            position: relative;
            max-width: 800px;
            margin: 0 auto;
        }
        
        .studies-timeline::before {
            content: '';
            position: absolute;
            left: 50%;
            top: 0;
            width: 2px;
            height: 100%;
            background: var(--accent-purple);
            transform: translateX(-50%);
        }
        
        .study-item {
            position: relative;
            padding: 2rem 0;
            width: 50%;
        }
        
        .study-item:nth-child(odd) {
            left: 0;
            padding-right: 3rem;
            text-align: right;
        }
        
        .study-item:nth-child(even) {
            left: 50%;
            padding-left: 3rem;
        }
        
        .study-item::before {
            content: '';
            position: absolute;
            width: 20px;
            height: 20px;
            background: var(--accent-purple);
            border-radius: 50%;
            top: 2.5rem;
            box-shadow: var(--glow-purple);
        }
        
        .study-item:nth-child(odd)::before {
            right: -10px;
        }
        
        .study-item:nth-child(even)::before {
            left: -10px;
        }
        
        .study-content {
            background: var(--bg-card);
            padding: 1.5rem;
            border-radius: 10px;
            border: 1px solid rgba(157, 80, 187, 0.2);
        }
        
        /* Certificates Section */
        .certificates-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 2rem;
        }
        
        .certificate-card {
            background: var(--bg-card);
            border-radius: 15px;
            overflow: hidden;
            transition: var(--transition);
            cursor: pointer;
            border: 1px solid rgba(0, 102, 255, 0.2);
        }
        
        .certificate-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 102, 255, 0.3);
            border-color: var(--accent-blue);
        }
        
        .certificate-image {
            height: 200px;
            background: linear-gradient(45deg, var(--bg-secondary), var(--bg-card));
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3rem;
            color: var(--accent-blue);
        }
        
        .certificate-content {
            padding: 1.5rem;
        }
        
        /* Gallery Section */
        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 1rem;
        }
        
        .gallery-item {
            position: relative;
            overflow: hidden;
            border-radius: 10px;
            height: 250px;
            cursor: pointer;
            transition: var(--transition);
        }
        
        .gallery-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
        }
        
        .gallery-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.7);
            display: flex;
            align-items: center;
            justify-content: center;
            opacity: 0;
            transition: var(--transition);
        }
        
        .gallery-item:hover .gallery-overlay {
            opacity: 1;
        }
        
        .gallery-item:hover img {
            transform: scale(1.1);
        }
        
        /* Contact Section */
        .contact-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
        }
        
        .contact-form {
            background: var(--bg-card);
            padding: 2rem;
            border-radius: 15px;
            border: 1px solid rgba(0, 217, 255, 0.2);
        }
        
        .form-group {
            margin-bottom: 1.5rem;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            color: var(--text-secondary);
        }
        
        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 12px;
            background: var(--bg-secondary);
            border: 1px solid rgba(0, 217, 255, 0.3);
            border-radius: 8px;
            color: var(--text-primary);
            transition: var(--transition);
        }
        
        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: var(--accent-cyan);
            box-shadow: 0 0 0 2px rgba(0, 217, 255, 0.2);
        }
        
        .contact-info {
            display: flex;
            flex-direction: column;
            gap: 2rem;
        }
        
        .contact-item {
            display: flex;
            align-items: center;
            gap: 1rem;
        }
        
        .contact-icon {
            width: 50px;
            height: 50px;
            background: var(--bg-card);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.2rem;
            color: var(--accent-cyan);
            border: 1px solid rgba(0, 217, 255, 0.3);
        }
        
        .social-links {
            display: flex;
            gap: 1rem;
            margin-top: 2rem;
        }
        
        .social-link {
            width: 40px;
            height: 40px;
            background: var(--bg-card);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--text-primary);
            transition: var(--transition);
            border: 1px solid rgba(0, 217, 255, 0.3);
        }
        
        .social-link:hover {
            background: var(--accent-cyan);
            color: var(--bg-primary);
            transform: translateY(-5px);
        }
        
        /* Footer */
        footer {
            background: var(--bg-secondary);
            padding: 3rem 0 1rem;
            border-top: 1px solid rgba(0, 217, 255, 0.3);
            text-align: center;
        }
        
        .footer-nav {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin-bottom: 2rem;
        }
        
        .footer-nav a {
            color: var(--text-secondary);
            transition: var(--transition);
        }
        
        .footer-nav a:hover {
            color: var(--accent-cyan);
        }
        
        .copyright {
            color: var(--text-secondary);
            font-size: 0.9rem;
            padding-top: 2rem;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        /* Lightbox */
        .lightbox {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.9);
            display: none;
            align-items: center;
            justify-content: center;
            z-index: 2000;
            cursor: pointer;
        }
        
        .lightbox-content {
            max-width: 90%;
            max-height: 90%;
            position: relative;
        }
        
        .lightbox-content img {
            width: 100%;
            height: 100%;
            object-fit: contain;
        }
        
        .lightbox-close {
            position: absolute;
            top: -40px;
            right: 0;
            color: white;
            font-size: 2rem;
            cursor: pointer;
        }
        
        /* Animations */
        @keyframes fadeInLeft {
            from {
                opacity: 0;
                transform: translateX(-50px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }
        
        @keyframes fadeInRight {
            from {
                opacity: 0;
                transform: translateX(50px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }
        
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.8s ease;
        }
        
        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }
        
        /* Responsive */
        @media (max-width: 992px) {
            .hero-content {
                flex-direction: column;
                text-align: center;
            }
            
            .hero-image {
                flex: 0 0 60%;
            }
            
            .about-content,
            .contact-content {
                grid-template-columns: 1fr;
            }
            
            .study-item {
                width: 100%;
                left: 0 !important;
                padding-left: 3rem !important;
                padding-right: 0 !important;
                text-align: left !important;
            }
            
            .study-item::before {
                left: -10px !important;
            }
            
            .studies-timeline::before {
                left: 0;
            }
        }
        
        @media (max-width: 768px) {
            .nav-links {
                position: fixed;
                top: 70px;
                left: -100%;
                width: 100%;
                height: calc(100vh - 70px);
                background: var(--bg-primary);
                flex-direction: column;
                align-items: center;
                justify-content: start;
                padding-top: 2rem;
                transition: left 0.3s ease;
            }
            
            .nav-links.active {
                left: 0;
            }
            
            .mobile-menu {
                display: flex;
            }
            
            .mobile-menu.active span:nth-child(1) {
                transform: rotate(45deg) translate(5px, 5px);
            }
            
            .mobile-menu.active span:nth-child(2) {
                opacity: 0;
            }
            
            .mobile-menu.active span:nth-child(3) {
                transform: rotate(-45deg) translate(7px, -6px);
            }
            
            .hero-text h1 {
                font-size: 2.5rem;
            }
            
            .projects-grid,
            .achievements-grid,
            .certificates-grid {
                grid-template-columns: 1fr;
            }
            
            .gallery-grid {
                grid-template-columns: repeat(2, 1fr);
            }
        }
        
        @media (max-width: 480px) {
            .hero-text h1 {
                font-size: 2rem;
            }
            
            .gallery-grid {
                grid-template-columns: 1fr;
            }
            
            .footer-nav {
                flex-direction: column;
                gap: 1rem;
            }
        }
    </style>
</head>
<body>
    <!-- Header/Navbar -->
    <header>
        <nav class="container">
            <div class="logo">Arizwan</div>
            <ul class="nav-links">
                <li><a href="#home" class="nav-link active">Home</a></li>
                <li><a href="#about" class="nav-link">About</a></li>
                <li><a href="#projects" class="nav-link">Projects</a></li>
                <li><a href="#achievements" class="nav-link">Achievements</a></li>
                <li><a href="#studies" class="nav-link">Studies</a></li>
                <li><a href="#certificates" class="nav-link">Certificates</a></li>
                <li><a href="#gallery" class="nav-link">Gallery</a></li>
                <li><a href="#contact" class="nav-link">Contact</a></li>
            </ul>
            <button class="theme-toggle" id="theme-toggle">
                <i class="fas fa-moon"></i>
            </button>
            <div class="mobile-menu" id="mobile-menu">
                <span></span>
                <span></span>
                <span></span>
            </div>
        </nav>
    </header>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="hero-bg">
            <canvas id="hero-canvas"></canvas>
        </div>
        <div class="container">
            <div class="hero-content">
                <div class="hero-text">
                    <h1>Hi, I'm Arizwan</h1>
                    <p>A Computer Science & AI enthusiast, developer, and creator.</p>
                    <a href="#projects" class="btn">Explore My Work</a>
                </div>
                <div class="hero-image">
                    <img src="https://via.placeholder.com/400x400" alt="Arizwan">
                </div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="about">
        <div class="container">
            <h2 class="section-title fade-in">About Me</h2>
            <div class="about-content fade-in">
                <div class="about-text">
                    <p>I'm a passionate Computer Science and Artificial Intelligence enthusiast with a strong foundation in programming, machine learning, and software development. My journey in tech has been driven by curiosity and a desire to create innovative solutions that make a difference.</p>
                    <p>With expertise in various programming languages and AI frameworks, I enjoy tackling complex problems and turning ideas into reality. I'm constantly learning and exploring new technologies to stay at the forefront of the rapidly evolving tech landscape.</p>
                    <div class="skills">
                        <span class="skill-tag">Python</span>
                        <span class="skill-tag">JavaScript</span>
                        <span class="skill-tag">TensorFlow</span>
                        <span class="skill-tag">PyTorch</span>
                        <span class="skill-tag">React</span>
                        <span class="skill-tag">Node.js</span>
                        <span class="skill-tag">Machine Learning</span>
                        <span class="skill-tag">Deep Learning</span>
                        <span class="skill-tag">Data Science</span>
                    </div>
                </div>
                <div class="timeline">
                    <div class="timeline-item">
                        <div class="timeline-date">2020 - Present</div>
                        <h3>AI Research & Development</h3>
                        <p>Working on cutting-edge AI projects and machine learning models</p>
                    </div>
                    <div class="timeline-item">
                        <div class="timeline-date">2018 - 2020</div>
                        <h3>Software Development</h3>
                        <p>Full-stack development with focus on web applications</p>
                    </div>
                    <div class="timeline-item">
                        <div class="timeline-date">2016 - 2018</div>
                        <h3>Computer Science Studies</h3>
                        <p>Began my journey in Computer Science and AI</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section id="projects" class="projects">
        <div class="container">
            <h2 class="section-title fade-in">Projects</h2>
            <div class="projects-grid fade-in">
                <div class="project-card">
                    <div class="project-image">
                        <i class="fas fa-brain"></i>
                    </div>
                    <div class="project-content">
                        <h3 class="project-title">AI Image Recognition</h3>
                        <p class="project-description">A deep learning model for real-time image recognition with 95% accuracy.</p>
                        <div class="project-tech">
                            <span class="tech-icon"><i class="fab fa-python"></i></span>
                            <span class="tech-icon"><i class="fas fa-brain"></i></span>
                            <span class="tech-icon"><i class="fas fa-database"></i></span>
                        </div>
                        <a href="#" class="btn">View Project</a>
                    </div>
                </div>
                <div class="project-card">
                    <div class="project-image">
                        <i class="fas fa-robot"></i>
                    </div>
                    <div class="project-content">
                        <h3 class="project-title">Chatbot Assistant</h3>
                        <p class="project-description">An intelligent chatbot powered by NLP for customer support automation.</p>
                        <div class="project-tech">
                            <span class="tech-icon"><i class="fab fa-js"></i></span>
                            <span class="tech-icon"><i class="fas fa-comments"></i></span>
                            <span class="tech-icon"><i class="fab fa-node-js"></i></span>
                        </div>
                        <a href="#" class="btn">View Project</a>
                    </div>
                </div>
                <div class="project-card">
                    <div class="project-image">
                        <i class="fas fa-chart-line"></i>
                    </div>
                    <div class="project-content">
                        <h3 class="project-title">Data Analytics Dashboard</h3>
                        <p class="project-description">Interactive dashboard for visualizing complex datasets and generating insights.</p>
                        <div class="project-tech">
                            <span class="tech-icon"><i class="fab fa-react"></i></span>
                            <span class="tech-icon"><i class="fas fa-chart-bar"></i></span>
                            <span class="tech-icon"><i class="fas fa-database"></i></span>
                        </div>
                        <a href="#" class="btn">View Project</a>
                    </div>
                </div>
                <div class="project-card">
                    <div class="project-image">
                        <i class="fas fa-shield-alt"></i>
                    </div>
                    <div class="project-content">
                        <h3 class="project-title">Cybersecurity AI</h3>
                        <p class="project-description">Machine learning system for detecting and preventing cyber threats in real-time.</p>
                        <div class="project-tech">
                            <span class="tech-icon"><i class="fab fa-python"></i></span>
                            <span class="tech-icon"><i class="fas fa-shield-alt"></i></span>
                            <span class="tech-icon"><i class="fas fa-network-wired"></i></span>
                        </div>
                        <a href="#" class="btn">View Project</a>
                    </div>
                </div>
                <div class="project-card">
                    <div class="project-image">
                        <i class="fas fa-mobile-alt"></i>
                    </div>
                    <div class="project-content">
                        <h3 class="project-title">Mobile AI App</h3>
                        <p class="project-description">Cross-platform mobile app with AI-powered features for personal productivity.</p>
                        <div class="project-tech">
                            <span class="tech-icon"><i class="fab fa-react"></i></span>
                            <span class="tech-icon"><i class="fas fa-mobile-alt"></i></span>
                            <span class="tech-icon"><i class="fas fa-brain"></i></span>
                        </div>
                        <a href="#" class="btn">View Project</a>
                    </div>
                </div>
                <div class="project-card">
                    <div class="project-image">
                        <i class="fas fa-cloud"></i>
                    </div>
                    <div class="project-content">
                        <h3 class="project-title">Cloud Infrastructure</h3>
                        <p class="project-description">Scalable cloud infrastructure for deploying AI models and applications.</p>
                        <div class="project-tech">
                            <span class="tech-icon"><i class="fab fa-aws"></i></span>
                            <span class="tech-icon"><i class="fas fa-docker"></i></span>
                            <span class="tech-icon"><i class="fas fa-server"></i></span>
                        </div>
                        <a href="#" class="btn">View Project</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Achievements Section -->
    <section id="achievements" class="achievements">
        <div class="container">
            <h2 class="section-title fade-in">Achievements</h2>
            <div class="achievements-grid fade-in">
                <div class="achievement-card">
                    <div class="achievement-icon">
                        <i class="fas fa-trophy"></i>
                    </div>
                    <h3>AI Innovation Award</h3>
                    <p>Recognized for groundbreaking work in machine learning applications</p>
                </div>
                <div class="achievement-card">
                    <div class="achievement-icon">
                        <i class="fas fa-code"></i>
                    </div>
                    <h3>Hackathon Winner</h3>
                    <p>First place in national AI hackathon with innovative solution</p>
                </div>
                <div class="achievement-card">
                    <div class="achievement-icon">
                        <i class="fas fa-certificate"></i>
                    </div>
                    <h3>Certified AI Professional</h3>
                    <p>Advanced certification in Artificial Intelligence and Machine Learning</p>
                </div>
                <div class="achievement-card">
                    <div class="achievement-icon">
                        <i class="fas fa-users"></i>
                    </div>
                    <h3>Tech Community Leader</h3>
                    <p>Leading AI community with 500+ members and regular workshops</p>
                </div>
                <div class="achievement-card">
                    <div class="achievement-icon">
                        <i class="fas fa-graduation-cap"></i>
                    </div>
                    <h3>Academic Excellence</h3>
                    <p>Top performer in Computer Science with specialization in AI</p>
                </div>
                <div class="achievement-card">
                    <div class="achievement-icon">
                        <i class="fas fa-lightbulb"></i>
                    </div>
                    <h3>Innovation Grant</h3>
                    <p>Received funding for AI research project on sustainable technology</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Studies Section -->
    <section id="studies" class="studies">
        <div class="container">
            <h2 class="section-title fade-in">Education</h2>
            <div class="studies-timeline fade-in">
                <div class="study-item">
                    <div class="study-content">
                        <h3>Master's in Computer Science</h3>
                        <p>Specialization in Artificial Intelligence and Machine Learning</p>
                        <p>University of Technology</p>
                        <p>2018 - 2020</p>
                    </div>
                </div>
                <div class="study-item">
                    <div class="study-content">
                        <h3>Bachelor's in Computer Science</h3>
                        <p>Focus on Software Engineering and Data Structures</p>
                        <p>Tech Institute</p>
                        <p>2014 - 2018</p>
                    </div>
                </div>
                <div class="study-item">
                    <div class="study-content">
                        <h3>AI & Deep Learning Specialization</h3>
                        <p>Advanced course on Neural Networks and Deep Learning</p>
                        <p>Online Learning Platform</p>
                        <p>2020</p>
                    </div>
                </div>
                <div class="study-item">
                    <div class="study-content">
                        <h3>Certification in Cloud Computing</h3>
                        <p>AWS Certified Solutions Architect</p>
                        <p>Amazon Web Services</p>
                        <p>2021</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Certificates Section -->
    <section id="certificates" class="certificates">
        <div class="container">
            <h2 class="section-title fade-in">Certificates</h2>
            <div class="certificates-grid fade-in">
                <div class="certificate-card" onclick="openLightbox('https://via.placeholder.com/800x600')">
                    <div class="certificate-image">
                        <i class="fas fa-certificate"></i>
                    </div>
                    <div class="certificate-content">
                        <h3>Coursera AI Certificate</h3>
                        <p>Machine Learning by Andrew Ng</p>
                    </div>
                </div>
                <div class="certificate-card" onclick="openLightbox('https://via.placeholder.com/800x600')">
                    <div class="certificate-image">
                        <i class="fas fa-certificate"></i>
                    </div>
                    <div class="certificate-content">
                        <h3>Google Prompt Engineering</h3>
                        <p>Advanced Prompt Engineering for AI Systems</p>
                    </div>
                </div>
                <div class="certificate-card" onclick="openLightbox('https://via.placeholder.com/800x600')">
                    <div class="certificate-image">
                        <i class="fas fa-certificate"></i>
                    </div>
                    <div class="certificate-content">
                        <h3>Deep Learning Specialization</h3>
                        <p>Neural Networks and Deep Learning</p>
                    </div>
                </div>
                <div class="certificate-card" onclick="openLightbox('https://via.placeholder.com/800x600')">
                    <div class="certificate-image">
                        <i class="fas fa-certificate"></i>
                    </div>
                    <div class="certificate-content">
                        <h3>AWS Machine Learning</h3>
                        <p>Machine Learning on AWS Platform</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Gallery Section -->
    <section id="gallery" class="gallery">
        <div class="container">
            <h2 class="section-title fade-in">Gallery</h2>
            <div class="gallery-grid fade-in">
                <div class="gallery-item" onclick="openLightbox('https://via.placeholder.com/800x600')">
                    <img src="https://via.placeholder.com/400x400" alt="Gallery Image">
                    <div class="gallery-overlay">
                        <i class="fas fa-search-plus fa-2x"></i>
                    </div>
                </div>
                <div class="gallery-item" onclick="openLightbox('https://via.placeholder.com/800x600')">
                    <img src="https://via.placeholder.com/400x400" alt="Gallery Image">
                    <div class="gallery-overlay">
                        <i class="fas fa-search-plus fa-2x"></i>
                    </div>
                </div>
                <div class="gallery-item" onclick="openLightbox('https://via.placeholder.com/800x600')">
                    <img src="https://via.placeholder.com/400x400" alt="Gallery Image">
                    <div class="gallery-overlay">
                        <i class="fas fa-search-plus fa-2x"></i>
                    </div>
                </div>
                <div class="gallery-item" onclick="openLightbox('https://via.placeholder.com/800x600')">
                    <img src="https://via.placeholder.com/400x400" alt="Gallery Image">
                    <div class="gallery-overlay">
                        <i class="fas fa-search-plus fa-2x"></i>
                    </div>
                </div>
                <div class="gallery-item" onclick="openLightbox('https://via.placeholder.com/800x600')">
                    <img src="https://via.placeholder.com/400x400" alt="Gallery Image">
                    <div class="gallery-overlay">
                        <i class="fas fa-search-plus fa-2x"></i>
                    </div>
                </div>
                <div class="gallery-item" onclick="openLightbox('https://via.placeholder.com/800x600')">
                    <img src="https://via.placeholder.com/400x400" alt="Gallery Image">
                    <div class="gallery-overlay">
                        <i class="fas fa-search-plus fa-2x"></i>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="contact">
        <div class="container">
            <h2 class="section-title fade-in">Contact Me</h2>
            <div class="contact-content fade-in">
                <form class="contact-form" id="contact-form">
                    <div class="form-group">
                        <label for="name">Name</label>
                        <input type="text" id="name" name="name" required>
                    </div>
                    <div class="form-group">
                        <label for="email">Email</label>
                        <input type="email" id="email" name="email" required>
                    </div>
                    <div class="form-group">
                        <label for="message">Message</label>
                        <textarea id="message" name="message" rows="5" required></textarea>
                    </div>
                    <button type="submit" class="btn">Send Message</button>
                </form>
                <div class="contact-info">
                    <div class="contact-item">
                        <div class="contact-icon">
                            <i class="fas fa-envelope"></i>
                        </div>
                        <div>
                            <h3>Email</h3>
                            <p>contact@arizwan.com</p>
                        </div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon">
                            <i class="fas fa-map-marker-alt"></i>
                        </div>
                        <div>
                            <h3>Location</h3>
                            <p>Tech City, Innovation District</p>
                        </div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon">
                            <i class="fas fa-phone"></i>
                        </div>
                        <div>
                            <h3>Phone</h3>
                            <p>+1 (123) 456-7890</p>
                        </div>
                    </div>
                    <div class="social-links">
                        <a href="#" class="social-link">
                            <i class="fab fa-github"></i>
                        </a>
                        <a href="#" class="social-link">
                            <i class="fab fa-linkedin"></i>
                        </a>
                        <a href="#" class="social-link">
                            <i class="fab fa-twitter"></i>
                        </a>
                        <a href="#" class="social-link">
                            <i class="fab fa-instagram"></i>
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-nav">
                <a href="#home">Home</a>
                <a href="#about">About</a>
                <a href="#projects">Projects</a>
                <a href="#achievements">Achievements</a>
                <a href="#studies">Studies</a>
                <a href="#certificates">Certificates</a>
                <a href="#gallery">Gallery</a>
                <a href="#contact">Contact</a>
            </div>
            <div class="copyright">
                <p>&copy; 2025 Arizwan. All Rights Reserved.</p>
            </div>
        </div>
    </footer>

    <!-- Lightbox -->
    <div class="lightbox" id="lightbox" onclick="closeLightbox()">
        <div class="lightbox-content">
            <span class="lightbox-close">&times;</span>
            <img id="lightbox-img" src="" alt="Lightbox Image">
        </div>
    </div>

    <script>
        // Theme Toggle
        const themeToggle = document.getElementById('theme-toggle');
        const body = document.body;
        const icon = themeToggle.querySelector('i');
        
        themeToggle.addEventListener('click', () => {
            if (body.getAttribute('data-theme') === 'light') {
                body.removeAttribute('data-theme');
                icon.classList.remove('fa-sun');
                icon.classList.add('fa-moon');
                localStorage.setItem('theme', 'dark');
            } else {
                body.setAttribute('data-theme', 'light');
                icon.classList.remove('fa-moon');
                icon.classList.add('fa-sun');
                localStorage.setItem('theme', 'light');
            }
        });
        
        // Check for saved theme preference
        if (localStorage.getItem('theme') === 'light') {
            body.setAttribute('data-theme', 'light');
            icon.classList.remove('fa-moon');
            icon.classList.add('fa-sun');
        }
        
        // Mobile Menu Toggle
        const mobileMenu = document.getElementById('mobile-menu');
        const navLinks = document.querySelector('.nav-links');
        
        mobileMenu.addEventListener('click', () => {
            mobileMenu.classList.toggle('active');
            navLinks.classList.toggle('active');
        });
        
        // Close mobile menu when link is clicked
        document.querySelectorAll('.nav-link').forEach(link => {
            link.addEventListener('click', () => {
                mobileMenu.classList.remove('active');
                navLinks.classList.remove('active');
            });
        });
        
        // Active Navigation Link
        const sections = document.querySelectorAll('section');
        const navItems = document.querySelectorAll('.nav-link');
        
        window.addEventListener('scroll', () => {
            let current = '';
            
            sections.forEach(section => {
                const sectionTop = section.offsetTop;
                const sectionHeight = section.clientHeight;
                if (scrollY >= (sectionTop - 200)) {
                    current = section.getAttribute('id');
                }
            });
            
            navItems.forEach(item => {
                item.classList.remove('active');
                if (item.getAttribute('href').slice(1) === current) {
                    item.classList.add('active');
                }
            });
        });
        
        // Fade In Animation on Scroll
        const fadeElements = document.querySelectorAll('.fade-in');
        
        const fadeInOnScroll = () => {
            fadeElements.forEach(element => {
                const elementTop = element.getBoundingClientRect().top;
                const elementVisible = 150;
                
                if (elementTop < window.innerHeight - elementVisible) {
                    element.classList.add('visible');
                }
            });
        };
        
        window.addEventListener('scroll', fadeInOnScroll);
        fadeInOnScroll(); // Check on load
        
        // Hero Canvas Animation
        const canvas = document.getElementById('hero-canvas');
        const ctx = canvas.getContext('2d');
        
        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;
        
        window.addEventListener('resize', () => {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
        });
        
        // Binary Rain Effect
        const binary = '01';
        const binaryArray = binary.split('');
        const fontSize = 16;
        const columns = canvas.width / fontSize;
        const drops = [];
        
        for (let i = 0; i < columns; i++) {
            drops[i] = 1;
        }
        
        function drawBinaryRain() {
            ctx.fillStyle = 'rgba(10, 14, 39, 0.05)';
            ctx.fillRect(0, 0, canvas.width, canvas.height);
            
            ctx.fillStyle = '#00d9ff';
            ctx.font = fontSize + 'px monospace';
            
            for (let i = 0; i < drops.length; i++) {
                const text = binaryArray[Math.floor(Math.random() * binaryArray.length)];
                ctx.fillText(text, i * fontSize, drops[i] * fontSize);
                
                if (drops[i] * fontSize > canvas.height && Math.random() > 0.975) {
                    drops[i] = 0;
                }
                
                drops[i]++;
            }
        }
        
        setInterval(drawBinaryRain, 35);
        
        // Circuit Animation
        function createCircuitAnimation() {
            const circuitContainer = document.createElement('div');
            circuitContainer.className = 'circuit';
            document.querySelector('.hero').appendChild(circuitContainer);
            
            // Create circuit lines
            for (let i = 0; i < 20; i++) {
                const line = document.createElement('div');
                line.className = 'circuit-line';
                
                const isHorizontal = Math.random() > 0.5;
                const length = Math.random() * 200 + 100;
                const posX = Math.random() * window.innerWidth;
                const posY = Math.random() * window.innerHeight;
                
                if (isHorizontal) {
                    line.style.width = length + 'px';
                    line.style.height = '2px';
                    line.style.left = posX + 'px';
                    line.style.top = posY + 'px';
                } else {
                    line.style.width = '2px';
                    line.style.height = length + 'px';
                    line.style.left = posX + 'px';
                    line.style.top = posY + 'px';
                }
                
                circuitContainer.appendChild(line);
            }
            
            // Create circuit nodes
            for (let i = 0; i < 30; i++) {
                const node = document.createElement('div');
                node.className = 'circuit-node';
                
                node.style.left = Math.random() * window.innerWidth + 'px';
                node.style.top = Math.random() * window.innerHeight + 'px';
                
                circuitContainer.appendChild(node);
            }
        }
        
        createCircuitAnimation();
        
        // Lightbox
        function openLightbox(src) {
            const lightbox = document.getElementById('lightbox');
            const lightboxImg = document.getElementById('lightbox-img');
            
            lightboxImg.src = src;
            lightbox.style.display = 'flex';
            document.body.style.overflow = 'hidden';
        }
        
        function closeLightbox() {
            const lightbox = document.getElementById('lightbox');
            lightbox.style.display = 'none';
            document.body.style.overflow = 'auto';
        }
        
        // Contact Form
        const contactForm = document.getElementById('contact-form');
        
        contactForm.addEventListener('submit', (e) => {
            e.preventDefault();
            
            // Get form values
            const name = document.getElementById('name').value;
            const email = document.getElementById('email').value;
            const message = document.getElementById('message').value;
            
            // Here you would normally send the form data to a server
            // For this example, we'll just show a success message
            alert(`Thank you, ${name}! Your message has been sent successfully.`);
            
            // Reset form
            contactForm.reset();
        });
        
        // Smooth scrolling for all links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });
    </script>
</body>
</html>
