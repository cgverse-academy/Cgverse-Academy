<!DOCTYPE html>
<html lang="en" class="scroll-smooth dark">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>CGVerse Academy | 3D Game Art & Digital Sculpting Mentorship</title>
  <meta name="description" content="Turn your art passion into a career as a 3D Game Artist & Digital 3D Sculptor. Learn ZBrush, Blender/Maya, Substance 3D Painter, Photoshop & Premiere Pro from industry professionals." />
  
  <!-- Google Fonts: Inter & Space Grotesk for a sharp 3D Studio aesthetic -->
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&family=Space+Grotesk:wght@600;700&display=swap" rel="stylesheet" />

  <!-- Tailwind CSS via CDN (Zero build step required for GitHub Pages) -->
  <script src="https://cdn.tailwindcss.com"></script>
  <script>
    tailwind.config = {
      darkMode: 'class',
      theme: {
        extend: {
          fontFamily: {
            sans: ['Inter', 'sans-serif'],
            display: ['Space Grotesk', 'sans-serif'],
          },
          colors: {
            obsidian: '#07090E',
            surface: '#0E121B',
            card: '#131824',
            cyanGlow: '#06B6D4',
            violetGlow: '#8B5CF6',
          },
          animation: {
            'pulse-slow': 'pulse 4s cubic-bezier(0.4, 0, 0.6, 1) infinite',
            'float': 'float 6s ease-in-out infinite',
          },
          keyframes: {
            float: {
              '0%, 100%': { transform: 'translateY(0px)' },
              '50%': { transform: 'translateY(-10px)' },
            }
          }
        }
      }
    }
  </script>

  <style>
    /* Custom subtle grid background & glassmorphic utilities */
    body {
      background-color: #07090E;
      color: #F8FAFC;
      overflow-x: hidden;
    }
    .bg-studio-grid {
      background-size: 40px 40px;
      background-image: 
        linear-gradient(to right, rgba(255, 255, 255, 0.03) 1px, transparent 1px),
        linear-gradient(to bottom, rgba(255, 255, 255, 0.03) 1px, transparent 1px);
    }
    .glass-nav {
      background: rgba(7, 9, 14, 0.82);
      backdrop-filter: blur(14px);
      -webkit-backdrop-filter: blur(14px);
    }
    .card-glow:hover {
      box-shadow: 0 0 35px -5px rgba(6, 182, 212, 0.22);
    }
    .featured-glow {
      box-shadow: 0 0 45px -10px rgba(139, 92, 246, 0.35);
    }
    .featured-glow:hover {
      box-shadow: 0 0 55px -5px rgba(6, 182, 212, 0.4);
    }
  </style>
