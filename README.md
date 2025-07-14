<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ankit | Web Developer</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&family=Space+Grotesk:wght@400;500;700&display=swap');

        :root {
            --primary: #00f0ff;
            --secondary: #9600ff;
            --accent: #ff00aa;
            --dark: #0a0a14;
            --light: #f0f5ff;
            --neon-glow: 0 0 15px rgba(0, 240, 255, 0.7),
                         0 0 30px rgba(0, 240, 255, 0.4);
            --gradient: linear-gradient(135deg, var(--primary), var(--accent));
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background-color: var(--dark);
            color: var(--light);
            font-family: 'Poppins', sans-serif;
            overflow-x: hidden;
            scroll-behavior: smooth;
            background-image: url(https://giffiles.alphacoders.com/521/5218.gif);
            background-repeat: no-repeat;
            background-size: cover;
            background-attachment: fixed;
        }

        /* ================ */
        /* GLITCH HEADER */
        /* ================ */
        header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            padding: 1.5rem 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            z-index: 1000;
            background: rgba(10, 10, 20, 0.9);
            backdrop-filter: blur(15px);
            -webkit-backdrop-filter: blur(15px);
            border-bottom: 1px solid rgba(0, 240, 255, 0.1);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
            transition: all 0.4s ease;
        }

        header.scrolled {
            padding: 1rem 5%;
            background: rgba(10, 10, 20, 0.98);
        }
         
        .logo {
            font-family: 'Space Grotesk', sans-serif;
            font-size: 2rem;
            font-weight: 700;
            background: var(--gradient);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            text-decoration: none;
            position: relative;
            letter-spacing: 2px;
            display: flex;
            flex-direction: column;
        }
    

        .logo::before {
            content: "</>";
            margin-right: 8px;
            font-size: 1.8rem;
            animation: glitch 2s infinite alternate;
        }

        @keyframes glitch {
            0%, 100% { opacity: 1; transform: translate(0); }
            25% { opacity: 0.8; transform: translate(-2px, 2px); }
            50% { opacity: 0.9; transform: translate(2px, -2px); }
            75% { opacity: 0.8; transform: translate(-2px, -2px); }
        }

        /* ================ */
        /* CYBER NAV */
        /* ================ */
        .nav-links {
            display: flex;
            list-style: none;
        }

        .nav-item {
            position: relative;
        }

        .nav-link {
            color: var(--light);
            text-decoration: none;
            font-weight: 500;
            font-size: 1.1rem;
            padding: 0.5rem 1rem;
            transition: all 0.4s ease;
            position: relative;
        }

        .nav-link::before {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--primary);
            transition: width 0.4s ease;
            box-shadow: var(--neon-glow);
        }

        .nav-link:hover::before {
            width: 100%;
        }

        .nav-link i {
            margin-right: 8px;
            font-size: 0.9rem;
            color: var(--primary);
        }

        /* ================ */
        /* MOBILE NAV */
        /* ================ */
        .hamburger {
            display: none;
            cursor: pointer;
            background: transparent;
            border: none;
            z-index: 1001;
        }

        .hamburger span {
            display: block;
            width: 30px;
            height: 3px;
            background: var(--primary);
            margin: 6px 0;
            transition: all 0.3s ease;
            border-radius: 3px;
            box-shadow: var(--neon-glow);
        }

        .hamburger.active span:nth-child(1) {
            transform: rotate(45deg) translate(5px, 5px);
        }

        .hamburger.active span:nth-child(2) {
            opacity: 0;
        }

        .hamburger.active span:nth-child(3) {
            transform: rotate(-45deg) translate(7px, -6px);
        }

        /* ================ */
        /* HERO SECTION */
        /* ================ */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            padding: 0 5%;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, 
                rgba(0, 240, 255, 0.05) 0%, 
                transparent 70%);
            z-index: -1;
            animation: pulse 15s infinite alternate;
        }

        @keyframes pulse {
            0% { transform: scale(0.8); opacity: 0.5; }
            100% { transform: scale(1.2); opacity: 1; }
        }

        .hero-content {
            max-width: 600px;
        }

        .hero-title {
            font-size: 3.5rem;
            margin-bottom: 1.5rem;
            line-height: 1.2;
            background: var(--gradient);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            position: relative;
        }

        .hero-title::after {
            content: '_';
            animation: blink 1s infinite step-end;
            color: var(--primary);
        }

        @keyframes blink {
            0%, 100% { opacity: 1; }
            50% { opacity: 0; }
        }

        .hero-subtitle {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            color: var(--primary);
            font-weight: 500;
        }

        .hero-desc {
            font-size: 1.1rem;
            margin-bottom: 2rem;
            color: rgba(255, 255, 255, 0.8);
            line-height: 1.8;
        }

        .btn {
            display: inline-flex;
            align-items: center;
            gap: 0.8rem;
            padding: 1rem 2.5rem;
            border-radius: 50px;
            font-weight: 600;
            text-decoration: none;
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            position: relative;
            overflow: hidden;
        }

        .btn-primary {
            background: var(--gradient);
            color: var(--dark);
            box-shadow: 0 5px 25px rgba(0, 240, 255, 0.4);
        }

        .btn-primary:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 35px rgba(0, 240, 255, 0.6);
        }

        .btn-outline {
            background: transparent;
            color: var(--primary);
            border: 2px solid var(--primary);
            margin-left: 1rem;
        }

        .btn-outline:hover {
            background: rgba(0, 240, 255, 0.1);
            transform: translateY(-5px);
            box-shadow: var(--neon-glow);
        }

        /* ================ */
        /* ABOUT SECTION */
        /* ================ */
        .about {
            padding: 8rem 5%;
            background: rgba(0, 240, 255, 0.03);
            backdrop-filter: blur(10px);
            -webkit-backdrop-filter: blur(10px);
            position: relative;
            overflow: hidden;
        }

        .about::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath fill='%2300f0ff' fill-opacity='0.03' d='M49,-65.5C60.5,-56.2,64.9,-37.4,68.3,-18.9C71.7,-0.4,74.2,17.8,66.8,32.8C59.4,47.8,42.2,59.6,23.4,68.4C4.7,77.2,-15.6,83,-32.4,76.5C-49.2,70,-62.5,51.2,-70.2,30.6C-77.9,10,-80,-12.4,-72.7,-31.2C-65.3,-50,-48.6,-65.2,-30.2,-72.9C-11.8,-80.7,8.3,-81,49,-65.5Z' transform='translate(100 100)'/%3E%3C/svg%3E");
            background-size: 500px;
            animation: move 20s infinite linear;
            z-index: -1;
        }

        @keyframes move {
            0% { background-position: 0 0; }
            100% { background-position: 500px 500px; }
        }

        .section-title {
            font-size: 2.5rem;
            margin-bottom: 3rem;
            text-align: center;
            background: var(--gradient);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            position: relative;
            display: inline-block;
            left: 50%;
            transform: translateX(-50%);
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 0;
            width: 100%;
            height: 3px;
            background: var(--gradient);
            border-radius: 3px;
            box-shadow: var(--neon-glow);
        }

        .about-container {
            display: flex;
            align-items: center;
            gap: 4rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .about-image {
            flex: 1;
            position: relative;
            perspective: 1000px;
        }

        .profile-card {
            background: rgba(10, 10, 20, 0.6);
            backdrop-filter: blur(10px);
            -webkit-backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 2rem;
            box-shadow: 0 20px 50px rgba(0, 0, 0, 0.3),
                       -10px 0 30px rgba(0, 240, 255, 0.2),
                       10px 0 30px rgba(150, 0, 255, 0.2),
                       inset 0 0 20px rgba(0, 240, 255, 0.1);
            border: 1px solid rgba(0, 240, 255, 0.2);
            transform-style: preserve-3d;
            transform: rotateY(-15deg);
            transition: transform 0.5s ease;
        }

        .profile-card:hover {
            transform: rotateY(-5deg);
        }

        .profile-image {
            width: 100%;
            border-radius: 15px;
            margin-bottom: 1.5rem;
            border: 3px solid rgba(0, 240, 255, 0.3);
            box-shadow: var(--neon-glow);
        }

        .profile-links {
            display: flex;
            justify-content: center;
            gap: 1rem;
        }

        .profile-link {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            background: rgba(0, 240, 255, 0.1);
            color: var(--light);
            text-decoration: none;
            transition: all 0.3s ease;
            border: 1px solid rgba(0, 240, 255, 0.2);
        }

        .profile-link:hover {
            background: rgba(0, 240, 255, 0.2);
            transform: translateY(-5px);
            color: var(--primary);
            box-shadow: var(--neon-glow);
        }

        .about-content {
            flex: 1;
        }

        .about-content p {
            color: rgba(255, 255, 255, 0.8);
            line-height: 1.8;
            margin-bottom: 1.5rem;
            font-size: 1.1rem;
        }

        .skills {
            display: flex;
            flex-wrap: wrap;
            gap: 0.8rem;
            margin-top: 2rem;
        }

        .skill {
            background: rgba(0, 240, 255, 0.1);
            color: var(--primary);
            padding: 0.5rem 1.2rem;
            border-radius: 50px;
            font-size: 0.9rem;
            font-weight: 500;
            border: 1px solid rgba(0, 240, 255, 0.2);
            transition: all 0.3s ease;
        }

        .skill:hover {
            background: rgba(0, 240, 255, 0.2);
            transform: translateY(-3px);
            box-shadow: var(--neon-glow);
        }

        /* Glass Card Container */
        .glass-card {
          --bg-color: rgba(255, 255, 255, 0.25);
          --highlight: rgba(255, 255, 255, 0.75);
          --text: #ffffff;
          
          position: relative;
          width: 300px;
          height: 200px;
          border-radius: 20px;
          overflow: hidden;
          box-shadow: 0 6px 24px rgba(0, 0, 0, 0.2);
        }

        .glass-filter,
        .glass-overlay,
        .glass-specular {
          position: absolute;
          inset: 0;
          border-radius: inherit;
        }

        .glass-filter {
          z-index: 1;
          backdrop-filter: blur(4px);
          filter: url(#glass-distortion) saturate(120%) brightness(1.15);
        }

        .glass-distortion-overlay {
          position: absolute;
          inset: 0;
          background: radial-gradient(circle at 20% 30%, rgba(255,255,255,0.05) 0%, transparent 80%),
                      radial-gradient(circle at 80% 70%, rgba(255,255,255,0.05) 0%, transparent 80%);
          background-size: 300% 300%;
          animation: floatDistort 10s infinite ease-in-out;
          mix-blend-mode: overlay;
          z-index: 2;
          pointer-events: none;
        }

        @keyframes floatDistort {
          0% { background-position: 0% 0%; }
          50% { background-position: 100% 100%; }
          100% { background-position: 0% 0%; }
        }

        .glass-overlay {
          z-index: 2;
          background: var(--bg-color);
        }

        .glass-specular {
          z-index: 3;
          box-shadow: inset 1px 1px 1px var(--highlight);
        }

        .glass-content {
          position: relative;
          z-index: 4;
          padding: 20px;
          color: var(--text);
          text-align: center;
          display: flex;
          flex-direction: column;
          justify-content: center;
          align-items: center;
          height: 100%;
        }

        .glass-content h3 {
          margin: 0 0 10px 0;
          font-size: 24px;
          font-weight: 600;
        }

        .glass-content p {
          margin: 0;
          opacity: 0.8;
        }

        /* Dark mode styles */
        @media (prefers-color-scheme: dark) {
          .glass-card {
            --bg-color: rgba(0, 0, 0, 0.25);
            --highlight: rgba(255, 255, 255, 0.15);
          }
        }

        .footer {
            background: var(--primary);
            color: #072525;
            text-align: center;
            padding: 20px;
            font-family: 'Courier New', monospace;
            font-size: 14px;
            border-top: 1px solid #dee4e4;
            font-weight: 600;
        }
        
        .footer a {
            color: #ebeeee;
            text-decoration: none;
            margin: 0 10px;
        }
        
        .footer a:hover {
            text-decoration: underline;
        }

        /* ================ */
        /* RESPONSIVE DESIGN */
        /* ================ */
        @media (max-width: 1200px) {
            .about-container {
                flex-direction: column;
            }
            
            .profile-card {
                max-width: 400px;
                margin: 0 auto 3rem;
            }
        }

        @media (max-width: 992px) {
            .hero-title {
                font-size: 3rem;
            }
        }

        @media (max-width: 768px) {
            .hero-title {
                font-size: 2.5rem;
            }
            
            .hero-subtitle {
                font-size: 1.2rem;
            }
            
            .section-title {
                font-size: 2rem;
            }
            
            .btn-group {
                display: flex;
                flex-direction: column;
                gap: 1rem;
            }
            
            .btn-outline {
                margin-left: 0;
                margin-top: 1rem;
            }
            
            .nav-links {
                position: fixed;
                top: 0;
                right: -100%;
                width: 80%;
                max-width: 300px;
                height: 100vh;
                background: rgba(10, 10, 20, 0.95);
                backdrop-filter: blur(15px);
                -webkit-backdrop-filter: blur(15px);
                flex-direction: column;
                align-items: center;
                justify-content: center;
                transition: all 0.5s ease;
                box-shadow: -10px 0 30px rgba(0, 0, 0, 0.5);
                z-index: 1000;
            }
            
            .nav-links.active {
                right: 0;
            }
            
            .nav-item {
                margin: 1.5rem 0;
            }
            
            .hamburger {
                display: block;
            }
        }

        @media (max-width: 576px) {
            .hero-title {
                font-size: 2rem;
            }
            
            .hero-desc {
                font-size: 1rem;
            }
            
            .section-title {
                font-size: 1.8rem;
            }
            
            .profile-card {
                padding: 1.5rem;
            }
            
            .glass-card {
                width: 100%;
                max-width: 280px;
            }
        }

        .cont{
             display: inline-flex;
            align-items: center;
            gap: 0.7rem;
            padding: 0.7rem 1.5rem;
            border-radius: 50px;
            font-weight: 600;
            text-decoration: none;
            font-size: 1rem;
            transition: all 0.3s ease;
            background: var(--primary);
            position: relative;
            bottom: 10px;
        }
      
        .social-icons {
  display: flex;
  justify-content: center;
  gap:75px;
}

.icon-button {
  width: 80px;
  height: 80px;
  border-radius: 50%;
  overflow: hidden;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #fff; 
  position: relative;
  bottom: 65px;
  /* optional, you can remove */
}

.icon-button img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
   
    </style>
</head>
<body>
    <!-- Glitch Header -->
    <header>
        <a href="#" class="logo">Ankit Sharma Webdevelopment</a>
        <button class="hamburger" id="hamburger">
            <span></span>
            <span></span>
            <span></span>
        </button>
        <nav>
            <ul class="nav-links" id="navLinks">
                <li class="nav-item"><a href="index.html" class="nav-link"><i class="fas fa-home"></i> Home</a></li>
                <li class="nav-item"><a href="skill.html" class="nav-link"><i class="fas fa-code"></i> Skills</a></li>
                <li class="nav-item"><a href="project.html" class="nav-link"><i class="fas fa-project-diagram"></i> Projects</a></li>
                <li class="nav-item"><a href="https://wa.me/919671802101" class="nav-link"><i class="fas fa-envelope"></i> Contact</a></li>
            </ul>
        </nav>
    </header>

    <!-- Hero Section -->
   <center> <section class="hero" id="home">
     <div class="hero-content">
            <h1 class="hero-title">Hi, I'm Ankit</h1>
            <h2 class="hero-subtitle">Web Developer & UI Specialist</h2>
            <p class="hero-desc">
                I build immersive digital experiences with cutting-edge web technologies. 
                Passionate about creating performant, accessible, and visually stunning websites.
            </p>
            <!-- SVG Filter for Glass Distortion -->
            <svg style="display: none">
                <filter id="glass-distortion">
                    <feTurbulence type="turbulence" baseFrequency="0.008" numOctaves="2" result="noise" />
                    <feDisplacementMap in="SourceGraphic" in2="noise" scale="77" />
                </filter>
            </svg>

            <center><div class="glass-card and2">
                <div class="glass-filter"></div>
                <div class="glass-overlay"></div>
                <div class="glass-specular"></div>
                <div class="glass-content">
                    <div class="glass-section">
                        <h2 class="headline">Looking for a Developer Who Builds Stunning Websites?</h2>
                        <h1>Contact Us!</h1>
                    </div>
                </div>
            </div></center>
        </div>
    </section>
    </center>

    <!-- About Section -->
    <section class="about" id="about">
        <h2 class="section-title">About Me</h2>
        <div class="about-container">
            <div class="about-image">
                <div class="profile-card">
                    <img src="https://camo.githubusercontent.com/5046cb083418fd1922b7f5990e594c3bb06f5d87e5516cd8839ae0aa48b3aec4/68747470733a2f2f696d616765732e73717561726573706163652d63646e2e636f6d2f636f6e74656e742f76312f3537363966633430316236333162616231616464623261622f313534313538303631313632342d5445363451474b524a4738535741495553374e532f6b6531375a77644742546f6464493870446d34386b506f73776c7a6a53564d4d2d53784f703743563539425a772d7a505067646e346a557756634a45315a7657515578776b6d794578676c4e714770304976544a5a616d574c49327a76595748384b332d735f3479737a63703272795449304871544f6161556f68724938504936465879386339505774426c7141566c555335697a7064634958445a71445976707252715a32395077306f2f636f64696e672d667265616b2e676966" alt="Ankit - Web Developer" class="profile-image">
                    <center><div><button class="cont">Contact Me On !</button></div></center>
                    <div class="profile-links">
                        <a href="https://wa.me/919671802101" class="profile-link"><i class="fab fa-whatsapp"></i></a>
                        <a href="https://www.instagram.com/the-ankit_9_9_9/" class="profile-link"><i class="fab fa-instagram"></i></a>
                        <a href="" class="profile-link"><i class="fab fa-facebook"></i></a>
                        <a href="mailto:ankit2000aa@gmail.com" class="profile-link"><i class="fas fa-envelope"></i></a>
                    </div>
                </div>
            </div>
            <div class="about-content">
                <p>
                    I'm Ankit, a passionate web developer with expertise in modern JavaScript frameworks and 
                    a keen eye for design. With 3+ years of experience, I specialize in creating 
                    responsive, user-friendly websites and web applications.
                </p>
                <p>
                    My approach combines technical excellence with creative problem-solving to build 
                    applications that users love. I'm constantly learning and adapting to new technologies 
                    to deliver cutting-edge solutions.
                </p>
                <p>
                    When I'm not coding, you can find me contributing to open-source projects, 
                    exploring new design trends, or mentoring aspiring developers.
                </p>
                <p>Coders are modern-day architects of the digital world, crafting logic where others see chaos. With coffee as fuel and determination as their compass, they turn lines of code into tools, apps, and systems that shape our lives. Every bug is a puzzle, every solution a small victory. They speak in languages most don't understand, yet their work speaks volumes — powering everything from the phones in our hands to the systems that run entire cities. In silence, they build the future.</p>
                <p>In the world of zeros and ones, coders are the silent architects of tomorrow. They breathe life into abstract ideas, shaping them into something tangible with just a few lines of code. Every bug they face is a puzzle, a riddle that demands patience and skill to solve. They are the ones who see the beauty in logic, the poetry in algorithms. With each keystroke, they write not just programs but futures, creating worlds that are invisible yet essential, from the apps in our hands to the systems that power entire cities. They code not because it's easy, but because it's how they build something greater than themselves.</p>
            </div>
        </div>
    </section>
   
    <div class="social-icons">
  <a href="https://www.instagram.com/the_ankit_9_9_9/" class="icon-button" target="_blank">
    <img src="https://upload.wikimedia.org/wikipedia/commons/a/a5/Instagram_icon.png" alt="Instagram">
  </a>
  <a href="https://wa.me/919671802101" class="icon-button" target="_blank">
    <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQ7Cw9hB7EwXa8BR-V308PCFFG9MtVYEZ3bjA&s" alt="WhatsApp">
  </a>
  <a href="mailto:ankit2000aa@gmail.com" class="icon-button">
    <img src="https://images.icon-icons.com/2642/PNG/512/google_mail_gmail_logo_icon_159346.png" alt="Email">
  </a>
</div>

    <footer class="footer">
        © 2024 Ankit | 
        Thank's for visiting my web page.
        <div>This page has all the web page code.</div>
        <div>Don't copy it without permission.</div>
    </footer>

    <script>
        // Navbar scroll effect
        window.addEventListener('scroll', () => {
            const header = document.querySelector('header');
            if(window.scrollY > 50) {
                header.classList.add('scrolled');
            } else {
                header.classList.remove('scrolled');
            }
        });

        // Smooth scrolling for anchor links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if(target) {
                    target.scrollIntoView({
                        behavior: 'smooth'
                    });
                }
            });
        });

        // Mobile menu toggle
        const hamburger = document.getElementById('hamburger');
        const navLinks = document.getElementById('navLinks');
        
        hamburger.addEventListener('click', () => {
            navLinks.classList.toggle('active');
            hamburger.classList.toggle('active');
        });

        // Close mobile menu when clicking a link
        document.querySelectorAll('.nav-link').forEach(link => {
            link.addEventListener('click', () => {
                navLinks.classList.remove('active');
                hamburger.classList.remove('active');
            });
        });

        // Animate elements when they come into view
        const animateOnScroll = () => {
            const elements = document.querySelectorAll('.profile-card, .about-content');
            
            elements.forEach(element => {
                const elementPosition = element.getBoundingClientRect().top;
                const screenPosition = window.innerHeight / 1.3;
                
                if(elementPosition < screenPosition) {
                    element.style.opacity = '1';
                    element.style.transform = 'translateY(0)';
                }
            });
        };

        // Set initial state for animation
        document.querySelectorAll('.profile-card, .about-content').forEach(el => {
            el.style.opacity = '0';
            el.style.transform = 'translateY(30px)';
            el.style.transition = 'all 0.6s ease';
        });

        window.addEventListener('scroll', animateOnScroll);
        window.addEventListener('load', animateOnScroll);
        
        // Add mouse movement interactivity to glass elements
        document.addEventListener('DOMContentLoaded', function() {
            // Get all glass elements
            const glassElements = document.querySelectorAll('.glass-card');
            
            // Add mousemove effect for each glass element
            glassElements.forEach(element => {
                element.addEventListener('mousemove', handleMouseMove);
                element.addEventListener('mouseleave', handleMouseLeave);
            });
            
            // Handle mouse movement over glass elements
            function handleMouseMove(e) {
                const rect = this.getBoundingClientRect();
                const x = e.clientX - rect.left;
                const y = e.clientY - rect.top;
                
                // Update filter turbulence based on mouse position
                const filter = this.querySelector('filter feDisplacementMap');
                if (filter) {
                    const scaleX = (x / rect.width) * 100;
                    const scaleY = (y / rect.height) * 100;
                    filter.setAttribute('scale', Math.min(scaleX, scaleY));
                }
                
                // Add highlight effect
                const specular = this.querySelector('.glass-specular');
                if (specular) {
                    specular.style.background = `radial-gradient(
                        circle at ${x}px ${y}px,
                        rgba(255,255,255,0.15) 0%,
                        rgba(255,255,255,0.05) 30%,
                        rgba(255,255,255,0) 60%
                    )`;
                }
            }
            
            // Reset effects when mouse leaves
            function handleMouseLeave() {
                const filter = this.querySelector('filter feDisplacementMap');
                if (filter) {
                    filter.setAttribute('scale', '77');
                }
                
                const specular = this.querySelector('.glass-specular');
                if (specular) {
                    specular.style.background = 'none';
                }
            }
        });
    </script>
</body>
</html>
