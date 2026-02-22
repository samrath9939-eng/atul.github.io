<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>NEXUS | Future Interface</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;600;800&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #3b82f6;
            --secondary: #a855f7;
            --bg-dark: #050810;
        }
        body { 
            font-family: 'Plus Jakarta Sans', sans-serif; 
            background: var(--bg-dark); 
            color: white; 
            overflow-x: hidden; 
        }

        /* --- 1. PARALLAX & BACKGROUND ENGINE --- */
        #parallax-bg {
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            z-index: -1;
            overflow: hidden;
            background: radial-gradient(circle at 50% 50%, #111827 0%, #050810 100%);
        }
        .particle {
            position: absolute;
            border-radius: 50%;
            background: white;
            opacity: 0.3;
            pointer-events: none;
        }

        /* --- 2. MICRO-INTERACTIONS (SCROLL TRIGGER) --- */
        .reveal {
            opacity: 0;
            transform: translateY(40px) scale(0.95);
            transition: all 0.8s cubic-bezier(0.22, 1, 0.36, 1);
        }
        .reveal.active {
            opacity: 1;
            transform: translateY(0) scale(1);
        }

        /* --- 3. GLOWING BUTTONS --- */
        .btn-glow {
            position: relative;
            overflow: hidden;
            transition: all 0.4s ease;
            box-shadow: 0 0 0 rgba(59, 130, 246, 0);
        }
        .btn-glow:hover {
            box-shadow: 0 0 25px rgba(59, 130, 246, 0.5);
            transform: translateY(-3px);
        }
        .btn-glow:active { transform: scale(0.95); }

        /* Glassmorphism Refined */
        .glass {
            background: rgba(255, 255, 255, 0.03);
            backdrop-filter: blur(15px);
            border: 1px solid rgba(255, 255, 255, 0.08);
            transition: border 0.3s ease;
        }
        .glass:hover { border: 1px solid rgba(59, 130, 246, 0.3); }

        /* Floating Animation */
        @keyframes float-slow {
            0% { transform: translate(0, 0); }
            50% { transform: translate(15px, -20px); }
            100% { transform: translate(0, 0); }
        }
        .floating { animation: float-slow 8s ease-in-out infinite; }
    </style>
