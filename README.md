<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AMAL KVS - Neural Flutter Developer</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Exo+2:wght@300;400;600&display=swap');
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            background: linear-gradient(135deg, #0c0c0c 0%, #1a1a2e 50%, #16213e 100%);
            background-attachment: fixed;
            color: #00f5ff;
            font-family: 'Exo 2', sans-serif;
            overflow-x: hidden;
            min-height: 100vh;
            position: relative;
        }
        
        /* Animated Background */
        .matrix-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            opacity: 0.1;
        }
        
        .matrix-bg::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-image: 
                linear-gradient(45deg, transparent 30%, rgba(0, 245, 255, 0.03) 50%, transparent 70%),
                linear-gradient(-45deg, transparent 30%, rgba(255, 0, 255, 0.03) 50%, transparent 70%);
            background-size: 50px 50px;
            animation: matrixFlow 20s linear infinite;
        }
        
        @keyframes matrixFlow {
            0% { transform: translateX(-50px) translateY(-50px); }
            100% { transform: translateX(calc(100vw + 50px)) translateY(calc(100vh + 50px)); }
        }
        
        /* Header */
        .header {
            text-align: center;
            padding: 2rem 1rem;
            position: relative;
        }
        
        .typing-animation {
            font-size: clamp(1.5rem, 5vw, 3rem);
            font-family: 'Orbitron', monospace;
            margin-bottom: 1rem;
            min-height: 50px;
        }
        
        .name-container {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 1rem;
            flex-wrap: wrap;
            margin: 1rem 0;
        }
        
        .name {
            font-family: 'Orbitron', monospace;
            font-size: clamp(2.5rem, 8vw, 5rem);
            font-weight: 900;
            background: linear-gradient(45deg, #00f5ff, #ff00ff, #00ff88, #00f5ff);
            background-size: 300% 300%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: neonGlow 3s ease-in-out infinite alternate, gradientShift 4s ease infinite;
            text-shadow: 0 0 20px rgba(0, 245, 255, 0.5);
        }
        
        @keyframes neonGlow {
            from { filter: drop-shadow(0 0 10px #00f5ff); }
            to { filter: drop-shadow(0 0 30px #00f5ff) drop-shadow(0 0 40px #ff00ff); }
        }
        
        @keyframes gradientShift {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }
        
        .snake-animation {
            width: 80px;
            height: 80px;
            animation: snakeRotate 4s linear infinite;
        }
        
        @keyframes snakeRotate {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }
        
        /* Profile Stats */
        .profile-stats {
            display: flex;
            justify-content: center;
            gap: 1rem;
            flex-wrap: wrap;
            margin: 2rem 0;
        }
        
        .stat-badge {
            background: linear-gradient(145deg, rgba(14, 117, 182, 0.2), rgba(0, 245, 255, 0.1));
            backdrop-filter: blur(10px);
            border: 1px solid rgba(0, 245, 255, 0.3);
            border-radius: 25px;
            padding: 0.5rem 1.5rem;
            font-weight: 600;
            font-size: 0.9rem;
            box-shadow: 0 8px 32px rgba(0, 245, 255, 0.1);
            transition: all 0.3s ease;
        }
        
        .stat-badge:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(0, 245, 255, 0.3);
            border-color: #ff00ff;
        }
        
        /* Social Links */
        .social-links {
            display: flex;
            justify-content: center;
            gap: 1rem;
            flex-wrap: wrap;
            margin: 2rem 0;
        }
        
        .social-badge {
            padding: 0.7rem 1.2rem;
            background: linear-gradient(45deg, rgba(255, 0, 255, 0.2), rgba(0, 245, 255, 0.2));
            border: 1px solid transparent;
            border-radius: 50px;
            color: #fff;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }
        
        .social-badge::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
            transition: left 0.5s;
        }
        
        .social-badge:hover::before {
            left: 100%;
        }
        
        .social-badge:hover {
            transform: translateY(-3px) scale(1.05);
            box-shadow: 0 10px 30px rgba(255, 0, 255, 0.4);
            border-color: #00f5ff;
        }
        
        /* Sections */
        .section {
            max-width: 1200px;
            margin: 3rem auto;
            padding: 0 2rem;
        }
        
        .section-title {
            font-family: 'Orbitron', monospace;
            font-size: 2rem;
            font-weight: 700;
            margin-bottom: 2rem;
            text-align: center;
            background: linear-gradient(45deg, #00f5ff, #ff00ff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
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
            background: linear-gradient(90deg, transparent, #00f5ff, #ff00ff, transparent);
            border-radius: 2px;
        }
        
        /* Tech Stack */
        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
            gap: 2rem;
            margin: 2rem 0;
        }
        
        .tech-item {
            text-align: center;
            padding: 1.5rem;
            background: rgba(14, 117, 182, 0.1);
            backdrop-filter: blur(20px);
            border: 1px solid rgba(0, 245, 255, 0.2);
            border-radius: 20px;
            transition: all 0.4s ease;
            position: relative;
            overflow: hidden;
        }
        
        .tech-item::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(45deg, transparent, rgba(0, 245, 255, 0.1), transparent);
            opacity: 0;
            transition: opacity 0.3s ease;
        }
        
        .tech-item:hover::before {
            opacity: 1;
        }
        
        .tech-item:hover {
            transform: translateY(-10px) scale(1.05);
            border-color: #ff00ff;
            box-shadow: 0 20px 50px rgba(0, 245, 255, 0.3);
        }
        
        .tech-icon {
            width: 60px;
            height: 60px;
            margin-bottom: 1rem;
            filter: drop-shadow(0 0 10px rgba(0, 245, 255, 0.5));
            transition: all 0.3s ease;
        }
        
        .tech-item:hover .tech-icon {
            filter: drop-shadow(0 0 20px #ff00ff);
            transform: scale(1.1);
        }
        
        /* Mermaid Diagram */
        .mermaid {
            background: rgba(26, 26, 46, 0.5);
            backdrop-filter: blur(20px);
            border-radius: 20px;
            padding: 2rem;
            border: 1px solid rgba(0, 245, 255, 0.2);
            margin: 2rem 0;
        }
        
        /* Stats Cards */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin: 2rem 0;
        }
        
        .stat-card {
            background: linear-gradient(145deg, rgba(14, 117, 182, 0.2), rgba(26, 26, 46, 0.8));
            backdrop-filter: blur(20px);
            border: 1px solid rgba(0, 245, 255, 0.3);
            border-radius: 20px;
            padding: 2rem;
            text-align: center;
            transition: all 0.3s ease;
            height: 200px;
            display: flex;
            flex-direction: column;
            justify-content: center;
        }
        
        .stat-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 25px 60px rgba(0, 245, 255, 0.4);
            border-color: #ff00ff;
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .profile-stats, .social-links {
                flex-direction: column;
                align-items: center;
            }
            
            .name-container {
                flex-direction: column;
                gap: 0.5rem;
            }
        }
        
        /* Scroll animations */
        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.8s ease;
        }
        
        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
</head>
<body>
    <!-- Matrix Background -->
    <div class="matrix-bg"></div>
    
    <!-- Header -->
    <div class="header fade-in">
        <div class="typing-animation" id="typing"></div>
        <div class="name-container">
            <img src="https://raw.githubusercontent.com/amal-kvs/amal-kvs/output/github-contribution-grid-snake.svg" 
                 alt="snake animation" class="snake-animation">
            <h1 class="name">AMAL KVS</h1>
        </div>
        <h3>🚀 <b>Flutter Neural Core</b> | <b>Cyber UI/UX Matrix</b> | <b>Quantum Developer</b></h3>
        
        <!-- Profile Stats -->
        <div class="profile-stats">
            <div class="stat-badge">
                <img src="https://komarev.com/ghpvc/?username=amal-kvs&label=Profile%20views&color=0e75b6&style=flat" 
                     alt="Profile views" style="height: 20px; vertical-align: middle;">
            </div>
            <div class="stat-badge">🧠 Neural Load: 99.9%</div>
            <div class="stat-badge">⚡ Uptime: 24/7</div>
        </div>
    </div>
    
    <!-- Social Links -->
    <div class="social-links fade-in">
        <a href="https://twitter.com/amal_kvs" class="social-badge" target="_blank">🐦 Twitter</a>
        <a href="https://linkedin.com/in/amal_kvs" class="social-badge" target="_blank">💼 LinkedIn</a>
        <a href="https://www.youtube.com/c/amal_kvs" class="social-badge" target="_blank">📺 YouTube</a>
        <a href="https://discord.gg/amal_kvs" class="social-badge" target="_blank">💎 Discord</a>
    </div>
    
    <!-- Neural Interface Section -->
    <div class="section fade-in">
        <h2 class="section-title">🌌 NEURAL INTERFACE</h2>
        <div class="mermaid">
            ```mermaid
            graph TB
                A[🧠 Neural Core] --> B[Flutter Matrix]
                B --> C[UI Quantum Render]
                B --> D[Dart NanoCompiler]
                C --> E[Android Cyberlink]
                C --> F[iOS HoloBridge]
                D --> G[State Flux Manager]
                G --> H[Animation Warp Drive]
                style A fill:#0e75b6,stroke:#00f5ff,stroke-width:3px
                style B fill:#1a1a2e,stroke:#ff00ff,stroke-width:3px
            ```
        </div>
    </div>
    
    <!-- Tech Stack -->
    <div class="section fade-in">
        <h2 class="section-title">🚀 QUANTUM PROTOCOLS</h2>
        <div class="tech-grid">
            <div class="tech-item">
                <img src="https://www.vectorlogo.zone/logos/flutterio/flutterio-icon.svg" class="tech-icon" alt="Flutter">
                <div>Flutter Matrix</div>
            </div>
            <div class="tech-item">
                <img src="https://www.vectorlogo.zone/logos/dartlang/dartlang-icon.svg" class="tech-icon" alt="Dart">
                <div>Dart NanoCompiler</div>
            </div>
            <div class="tech-item">
                <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/swift/swift-original.svg" class="tech-icon" alt="Swift">
                <div>Swift HoloBridge</div>
            </div>
            <div class="tech-item">
                <img src="https://www.vectorlogo.zone/logos/firebase/firebase-icon.svg" class="tech-icon" alt="Firebase">
                <div>Firebase NeuralNet</div>
            </div>
            <div class="tech-item">
                <img src="https://www.vectorlogo.zone/logos/figma/figma-icon.svg" class="tech-icon" alt="Figma">
                <div>Figma QuantumDesign</div>
            </div>
            <div class="tech-item">
                <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/git/git-original.svg" class="tech-icon" alt="Git">
                <div>Git CyberRepo</div>
            </div>
        </div>
    </div>
    
    <!-- Stats Section -->
    <div class="section fade-in">
        <h2 class="section-title">📈 QUANTUM METRICS</h2>
        <div class="stats-grid">
            <div class="stat-card">
                <h3>Neural Sync</h3>
                <p>Currently working on cutting-edge Flutter applications</p>
            </div>
            <div class="stat-card">
                <h3>Neural Link</h3>
                <p>amalvelayudhan96@gmail.com</p>
            </div>
        </div>
    </div>
    
    <!-- Footer -->
    <div style="text-align: center; padding: 3rem 1rem; opacity: 0.7;">
        <p><strong>🤖 Neural Core Active | Bengaluru Matrix | 2026</strong></p>
    </div>

    <script src="https://cdn.jsdelivr.net/npm/typed.js@2.0.12"></script>
    <script>
        // Typing Animation
        new Typed('#typing', {
            strings: [
                'Initializing Neural Matrix...',
                'Welcome to AMAL KVS Core',
                'Flutter Developer Online',
                'UI Quantum Render Active',
                'Neural Interface Synced'
            ],
            typeSpeed: 50,
            backSpeed: 30,
            backDelay: 1000,
            loop: true
        });
        
        // Scroll Animations
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                }
            });
        });
        
        document.querySelectorAll('.fade-in').forEach(el => {
            observer.observe(el);
        });
    </script>
</body>
</html>