</head>
<body class="font-sans antialiased selection:bg-cyan-500 selection:text-slate-950">

  <!-- ==================== 1. NAVIGATION BAR ==================== -->
  <header class="fixed top-0 inset-x-0 z-50 glass-nav border-b border-slate-800/80">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex items-center justify-between h-16 sm:h-20">
        
        <!-- Logo -->
        <a href="#" class="flex items-center gap-3 group">
          <div class="w-10 h-10 rounded-xl bg-gradient-to-br from-cyan-400 via-blue-500 to-violet-600 p-0.5 shadow-lg shadow-cyan-500/20 group-hover:scale-105 transition-transform">
            <div class="w-full h-full bg-obsidian rounded-[10px] flex items-center justify-center">
              <!-- 3D Cube Wireframe Icon -->
              <svg class="w-6 h-6 text-cyan-400" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path stroke-linecap="round" stroke-linejoin="round" d="M21 16V8a2 2 0 0 0-1-1.73l-7-4a2 2 0 0 0-2 0l-7 4A2 2 0 0 0 3 8v8a2 2 0 0 0 1 1.73l7 4a2 2 0 0 0 2 0l7-4A2 2 0 0 0 21 16z" />
                <polyline points="3.27 6.96 12 12.01 20.73 6.96" />
                <line x1="12" y1="22.08" x2="12" y2="12" />
              </svg>
            </div>
          </div>
          <div>
            <span class="font-display font-bold text-xl tracking-tight text-white">CGVerse</span>
            <span class="block text-[11px] uppercase tracking-[0.2em] text-cyan-400 font-semibold -mt-1">Academy</span>
          </div>
        </a>

        <!-- Desktop Navigation Links -->
        <nav class="hidden md:flex items-center gap-8 text-sm font-medium text-slate-300">
          <a href="#about" class="hover:text-cyan-400 transition-colors">About</a>
          <a href="#courses" class="hover:text-cyan-400 transition-colors">Courses</a>
          <a href="#why-us" class="hover:text-cyan-400 transition-colors">Why Us</a>
        </nav>

        <!-- Desktop CTA & Mobile Menu Toggle -->
        <div class="flex items-center gap-3">
          <a href="#consultation" class="inline-flex items-center justify-center px-4 sm:px-5 py-2.5 text-xs sm:text-sm font-semibold text-slate-950 bg-gradient-to-r from-cyan-400 to-teal-300 rounded-xl shadow-lg shadow-cyan-500/25 hover:shadow-cyan-400/45 hover:brightness-110 transition-all">
            Book Free Consultation
          </a>
          <button id="mobile-menu-btn" aria-label="Toggle Menu" class="md:hidden p-2.5 rounded-xl bg-slate-900 border border-slate-800 text-slate-300 hover:text-white">
            <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
            </svg>
          </button>
        </div>
      </div>
    </div>

    <!-- Mobile Dropdown Navigation -->
    <div id="mobile-menu" class="hidden md:hidden border-t border-slate-800 bg-obsidian px-4 pt-3 pb-5 space-y-2">
      <a href="#about" class="block px-3 py-2.5 rounded-xl text-slate-300 hover:bg-slate-900 hover:text-cyan-400 font-medium">About</a>
      <a href="#courses" class="block px-3 py-2.5 rounded-xl text-slate-300 hover:bg-slate-900 hover:text-cyan-400 font-medium">Courses</a>
      <a href="#why-us" class="block px-3 py-2.5 rounded-xl text-slate-300 hover:bg-slate-900 hover:text-cyan-400 font-medium">Why Us</a>
    </div>
  </header>

  <main>
    <!-- ==================== 2. HERO SECTION ==================== -->
    <section class="relative pt-28 pb-20 sm:pt-36 sm:pb-28 bg-studio-grid overflow-hidden">
      <!-- Ambient Studio Glows -->
      <div class="pointer-events-none absolute -top-24 left-1/2 -translate-x-1/2 w-[680px] h-[380px] bg-gradient-to-r from-cyan-500/20 via-violet-600/20 to-amber-500/10 blur-3xl rounded-full animate-pulse-slow"></div>

      <div class="relative max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
        
        <!-- Urgency Badge -->
        <div class="inline-flex items-center gap-2.5 px-4 py-2 rounded-full bg-amber-500/10 border border-amber-400/30 text-amber-300 text-xs sm:text-sm font-semibold mb-8 shadow-md shadow-amber-500/5">
          <span class="relative flex h-2.5 w-2.5">
            <span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-amber-400 opacity-75"></span>
            <span class="relative inline-flex rounded-full h-2.5 w-2.5 bg-amber-400"></span>
          </span>
          <span>🔥 Batches Started Last Week — Limited Seats Remaining!</span>
        </div>

        <!-- Main Headline -->
        <h1 class="font-display text-4xl sm:text-5xl lg:text-6xl font-bold tracking-tight text-white max-w-4xl mx-auto leading-[1.12]">
          Turn Your Art Passion into a Career as a
          <span class="bg-gradient-to-r from-cyan-400 via-violet-400 to-amber-300 bg-clip-text text-transparent">
            3D Game Artist & Digital Sculptor
          </span>
        </h1>

        <!-- Subheadline -->
        <p class="mt-6 text-base sm:text-lg lg:text-xl text-slate-300 max-w-3xl mx-auto leading-relaxed">
          A lifetime opportunity to build your future in the gaming and digital art industry. Learn directly from seasoned industry professionals who guide you every step of the way until you land your first job.
        </p>

        <!-- Primary & Secondary CTAs -->
        <div class="mt-10 flex flex-col sm:flex-row items-center justify-center gap-4">
          <a href="#consultation" class="w-full sm:w-auto inline-flex items-center justify-center gap-2 px-8 py-4 text-base font-bold text-slate-950 bg-gradient-to-r from-cyan-400 via-teal-300 to-cyan-300 rounded-2xl shadow-xl shadow-cyan-500/25 hover:shadow-cyan-400/45 hover:-translate-y-0.5 transition-all">
            <span>Claim Your Spot Now</span>
            <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2.2" d="M13 7l5 5m0 0l-5 5m5-5H6" />
            </svg>
          </a>
          <a href="#courses" class="w-full sm:w-auto inline-flex items-center justify-center gap-2 px-8 py-4 text-base font-semibold text-white bg-slate-900/90 border border-slate-700/80 hover:border-cyan-400/60 hover:bg-slate-800/90 rounded-2xl transition-all">
            <span>Explore Courses</span>
          </a>
        </div>

        <!-- Quick Studio Pipeline Highlight Strip -->
        <div class="mt-14 pt-8 border-t border-slate-800/80 max-w-4xl mx-auto">
          <p class="text-xs uppercase tracking-widest text-slate-400 font-semibold mb-4">Master Production-Standard Industry Tools</p>
          <div class="flex flex-wrap items-center justify-center gap-2.5 sm:gap-3">
            <span class="px-3.5 py-1.5 rounded-xl bg-slate-900 border border-slate-800 text-xs sm:text-sm font-medium text-slate-200 hover:border-amber-400/50 transition-colors">ZBrush</span>
            <span class="px-3.5 py-1.5 rounded-xl bg-slate-900 border border-slate-800 text-xs sm:text-sm font-medium text-slate-200 hover:border-cyan-400/50 transition-colors">Blender / Maya</span>
            <span class="px-3.5 py-1.5 rounded-xl bg-slate-900 border border-slate-800 text-xs sm:text-sm font-medium text-slate-200 hover:border-violet-400/50 transition-colors">Substance 3D Painter</span>
            <span class="px-3.5 py-1.5 rounded-xl bg-slate-900 border border-slate-800 text-xs sm:text-sm font-medium text-slate-200 hover:border-blue-400/50 transition-colors">Adobe Photoshop</span>
            <span class="px-3.5 py-1.5 rounded-xl bg-slate-900 border border-slate-800 text-xs sm:text-sm font-medium text-slate-200 hover:border-fuchsia-400/50 transition-colors">Adobe Premiere Pro</span>
          </div>
        </div>
      </div>
    </section>

    <!-- ==================== 3. ABOUT & CAREER OPPORTUNITY ("WHAT WE DO") ==================== -->
    <section id="about" class="py-20 sm:py-24 bg-surface border-y border-slate-800/70">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        
        <!-- Section Intro -->
        <div class="max-w-3xl mx-auto text-center mb-16">
          <span class="text-xs font-bold uppercase tracking-widest text-cyan-400">What We Do & Why CGVerse</span>
          <h2 class="mt-3 font-display text-3xl sm:text-4xl font-bold text-white">
            Convert Your Art Hobbies into a Money-Making Profession
          </h2>
          <p class="mt-4 text-slate-300 text-base sm:text-lg leading-relaxed">
            If you are an art enthusiast dreaming of building characters, creatures, and game worlds for AAA studios and indie hits, this is your chance. At <strong class="text-white">CGVerse Academy</strong>, we bridge the gap between raw artistic passion and studio-ready production skills.
          </p>
        </div>

        <!-- 4 Core Value Pillars -->
        <div id="why-us" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
          
          <!-- Pillar 1 -->
          <div class="p-6 sm:p-7 rounded-2xl bg-card border border-slate-800/90 card-glow transition-all duration-300 hover:-translate-y-1">
            <div class="w-12 h-12 rounded-xl bg-cyan-500/10 border border-cyan-500/30 flex items-center justify-center text-cyan-400 mb-5">
              <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 13.255A23.931 23.931 0 0112 15c-3.183 0-6.22-.62-9-1.745M16 6V4a2 2 0 00-2-2h-4a2 2 0 00-2 2v2m4 6h.01M5 20h14a2 2 0 002-2V8a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
              </svg>
            </div>
            <h3 class="text-lg font-bold text-white mb-2.5">Industry-Veteran Mentorship</h3>
            <p class="text-sm text-slate-300 leading-relaxed">
              Learn directly from active game & 3D industry professionals who mentor you personally and guide you all the way until you get your first job.
            </p>
          </div>

          <!-- Pillar 2 -->
          <div class="p-6 sm:p-7 rounded-2xl bg-card border border-slate-800/90 card-glow transition-all duration-300 hover:-translate-y-1">
            <div class="w-12 h-12 rounded-xl bg-violet-500/10 border border-violet-500/30 flex items-center justify-center text-violet-400 mb-5">
              <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 10l4.553-2.276A1 1 0 0121 8.618v6.764a1 1 0 01-1.447.894L15 14M5 18h8a2 2 0 002-2V8a2 2 0 00-2-2H5a2 2 0 00-2 2v8a2 2 0 002 2z" />
              </svg>
            </div>
            <h3 class="text-lg font-bold text-white mb-2.5">Live Interactive Online Classes</h3>
            <p class="text-sm text-slate-300 leading-relaxed">
              Join live online classes from anywhere, watch real-time sculpting & modeling workflows, and ask 1-on-1 questions for instant feedback.
            </p>
          </div>

          <!-- Pillar 3 -->
          <div class="p-6 sm:p-7 rounded-2xl bg-card border border-slate-800/90 card-glow transition-all duration-300 hover:-translate-y-1">
            <div class="w-12 h-12 rounded-xl bg-amber-500/10 border border-amber-500/30 flex items-center justify-center text-amber-400 mb-5">
              <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14.752 11.168l-3.197-2.132A1 1 0 0010 9.87v4.263a1 1 0 001.555.832l3.197-2.132a1 1 0 000-1.664z" />
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 12a9 9 0 11-18 0 9 9 0 0118 0z" />
              </svg>
            </div>
            <h3 class="text-lg font-bold text-white mb-2.5">Anytime Recorded Access</h3>
            <p class="text-sm text-slate-300 leading-relaxed">
              Unable to attend a live session due to personal or work reasons? Every class is recorded so you can access and revise anytime without missing a beat.
            </p>
          </div>

          <!-- Pillar 4 -->
          <div class="p-6 sm:p-7 rounded-2xl bg-card border border-slate-800/90 card-glow transition-all duration-300 hover:-translate-y-1">
            <div class="w-12 h-12 rounded-xl bg-emerald-500/10 border border-emerald-500/30 flex items-center justify-center text-emerald-400 mb-5">
              <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4M7.835 4.697a3.42 3.42 0 001.946-.806 3.42 3.42 0 014.438 0 3.42 3.42 0 001.946.806 3.42 3.42 0 013.138 3.138 3.42 3.42 0 00.806 1.946 3.42 3.42 0 010 4.438 3.42 3.42 0 00-.806 1.946 3.42 3.42 0 01-3.138 3.138 3.42 3.42 0 00-1.946.806 3.42 3.42 0 01-4.438 0 3.42 3.42 0 00-1.946-.806 3.42 3.42 0 01-3.138-3.138 3.42 3.42 0 00-.806-1.946 3.42 3.42 0 010-4.438 3.42 3.42 0 00.806-1.946 3.42 3.42 0 013.138-3.138z" />
              </svg>
            </div>
            <h3 class="text-lg font-bold text-white mb-2.5">Job-Ready Portfolio Focus</h3>
            <p class="text-sm text-slate-300 leading-relaxed">
              Build production-grade 3D assets, sculpts, and showreels over a focused 4 to 6-month timeline engineered to impress studio recruiters.
            </p>
          </div>

        </div>
      </div>
    </section>

    <!-- ==================== 4. COURSES & BATCHES SECTION ("CHOOSE YOUR TRACK") ==================== -->
    <section id="courses" class="py-20 sm:py-28 bg-obsidian bg-studio-grid relative">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        
        <!-- Section Header -->
        <div class="text-center max-w-3xl mx-auto mb-16">
          <span class="inline-block px-3.5 py-1 rounded-full bg-cyan-500/10 border border-cyan-500/30 text-cyan-300 text-xs font-bold uppercase tracking-wider mb-3">
            4 to 6 Months Intensive Program • Live Online + Recorded Sessions
          </span>
          <h2 class="font-display text-3xl sm:text-4xl lg:text-5xl font-bold text-white">
            Choose Your Track
          </h2>
          <p class="mt-4 text-slate-300 text-base sm:text-lg">
            Whether you are picking up a stylus for the first time or leveling up your 3D workflow for AAA game studios, we have a dedicated batch tailored to your skill level.
          </p>
        </div>

        <!-- Side-by-Side Batch Cards -->
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-8 max-w-6xl mx-auto items-stretch">
          
          <!-- BATCH 1: BEGINNER LEVEL TRACK -->
          <div class="flex flex-col justify-between p-7 sm:p-10 rounded-3xl bg-card border border-slate-800 card-glow transition-all duration-300">
            <div>
              <div class="flex flex-wrap items-center justify-between gap-2 mb-5">
                <span class="px-3.5 py-1 rounded-xl bg-cyan-500/10 border border-cyan-500/30 text-cyan-300 text-xs font-bold uppercase tracking-wider">
                  Batch 01 • Foundation
                </span>
                <span class="text-xs font-semibold text-slate-400">4 – 6 Months Duration</span>
              </div>

              <h3 class="font-display text-2xl sm:text-3xl font-bold text-white">
                Beginner Level Track
              </h3>
              <p class="mt-3 text-slate-300 text-sm sm:text-base leading-relaxed">
                Designed for aspiring artists and hobbyists starting from scratch. Master the core foundations of digital sculpting, 3D modeling, texturing basics, and portfolio presentation.
              </p>

              <!-- 4 Softwares Covered -->
              <div class="mt-7">
                <p class="text-xs font-bold uppercase tracking-wider text-slate-400 mb-3">
                  4 Core Industry Softwares Covered:
                </p>
                <div class="flex flex-wrap gap-2">
                  <span class="px-3 py-1.5 rounded-xl bg-slate-900 border border-amber-500/30 text-amber-300 text-xs font-semibold hover:scale-105 transition-transform">
                    ZBrush
                  </span>
                  <span class="px-3 py-1.5 rounded-xl bg-slate-900 border border-cyan-500/30 text-cyan-300 text-xs font-semibold hover:scale-105 transition-transform">
                    Blender / Maya
                  </span>
                  <span class="px-3 py-1.5 rounded-xl bg-slate-900 border border-blue-500/30 text-blue-300 text-xs font-semibold hover:scale-105 transition-transform">
                    Adobe Photoshop
                  </span>
                  <span class="px-3 py-1.5 rounded-xl bg-slate-900 border border-purple-500/30 text-purple-300 text-xs font-semibold hover:scale-105 transition-transform">
                    Adobe Premiere Pro
                  </span>
                </div>
              </div>

              <!-- Curriculum Highlights -->
              <ul class="mt-8 space-y-3.5 text-sm text-slate-300 border-t border-slate-800/90 pt-6">
                <li class="flex items-start gap-3">
                  <svg class="w-5 h-5 text-cyan-400 shrink-0 mt-0.5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2.2" d="M5 13l4 4L19 7" /></svg>
                  <span>Fundamentals of 3D modeling, topology & hard-surface/organic forms</span>
                </li>
                <li class="flex items-start gap-3">
                  <svg class="w-5 h-5 text-cyan-400 shrink-0 mt-0.5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2.2" d="M5 13l4 4L19 7" /></svg>
                  <span>Digital sculpting anatomy, proportions & detailing in ZBrush</span>
                </li>
                <li class="flex items-start gap-3">
                  <svg class="w-5 h-5 text-cyan-400 shrink-0 mt-0.5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2.2" d="M5 13l4 4L19 7" /></svg>
                  <span>Texturing basics, render passes & post-processing in Photoshop</span>
                </li>
                <li class="flex items-start gap-3">
                  <svg class="w-5 h-5 text-cyan-400 shrink-0 mt-0.5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2.2" d="M5 13l4 4L19 7" /></svg>
                  <span>Turntable showreel editing & presentation in Premiere Pro</span>
                </li>
                <li class="flex items-start gap-3">
                  <svg class="w-5 h-5 text-cyan-400 shrink-0 mt-0.5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2.2" d="M5 13l4 4L19 7" /></svg>
                  <span>Live 1-on-1 Q&A + Full Recorded Session Access</span>
                </li>
              </ul>
            </div>

            <div class="mt-9 pt-6 border-t border-slate-800/80">
              <button type="button" onclick="selectTrackAndScroll('Beginner Level Track (4 Softwares)')" class="w-full py-3.5 px-6 rounded-2xl bg-slate-800 hover:bg-cyan-500 text-white hover:text-slate-950 font-bold text-sm sm:text-base transition-all border border-slate-700 hover:border-cyan-400">
                Enroll in Beginner Batch
              </button>
            </div>
          </div>

          <!-- BATCH 2: INTERMEDIATE LEVEL TRACK (FEATURED) -->
          <div class="relative flex flex-col justify-between p-7 sm:p-10 rounded-3xl bg-gradient-to-b from-[#171D2E] to-card border-2 border-violet-500/70 featured-glow transition-all duration-300">
            
            <!-- Most Popular Badge -->
            <div class="absolute -top-4 right-6 sm:right-8">
              <span class="inline-flex items-center gap-1.5 px-4 py-1.5 rounded-full bg-gradient-to-r from-violet-600 to-cyan-500 text-white text-xs font-extrabold uppercase tracking-wider shadow-lg">
                ★ Most Popular • Job-Ready Track
              </span>
            </div>

            <div>
              <div class="flex flex-wrap items-center justify-between gap-2 mb-5 mt-1">
                <span class="px-3.5 py-1 rounded-xl bg-violet-500/15 border border-violet-400/40 text-violet-300 text-xs font-bold uppercase tracking-wider">
                  Batch 02 • Production Mastery
                </span>
                <span class="text-xs font-semibold text-cyan-300">4 – 6 Months Duration</span>
              </div>

              <h3 class="font-display text-2xl sm:text-3xl font-bold text-white">
                Intermediate Level Track
              </h3>
              <p class="mt-3 text-slate-300 text-sm sm:text-base leading-relaxed">
                Designed to elevate your existing 3D skills to AAA studio standards. Master complete next-gen character & prop pipelines, realistic PBR texturing, look-dev, and job placement preparation.
              </p>

              <!-- 5 Softwares Covered -->
              <div class="mt-7">
                <p class="text-xs font-bold uppercase tracking-wider text-slate-400 mb-3">
                  5 Industry-Standard Softwares Covered:
                </p>
                <div class="flex flex-wrap gap-2">
                  <span class="px-3 py-1.5 rounded-xl bg-slate-900 border border-amber-500/40 text-amber-300 text-xs font-semibold hover:scale-105 transition-transform">
                    ZBrush
                  </span>
                  <span class="px-3 py-1.5 rounded-xl bg-slate-900 border border-cyan-500/40 text-cyan-300 text-xs font-semibold hover:scale-105 transition-transform">
                    Blender / Maya
                  </span>
                  <span class="px-3 py-1.5 rounded-xl bg-slate-900 border border-emerald-400/50 text-emerald-300 text-xs font-bold hover:scale-105 transition-transform shadow-sm shadow-emerald-500/10">
                    + Substance 3D Painter
                  </span>
                  <span class="px-3 py-1.5 rounded-xl bg-slate-900 border border-blue-500/40 text-blue-300 text-xs font-semibold hover:scale-105 transition-transform">
                    Adobe Photoshop
                  </span>
                  <span class="px-3 py-1.5 rounded-xl bg-slate-900 border border-purple-500/40 text-purple-300 text-xs font-semibold hover:scale-105 transition-transform">
                    Adobe Premiere Pro
                  </span>
                </div>
              </div>

              <!-- Curriculum Highlights -->
              <ul class="mt-8 space-y-3.5 text-sm text-slate-200 border-t border-slate-800/90 pt-6">
                <li class="flex items-start gap-3">
                  <svg class="w-5 h-5 text-violet-400 shrink-0 mt-0.5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2.2" d="M5 13l4 4L19 7" /></svg>
                  <span>Advanced character, creature & hero prop sculpting in ZBrush</span>
                </li>
                <li class="flex items-start gap-3">
                  <svg class="w-5 h-5 text-violet-400 shrink-0 mt-0.5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2.2" d="M5 13l4 4L19 7" /></svg>
                  <span>Game-ready retopology, UV unwrapping & baking in Blender / Maya</span>
                </li>
                <li class="flex items-start gap-3">
                  <svg class="w-5 h-5 text-emerald-400 shrink-0 mt-0.5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2.2" d="M5 13l4 4L19 7" /></svg>
                  <span><strong>Next-Gen PBR Texturing & Material Creation in Substance 3D Painter</strong></span>
                </li>
                <li class="flex items-start gap-3">
                  <svg class="w-5 h-5 text-violet-400 shrink-0 mt-0.5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2.2" d="M5 13l4 4L19 7" /></svg>
                  <span>Studio lighting, look-dev, ArtStation portfolio polish & showreel</span>
                </li>
                <li class="flex items-start gap-3">
                  <svg class="w-5 h-5 text-violet-400 shrink-0 mt-0.5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2.2" d="M5 13l4 4L19 7" /></svg>
                  <span>1-on-1 Career Guidance until you land your first 3D Artist job</span>
                </li>
              </ul>
            </div>

            <div class="mt-9 pt-6 border-t border-slate-800/80">
              <button type="button" onclick="selectTrackAndScroll('Intermediate Level Track (5 Softwares)')" class="w-full py-3.5 px-6 rounded-2xl bg-gradient-to-r from-violet-600 via-indigo-500 to-cyan-500 hover:brightness-110 text-white font-bold text-sm sm:text-base shadow-lg shadow-violet-600/30 transition-all">
                Enroll in Intermediate Batch
              </button>
            </div>
          </div>

        </div>
      </div>
    </section>

    <!-- ==================== 5. CONSULTATION & ENROLLMENT FORM SECTION ==================== -->
    <section id="consultation" class="py-20 sm:py-28 bg-surface border-t border-slate-800/80 relative overflow-hidden">
      <!-- Subtle Background Glow -->
      <div class="pointer-events-none absolute bottom-0 right-0 w-[500px] h-[500px] bg-cyan-500/10 blur-3xl rounded-full"></div>

      <div class="relative max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="grid grid-cols-1 lg:grid-cols-12 gap-10 lg:gap-12 items-center">
          
          <!-- Left Persuasive Callout Column -->
          <div class="lg:col-span-5 space-y-6">
            <div class="inline-flex items-center gap-2 px-3.5 py-1.5 rounded-full bg-rose-500/10 border border-rose-500/30 text-rose-300 text-xs font-bold uppercase tracking-wider">
              ⏳ Ongoing Enrollment — Don't Miss Out
            </div>

            <h2 class="font-display text-3xl sm:text-4xl font-bold text-white leading-tight">
              Book Your Free 1-on-1 Career Consultation
            </h2>

            <p class="text-slate-300 text-base leading-relaxed">
              <strong class="text-amber-300">Our new batches kicked off last week!</strong> Hurry up and fill out the form so our mentors can reach out to you for a free 1-on-1 career consultation, review your goals, and help you join the right batch right away.
            </p>

            <div class="space-y-4 pt-2">
              <div class="flex items-start gap-3.5">
                <div class="w-8 h-8 rounded-lg bg-cyan-500/15 border border-cyan-500/30 flex items-center justify-center text-cyan-400 shrink-0 mt-0.5 font-bold text-sm">1</div>
                <div>
                  <h4 class="text-sm font-bold text-white">Personalized Roadmap</h4>
                  <p class="text-xs sm:text-sm text-slate-400">Get honest advice on whether the Beginner or Intermediate track fits your current skill level.</p>
                </div>
              </div>
              <div class="flex items-start gap-3.5">
                <div class="w-8 h-8 rounded-lg bg-violet-500/15 border border-violet-500/30 flex items-center justify-center text-violet-400 shrink-0 mt-0.5 font-bold text-sm">2</div>
                <div>
                  <h4 class="text-sm font-bold text-white">Catch-Up Recorded Access Included</h4>
                  <p class="text-xs sm:text-sm text-slate-400">Since batches started last week, you'll get immediate access to the first week's session recordings so you start at 100% speed.</p>
                </div>
              </div>
              <div class="flex items-start gap-3.5">
                <div class="w-8 h-8 rounded-lg bg-amber-500/15 border border-amber-500/30 flex items-center justify-center text-amber-400 shrink-0 mt-0.5 font-bold text-sm">3</div>
                <div>
                  <h4 class="text-sm font-bold text-white">Zero Obligation, Direct Mentor Call</h4>
                  <p class="text-xs sm:text-sm text-slate-400">Ask all your questions about class timings, hardware requirements, and job placement support.</p>
                </div>
              </div>
            </div>
          </div>

          <!-- Right Interactive Form Column -->
          <div class="lg:col-span-7">
            <div class="p-6 sm:p-10 rounded-3xl bg-card border border-slate-800 shadow-2xl">
              
       
              <form action="https://formspree.io/f/mbgozjrv"
           method="POST" class="space-y-5">
                
                <div class="grid grid-cols-1 sm:grid-cols-2 gap-5">
                  <!-- Full Name -->
                  <div>
                    <label for="fullName" class="block text-xs font-semibold uppercase tracking-wider text-slate-300 mb-2">
                      Full Name <span class="text-rose-400">*</span>
                    </label>
                    <input type="text" id="fullName" name="fullName" required placeholder="e.g. Aarav Sharma"
                      class="w-full px-4 py-3.5 rounded-xl bg-obsidian border border-slate-700/90 text-white placeholder-slate-500 text-sm focus:outline-none focus:border-cyan-400 focus:ring-1 focus:ring-cyan-400 transition-colors" />
                  </div>

                  <!-- Email Address -->
                  <div>
                    <label for="email" class="block text-xs font-semibold uppercase tracking-wider text-slate-300 mb-2">
                      Email Address <span class="text-rose-400">*</span>
                    </label>
                    <input type="email" id="email" name="email" required placeholder="you@example.com"
                      class="w-full px-4 py-3.5 rounded-xl bg-obsidian border border-slate-700/90 text-white placeholder-slate-500 text-sm focus:outline-none focus:border-cyan-400 focus:ring-1 focus:ring-cyan-400 transition-colors" />
                  </div>
                </div>

                <div class="grid grid-cols-1 sm:grid-cols-2 gap-5">
                  <!-- Phone / WhatsApp Number -->
                  <div>
                    <label for="phone" class="block text-xs font-semibold uppercase tracking-wider text-slate-300 mb-2">
                      Phone / WhatsApp Number <span class="text-rose-400">*</span>
                    </label>
                    <input type="tel" id="phone" name="phone" required placeholder="+91 98765 43210"
                      class="w-full px-4 py-3.5 rounded-xl bg-obsidian border border-slate-700/90 text-white placeholder-slate-500 text-sm focus:outline-none focus:border-cyan-400 focus:ring-1 focus:ring-cyan-400 transition-colors" />
                  </div>

                  <!-- Preferred Track -->
                  <div>
                    <label for="track" class="block text-xs font-semibold uppercase tracking-wider text-slate-300 mb-2">
                      Preferred Batch Track <span class="text-rose-400">*</span>
                    </label>
                    <select id="track" name="track" required
                      class="w-full px-4 py-3.5 rounded-xl bg-obsidian border border-slate-700/90 text-white text-sm focus:outline-none focus:border-cyan-400 focus:ring-1 focus:ring-cyan-400 transition-colors">
                      <option value="Beginner Level Track (4 Softwares)">Beginner Level Track (4 Softwares)</option>
                      <option value="Intermediate Level Track (5 Softwares)" selected>Intermediate Level Track (5 Softwares)</option>
                      <option value="Not Sure Yet — Need Mentor Guidance">Not Sure Yet — Need Mentor Guidance</option>
                    </select>
                  </div>
                </div>

                <!-- Current Experience / Art Background -->
                <div>
                  <label for="background" class="block text-xs font-semibold uppercase tracking-wider text-slate-300 mb-2">
                    Current Experience / Art Background
                  </label>
                  <textarea id="background" name="background" rows="3" placeholder="Tell us briefly about your sketching, 3D software experience, or career goals..."
                    class="w-full px-4 py-3 rounded-xl bg-obsidian border border-slate-700/90 text-white placeholder-slate-500 text-sm focus:outline-none focus:border-cyan-400 focus:ring-1 focus:ring-cyan-400 transition-colors"></textarea>
                </div>

                <!-- Inline Validation Message Box (Replaces browser alert) -->
                <div id="form-error" class="hidden p-3.5 rounded-xl bg-rose-500/10 border border-rose-500/30 text-rose-300 text-xs sm:text-sm font-medium">
                  Please fill in your Full Name, valid Email Address, and Phone/WhatsApp Number so our mentors can reach you.
                </div>

                <!-- Submit Button -->
                <button type="submit" class="w-full py-4 px-6 rounded-2xl bg-gradient-to-r from-cyan-400 via-teal-300 to-cyan-300 text-slate-950 font-extrabold text-base shadow-xl shadow-cyan-500/25 hover:shadow-cyan-400/45 hover:brightness-105 transition-all cursor-pointer">
                  Request My Free 1-on-1 Consultation →
                </button>

                <p class="text-center text-xs text-slate-400">
                  🔒 Your details are 100% confidential. Our mentor team typically responds within a few hours.
                </p>
              </form>

              <!-- Success State Panel (Shown upon valid submission) -->
              <div id="form-success" class="hidden text-center py-8 space-y-4">
                <div class="w-16 h-16 rounded-2xl bg-emerald-500/15 border border-emerald-500/40 text-emerald-400 flex items-center justify-center mx-auto">
                  <svg class="w-8 h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2.5" d="M5 13l4 4L19 7" />
                  </svg>
                </div>
                <h3 class="font-display text-2xl font-bold text-white">Application Received!</h3>
                <p id="success-message" class="text-slate-300 text-sm sm:text-base max-w-md mx-auto leading-relaxed">
                  Thank you for applying to <strong class="text-cyan-400">CGVerse Academy</strong>! One of our industry mentors will reach out shortly via WhatsApp or Email for your free 1-on-1 consultation.
                </p>
                <div class="pt-4">
                  <button type="button" onclick="resetConsultationForm()" class="px-5 py-2.5 rounded-xl bg-slate-800 hover:bg-slate-700 text-slate-200 text-xs font-semibold border border-slate-700 transition-colors">
                    Submit Another Inquiry
                  </button>
                </div>
              </div>

            </div>
          </div>

        </div>
      </div>
    </section>
  </main>

  <!-- ==================== 6. FOOTER ==================== -->
  <footer class="bg-obsidian border-t border-slate-800/90 py-12">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex flex-col md:flex-row items-start md:items-center justify-between gap-8 pb-8 border-b border-slate-800/80">
        
        <!-- Brand Info -->
        <div class="max-w-sm">
          <a href="#" class="flex items-center gap-2.5">
            <span class="font-display font-bold text-xl text-white">CGVerse <span class="text-cyan-400">Academy</span></span>
          </a>
          <p class="mt-2.5 text-sm text-slate-400 leading-relaxed">
            Empowering art enthusiasts to become studio-ready 3D Game Artists & Digital Sculptors through live mentorship and job-focused training.
          </p>
        </div>

        <!-- Quick Links -->
        <div class="flex flex-wrap gap-6 text-sm font-medium text-slate-300">
          <a href="#about" class="hover:text-cyan-400 transition-colors">About</a>
          <a href="#courses" class="hover:text-cyan-400 transition-colors">Courses</a>
          <a href="#why-us" class="hover:text-cyan-400 transition-colors">Why Us</a>
          <a href="#consultation" class="hover:text-cyan-400 transition-colors">Book Consultation</a>
        </div>

        <!-- Contact Info -->
        <div class="text-sm text-slate-400 space-y-1">
          <p class="text-white font-semibold">Admissions & Mentorship Desk</p>
          <p>Email: <a href="mailto:admissions@cgverseacademy.com" class="text-cyan-400 hover:underline">admissions@cgverseacademy.com</a></p>
          <p>Live Online Classes • Worldwide Access</p>
        </div>
      </div>

      <div class="pt-8 flex flex-col sm:flex-row items-center justify-between gap-4 text-xs text-slate-500">
        <p>© <span id="current-year"></span> CGVerse Academy. All rights reserved.</p>
        <p>Built for aspiring 3D Game Artists & Digital Sculptors.</p>
      </div>
    </div>
  </footer>

  <!-- ==================== INTERACTIVE JAVASCRIPT ==================== -->
  <script>
    // Set current copyright year dynamically
    document.getElementById('current-year').textContent = new Date().getFullYear();

    // Mobile Navigation Menu Toggle
    const mobileMenuBtn = document.getElementById('mobile-menu-btn');
    const mobileMenu = document.getElementById('mobile-menu');

    mobileMenuBtn.addEventListener('click', () => {
      mobileMenu.classList.toggle('hidden');
    });

    // Close mobile menu when clicking a navigation link
    mobileMenu.querySelectorAll('a').forEach(link => {
      link.addEventListener('click', () => {
        mobileMenu.classList.add('hidden');
      });
    });

    // Pre-select track from Course Cards and smoothly scroll to Consultation Form
    function selectTrackAndScroll(trackValue) {
      const trackSelect = document.getElementById('track');
      if (trackSelect) {
        trackSelect.value = trackValue;
      }
      const consultationSection = document.getElementById('consultation');
      if (consultationSection) {
        consultationSection.scrollIntoView({ behavior: 'smooth' });
      }
    }

    // Client-side Form Handling with Instant Feedback
    const form = document.getElementById('consultation-form');
    const formError = document.getElementById('form-error');
    const formSuccess = document.getElementById('form-success');
    const successMessage = document.getElementById('success-message');

    form.addEventListener('submit', function (e) {
      e.preventDefault();

      const fullName = document.getElementById('fullName').value.trim();
      const email = document.getElementById('email').value.trim();
      const phone = document.getElementById('phone').value.trim();
      const track = document.getElementById('track').value;

      // Basic email regex check
      const emailValid = /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email);

      if (!fullName || !emailValid || !phone) {
        formError.classList.remove('hidden');
        return;
      }

      formError.classList.add('hidden');

      // Personalize confirmation feedback
      successMessage.innerHTML = `
        Thank you, <strong class="text-white">${escapeHTML(fullName)}</strong>! We have registered your interest for the <strong class="text-cyan-400">${escapeHTML(track)}</strong>. One of our industry mentors will reach out to <strong class="text-white">${escapeHTML(phone)}</strong> shortly for your free 1-on-1 consultation.
      `;

      form.classList.add('hidden');
      formSuccess.classList.remove('hidden');
    });

    function resetConsultationForm() {
      form.reset();
      formSuccess.classList.add('hidden');
      form.classList.remove('hidden');
    }

    // Utility to prevent XSS in dynamic confirmation message
    function escapeHTML(str) {
      return str.replace(/[&<>'"]/g, tag => ({
        '&': '&amp;',
        '<': '&lt;',
        '>': '&gt;',
        "'": '&#39;',
        '"': '&quot;'
      }[tag]));
    }
  </script>
</body>
</html>