</head>
<body>

    <div id="parallax-bg">
        <div class="particle floating" style="width: 2px; height: 2px; top: 20%; left: 10%; box-shadow: 0 0 10px white;"></div>
        <div class="particle floating" style="width: 3px; height: 3px; top: 60%; left: 80%; animation-delay: 2s;"></div>
        <div class="particle floating" style="width: 1px; height: 1px; top: 40%; left: 40%; animation-delay: 4s;"></div>
        <div class="absolute top-[-10%] left-[-10%] w-[40%] h-[40%] bg-blue-600/10 blur-[120px] rounded-full"></div>
        <div class="absolute bottom-[-10%] right-[-10%] w-[40%] h-[40%] bg-purple-600/10 blur-[120px] rounded-full"></div>
    </div>

    <section class="relative h-screen flex items-center justify-center px-6 overflow-hidden">
        <div class="text-center z-10 space-y-6">
            <h1 id="hero-title" class="text-6xl md:text-8xl font-black tracking-tighter bg-clip-text text-transparent bg-gradient-to-b from-white to-gray-500">
                BEYOND LIMITS.
            </h1>
            <p class="text-gray-400 text-lg md:text-xl max-w-2xl mx-auto reveal">
                A seamless fusion of high-performance engineering and futuristic aesthetics.
            </p>
            <div class="flex gap-4 justify-center pt-4 reveal">
                <button class="btn-glow bg-blue-600 px-8 py-4 rounded-full font-bold">Get Started</button>
                <button class="px-8 py-4 rounded-full border border-white/20 hover:bg-white/10 transition">Portfolio</button>
            </div>
        </div>
    </section>

    <section id="about" class="py-32 px-6 max-w-7xl mx-auto">
        <div class="grid grid-cols-1 md:grid-cols-2 gap-20 items-center">
            <div class="reveal">
                <h2 class="text-4xl font-bold mb-6 italic">Engineering<br><span class="text-blue-500">The Future</span></h2>
                <p class="text-gray-400 leading-loose">We don't just build websites; we create digital dimensions. Every pixel is calculated, every animation is intentional.</p>
            </div>
            <div class="grid grid-cols-2 gap-4">
                <div class="glass p-6 rounded-2xl reveal shadow-2xl" style="transition-delay: 0.1s;">
                    <h3 class="text-3xl font-bold text-blue-500">99%</h3>
                    <p class="text-xs text-gray-500 uppercase tracking-widest">Uptime</p>
                </div>
                <div class="glass p-6 rounded-2xl reveal shadow-2xl" style="transition-delay: 0.2s;">
                    <h3 class="text-3xl font-bold text-purple-500">24/7</h3>
                    <p class="text-xs text-gray-500 uppercase tracking-widest">Support</p>
                </div>
            </div>
        </div>
    </section>

    <section id="features" class="py-32 bg-white/5">
        <div class="max-w-7xl mx-auto px-6">
            <div class="text-center mb-20 reveal">
                <h2 class="text-4xl font-bold mb-4">Core Systems</h2>
                <div class="h-1 w-12 bg-blue-500 mx-auto"></div>
            </div>
            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <div class="glass p-8 rounded-[2rem] reveal hover:-translate-y-4 transition-all duration-500 group">
                    <div class="w-14 h-14 bg-blue-500/20 rounded-xl flex items-center justify-center mb-6 group-hover:bg-blue-500 transition">
                        <i class="fas fa-layer-group text-2xl"></i>
                    </div>
                    <h3 class="text-xl font-bold mb-4">Architecture</h3>
                    <p class="text-gray-400 text-sm">Scalable cloud-native structures built for massive data throughput.</p>
                </div>
                <div class="glass p-8 rounded-[2rem] reveal hover:-translate-y-4 transition-all duration-500 group" style="transition-delay: 0.2s;">
                    <div class="w-14 h-14 bg-purple-500/20 rounded-xl flex items-center justify-center mb-6 group-hover:bg-purple-500 transition">
                        <i class="fas fa-brain text-2xl"></i>
                    </div>
                    <h3 class="text-xl font-bold mb-4">Intelligence</h3>
                    <p class="text-gray-400 text-sm">Deep learning nodes integrated directly into your workflow.</p>
                </div>
                <div class="glass p-8 rounded-[2rem] reveal hover:-translate-y-4 transition-all duration-500 group" style="transition-delay: 0.4s;">
                    <div class="w-14 h-14 bg-pink-500/20 rounded-xl flex items-center justify-center mb-6 group-hover:bg-pink-500 transition">
                        <i class="fas fa-microchip text-2xl"></i>
                    </div>
                    <h3 class="text-xl font-bold mb-4">Hardware</h3>
                    <p class="text-gray-400 text-sm">Optimized for low-latency processing and edge computing.</p>
                </div>
            </div>
        </div>
    </section>

    <section class="py-32 px-6">
        <div class="max-w-5xl mx-auto glass rounded-[3rem] p-16 text-center reveal overflow-hidden relative">
            <div class="absolute top-0 left-0 w-full h-full bg-gradient-to-r from-blue-600/10 to-purple-600/10 -z-10"></div>
            <h2 class="text-4xl md:text-5xl font-bold mb-8">Ready to Transcend?</h2>
            <button class="btn-glow bg-white text-black px-10 py-4 rounded-full font-bold text-lg">Join the Network</button>
        </div>
    </section>

    <footer class="py-12 px-6 border-t border-white/5">
        <div class="max-w-7xl mx-auto flex flex-col md:flex-row justify-between items-center gap-6">
            <div class="text-xl font-black text-blue-500">NEXUS.</div>
            <div class="flex gap-8">
                <a href="#" class="text-gray-500 hover:text-white transition"><i class="fab fa-github"></i></a>
                <a href="#" class="text-gray-500 hover:text-white transition"><i class="fab fa-linkedin"></i></a>
            </div>
            <p class="text-gray-600 text-xs tracking-widest">EST 2026 / ALL RIGHTS RESERVED</p>
        </div>
    </footer>

    <div class="fixed bottom-8 right-8 z-[100] group">
        <div class="absolute -top-12 right-0 bg-blue-600 text-white text-[10px] px-3 py-1 rounded-full opacity-0 group-hover:opacity-100 transition shadow-xl font-bold">ONLINE</div>
        <button class="w-16 h-16 bg-blue-600 rounded-2xl flex items-center justify-center shadow-[0_10px_30px_rgba(59,130,246,0.4)] hover:rotate-6 active:scale-90 transition-all duration-300">
            <i class="fas fa-comment-alt text-xl"></i>
        </button>
    </div>

    <script>
        // 1. PARALLAX EFFECT
        window.addEventListener('scroll', () => {
            const scroll = window.pageYOffset;
            const heroTitle = document.getElementById('hero-title');
            heroTitle.style.transform = `translateY(${scroll * 0.4}px)`;
            heroTitle.style.opacity = 1 - (scroll / 700);
            
            // Subtle Background Parallax
            document.getElementById('parallax-bg').style.transform = `translateY(${scroll * 0.1}px)`;
        });

        // 2. SCROLL REVEAL (INTERSECTION OBSERVER)
        const observerOptions = { threshold: 0.15 };
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('active');
                }
            });
        }, observerOptions);

        document.querySelectorAll('.reveal').forEach(el => observer.observe(el));

        // 3. DYNAMIC PARTICLE GENERATION
        const bg = document.getElementById('parallax-bg');
        for (let i = 0; i < 30; i++) {
            const p = document.createElement('div');
            p.className = 'particle';
            const size = Math.random() * 3 + 'px';
            p.style.width = size;
            p.style.height = size;
            p.style.top = Math.random() * 100 + '%';
            p.style.left = Math.random() * 100 + '%';
            p.style.animation = `float-slow ${5 + Math.random() * 10}s infinite`;
            bg.appendChild(p);
        }
    </script>
</body>
</html>
