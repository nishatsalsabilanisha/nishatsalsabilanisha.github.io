<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nishat Salsabil Anisha - Developer Portfolio</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=JetBrains+Mono:wght@400;500;600&display=swap');
        
        body { 
            font-family: 'Space Grotesk', sans-serif; 
            background: #0a0a0a;
            color: #ffffff;
        }
        
        .code-font { font-family: 'JetBrains Mono', monospace; }
        
        .neon-glow {
            box-shadow: 0 0 20px rgba(34, 197, 94, 0.3);
            border: 1px solid rgba(34, 197, 94, 0.5);
        }
        
        .neon-text {
            text-shadow: 0 0 10px rgba(34, 197, 94, 0.8);
        }
        
        .glass-effect {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .terminal-window {
            background: #1a1a1a;
            border: 1px solid #333;
            border-radius: 8px;
        }
        
        .terminal-header {
            background: #2a2a2a;
            padding: 8px 16px;
            border-bottom: 1px solid #333;
            border-radius: 8px 8px 0 0;
        }
        
        .dot { 
            width: 12px; 
            height: 12px; 
            border-radius: 50%; 
            display: inline-block; 
            margin-right: 8px; 
        }
        
        .dot-red { background: #ff5f56; }
        .dot-yellow { background: #ffbd2e; }
        .dot-green { background: #27ca3f; }
        
        .typing-animation {
            overflow: hidden;
            border-right: 2px solid #22c55e;
            white-space: nowrap;
            animation: typing 3s steps(40, end), blink-caret 0.75s step-end infinite;
        }
        
        @keyframes typing {
            from { width: 0; }
            to { width: 100%; }
        }
        
        @keyframes blink-caret {
            from, to { border-color: transparent; }
            50% { border-color: #22c55e; }
        }
        
        .floating-card {
            transform: translateY(0);
            transition: all 0.3s ease;
        }
        
        .floating-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(34, 197, 94, 0.2);
        }
        
        .skill-progress {
            background: linear-gradient(90deg, #22c55e, #16a34a);
            height: 4px;
            border-radius: 2px;
            transition: width 2s ease-in-out;
        }
        
        .matrix-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
            opacity: 0.1;
        }
        
        .hexagon {
            width: 60px;
            height: 34.64px;
            background: rgba(34, 197, 94, 0.2);
            margin: 17.32px 0;
            position: relative;
        }
        
        .hexagon:before,
        .hexagon:after {
            content: "";
            position: absolute;
            width: 0;
            border-left: 30px solid transparent;
            border-right: 30px solid transparent;
        }
        
        .hexagon:before {
            bottom: 100%;
            border-bottom: 17.32px solid rgba(34, 197, 94, 0.2);
        }
        
        .hexagon:after {
            top: 100%;
            border-top: 17.32px solid rgba(34, 197, 94, 0.2);
        }
    </style>
</head>
<body class="bg-black text-white overflow-x-hidden">
    <!-- Matrix Background -->
    <canvas class="matrix-bg" id="matrix"></canvas>

    <!-- Sidebar Navigation -->
    <nav class="fixed left-0 top-0 h-full w-20 bg-gray-900 border-r border-gray-800 z-50 flex flex-col items-center py-8">
        <div class="mb-8">
            <div class="w-12 h-12 bg-green-500 rounded-lg flex items-center justify-center neon-glow">
                <span class="text-black font-bold text-xl">N</span>
            </div>
        </div>
        <div class="flex flex-col space-y-6">
            <a href="#home" class="nav-link w-12 h-12 flex items-center justify-center rounded-lg hover:bg-green-500 hover:text-black transition-all duration-300 group">
                <i class="fas fa-home text-lg"></i>
                <span class="absolute left-20 bg-gray-800 text-white px-2 py-1 rounded text-sm opacity-0 group-hover:opacity-100 transition-opacity duration-300">Home</span>
            </a>
            <a href="#about" class="nav-link w-12 h-12 flex items-center justify-center rounded-lg hover:bg-green-500 hover:text-black transition-all duration-300 group">
                <i class="fas fa-user text-lg"></i>
                <span class="absolute left-20 bg-gray-800 text-white px-2 py-1 rounded text-sm opacity-0 group-hover:opacity-100 transition-opacity duration-300">About</span>
            </a>
            <a href="#skills" class="nav-link w-12 h-12 flex items-center justify-center rounded-lg hover:bg-green-500 hover:text-black transition-all duration-300 group">
                <i class="fas fa-code text-lg"></i>
                <span class="absolute left-20 bg-gray-800 text-white px-2 py-1 rounded text-sm opacity-0 group-hover:opacity-100 transition-opacity duration-300">Skills</span>
            </a>
            <a href="#projects" class="nav-link w-12 h-12 flex items-center justify-center rounded-lg hover:bg-green-500 hover:text-black transition-all duration-300 group">
                <i class="fas fa-folder text-lg"></i>
                <span class="absolute left-20 bg-gray-800 text-white px-2 py-1 rounded text-sm opacity-0 group-hover:opacity-100 transition-opacity duration-300">Projects</span>
            </a>
            <a href="#contact" class="nav-link w-12 h-12 flex items-center justify-center rounded-lg hover:bg-green-500 hover:text-black transition-all duration-300 group">
                <i class="fas fa-envelope text-lg"></i>
                <span class="absolute left-20 bg-gray-800 text-white px-2 py-1 rounded text-sm opacity-0 group-hover:opacity-100 transition-opacity duration-300">Contact</span>
            </a>
        </div>
    </nav>

    <!-- Main Content -->
    <main class="ml-20">
        <!-- Hero Section -->
        <section id="home" class="min-h-screen flex items-center justify-center relative">
            <div class="container mx-auto px-8 grid lg:grid-cols-2 gap-12 items-center">
                <div>
                    <div class="terminal-window mb-8">
                        <div class="terminal-header">
                            <span class="dot dot-red"></span>
                            <span class="dot dot-yellow"></span>
                            <span class="dot dot-green"></span>
                            <span class="code-font text-sm text-gray-400 ml-4">nishat@portfolio:~$</span>
                        </div>
                        <div class="p-6 code-font text-sm">
                            <div class="text-green-400 mb-2">$ whoami</div>
                            <div class="text-white mb-4">Nishat Salsabil Anisha</div>
                            <div class="text-green-400 mb-2">$ cat skills.txt</div>
                            <div class="text-white mb-4">Python | C++ | JavaScript | Data Analysis</div>
                            <div class="text-green-400 mb-2">$ echo $EDUCATION</div>
                            <div class="text-white mb-4">CSE Student @ IUBAT | CGPA: 3.97/4.00</div>
                            <div class="text-green-400 mb-2">$ status</div>
                            <div class="text-white typing-animation">Ready for new opportunities...</div>
                        </div>
                    </div>
                    <div class="space-y-4">
                        <h1 class="text-5xl font-bold neon-text">
                            Hi, I'm <span class="text-green-400">Nishat</span>
                        </h1>
                        <p class="text-xl text-gray-300">
                            Computer Science Engineer & Data Enthusiast
                        </p>
                        <p class="text-gray-400 leading-relaxed">
                            Passionate about creating innovative solutions through code. 
                            Currently building the future with Python, IoT, and data analysis.
                        </p>
                        <div class="flex space-x-4 pt-4">
                            <button onclick="scrollToSection('projects')" class="bg-green-500 text-black px-6 py-3 rounded-lg font-semibold hover:bg-green-400 transition-colors duration-300 neon-glow">
                                View Projects
                            </button>
                            <button onclick="scrollToSection('contact')" class="border border-green-500 text-green-500 px-6 py-3 rounded-lg font-semibold hover:bg-green-500 hover:text-black transition-all duration-300">
                                Get In Touch
                            </button>
                        </div>
                    </div>
                </div>
                <div class="relative">
                    <div class="glass-effect rounded-2xl p-8 floating-card">
                        <div class="text-center">
                            <div class="w-32 h-32 bg-gradient-to-br from-green-400 to-green-600 rounded-full mx-auto mb-6 flex items-center justify-center text-4xl font-bold text-black">
                                NA
                            </div>
                            <div class="space-y-2">
                                <div class="flex justify-between items-center">
                                    <span class="text-gray-400">Location:</span>
                                    <span class="text-green-400">Dhaka, Bangladesh</span>
                                </div>
                                <div class="flex justify-between items-center">
                                    <span class="text-gray-400">Age:</span>
                                    <span class="text-green-400">21 years</span>
                                </div>
                                <div class="flex justify-between items-center">
                                    <span class="text-gray-400">Status:</span>
                                    <span class="text-green-400 flex items-center">
                                        <span class="w-2 h-2 bg-green-400 rounded-full mr-2 animate-pulse"></span>
                                        Available
                                    </span>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- About Section -->
        <section id="about" class="py-20">
            <div class="container mx-auto px-8">
                <div class="text-center mb-16">
                    <h2 class="text-4xl font-bold mb-4">
                        <span class="text-green-400 code-font">&lt;</span>
                        About Me
                        <span class="text-green-400 code-font">/&gt;</span>
                    </h2>
                    <div class="w-20 h-1 bg-green-500 mx-auto"></div>
                </div>
                
                <div class="grid lg:grid-cols-3 gap-8">
                    <div class="lg:col-span-2">
                        <div class="glass-effect rounded-2xl p-8 floating-card">
                            <h3 class="text-2xl font-semibold mb-6 text-green-400">Professional Summary</h3>
                            <p class="text-gray-300 leading-relaxed mb-6">
                                Dynamic professional with experience at Youth Skill Development Institute Trust, where I successfully organized and managed the annual budgeting process. Proficient in Python and data analysis, I excel in leveraging technical skills to drive impactful results while fostering collaboration and innovation in team environments.
                            </p>
                            
                            <div class="grid md:grid-cols-2 gap-8">
                                <div>
                                    <h4 class="text-lg font-semibold text-green-400 mb-4">Education Journey</h4>
                                    <div class="space-y-4">
                                        <div class="border-l-2 border-green-500 pl-4">
                                            <h5 class="font-semibold">BSc Computer Science & Engineering</h5>
                                            <p class="text-sm text-gray-400">IUBAT University (2022-Present)</p>
                                            <p class="text-sm text-green-400">CGPA: 3.97/4.00</p>
                                        </div>
                                        <div class="border-l-2 border-gray-600 pl-4">
                                            <h5 class="font-semibold">HSC - Science</h5>
                                            <p class="text-sm text-gray-400">Stamford College (2021)</p>
                                            <p class="text-sm text-green-400">GPA: 5.00/5.00</p>
                                        </div>
                                        <div class="border-l-2 border-gray-600 pl-4">
                                            <h5 class="font-semibold">SSC - Science</h5>
                                            <p class="text-sm text-gray-400">Stamford School (2019)</p>
                                            <p class="text-sm text-green-400">GPA: 4.06/5.00</p>
                                        </div>
                                    </div>
                                </div>
                                
                                <div>
                                    <h4 class="text-lg font-semibold text-green-400 mb-4">Experience</h4>
                                    <div class="space-y-4">
                                        <div class="border-l-2 border-green-500 pl-4">
                                            <h5 class="font-semibold">Executive Member</h5>
                                            <p class="text-sm text-gray-400">Youth Skill Development Institute Trust</p>
                                        </div>
                                        <div class="border-l-2 border-gray-600 pl-4">
                                            <h5 class="font-semibold">General Member</h5>
                                            <p class="text-sm text-gray-400">IIEC - IUBAT Innovation Center</p>
                                        </div>
                                    </div>
                                    
                                    <h4 class="text-lg font-semibold text-green-400 mb-4 mt-8">Languages</h4>
                                    <div class="space-y-2">
                                        <div class="flex justify-between">
                                            <span>Bangla</span>
                                            <span class="text-green-400">Native</span>
                                        </div>
                                        <div class="flex justify-between">
                                            <span>English</span>
                                            <span class="text-green-400">Fluent</span>
                                        </div>
                                        <div class="flex justify-between">
                                            <span>German</span>
                                            <span class="text-green-400">Learning</span>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                    
                    <div class="space-y-6">
                        <div class="glass-effect rounded-2xl p-6 floating-card">
                            <h4 class="text-lg font-semibold text-green-400 mb-4">Interests & Hobbies</h4>
                            <div class="space-y-3">
                                <div class="flex items-center">
                                    <i class="fas fa-fist-raised text-green-400 mr-3"></i>
                                    <span>Judo</span>
                                </div>
                                <div class="flex items-center">
                                    <i class="fas fa-hand-rock text-green-400 mr-3"></i>
                                    <span>Karate</span>
                                </div>
                                <div class="flex items-center">
                                    <i class="fas fa-laptop-code text-green-400 mr-3"></i>
                                    <span>Technology</span>
                                </div>
                            </div>
                        </div>
                        
                        <div class="glass-effect rounded-2xl p-6 floating-card">
                            <h4 class="text-lg font-semibold text-green-400 mb-4">Certifications</h4>
                            <div class="space-y-3">
                                <div class="flex items-start">
                                    <i class="fas fa-certificate text-green-400 mr-3 mt-1"></i>
                                    <div>
                                        <p class="font-semibold">Arduino Training</p>
                                        <p class="text-sm text-gray-400">2 months - Prestigious Certificate</p>
                                    </div>
                                </div>
                                <div class="flex items-start">
                                    <i class="fas fa-certificate text-green-400 mr-3 mt-1"></i>
                                    <div>
                                        <p class="font-semibold">Youth Development</p>
                                        <p class="text-sm text-gray-400">Leadership Training</p>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Skills Section -->
        <section id="skills" class="py-20 bg-gray-900">
            <div class="container mx-auto px-8">
                <div class="text-center mb-16">
                    <h2 class="text-4xl font-bold mb-4">
                        <span class="text-green-400 code-font">&lt;</span>
                        Technical Arsenal
                        <span class="text-green-400 code-font">/&gt;</span>
                    </h2>
                    <div class="w-20 h-1 bg-green-500 mx-auto"></div>
                </div>
                
                <div class="grid lg:grid-cols-2 gap-12">
                    <div>
                        <h3 class="text-2xl font-semibold mb-8 text-green-400">Programming Languages</h3>
                        <div class="space-y-6">
                            <div class="skill-item">
                                <div class="flex justify-between mb-2">
                                    <span class="flex items-center">
                                        <i class="fab fa-python text-2xl text-blue-400 mr-3"></i>
                                        Python
                                    </span>
                                    <span class="text-green-400 code-font">90%</span>
                                </div>
                                <div class="w-full bg-gray-700 rounded-full h-2">
                                    <div class="skill-progress rounded-full" style="width: 90%"></div>
                                </div>
                            </div>
                            
                            <div class="skill-item">
                                <div class="flex justify-between mb-2">
                                    <span class="flex items-center">
                                        <i class="fab fa-cuttlefish text-2xl text-blue-600 mr-3"></i>
                                        C++
                                    </span>
                                    <span class="text-green-400 code-font">85%</span>
                                </div>
                                <div class="w-full bg-gray-700 rounded-full h-2">
                                    <div class="skill-progress rounded-full" style="width: 85%"></div>
                                </div>
                            </div>
                            
                            <div class="skill-item">
                                <div class="flex justify-between mb-2">
                                    <span class="flex items-center">
                                        <i class="fab fa-js-square text-2xl text-yellow-400 mr-3"></i>
                                        JavaScript
                                    </span>
                                    <span class="text-green-400 code-font">80%</span>
                                </div>
                                <div class="w-full bg-gray-700 rounded-full h-2">
                                    <div class="skill-progress rounded-full" style="width: 80%"></div>
                                </div>
                            </div>
                        </div>
                        
                        <h3 class="text-2xl font-semibold mb-8 mt-12 text-green-400">Web Technologies</h3>
                        <div class="space-y-6">
                            <div class="skill-item">
                                <div class="flex justify-between mb-2">
                                    <span class="flex items-center">
                                        <i class="fab fa-html5 text-2xl text-orange-500 mr-3"></i>
                                        HTML5
                                    </span>
                                    <span class="text-green-400 code-font">88%</span>
                                </div>
                                <div class="w-full bg-gray-700 rounded-full h-2">
                                    <div class="skill-progress rounded-full" style="width: 88%"></div>
                                </div>
                            </div>
                            
                            <div class="skill-item">
                                <div class="flex justify-between mb-2">
                                    <span class="flex items-center">
                                        <i class="fab fa-css3-alt text-2xl text-blue-500 mr-3"></i>
                                        CSS
                                    </span>
                                    <span class="text-green-400 code-font">85%</span>
                                </div>
                                <div class="w-full bg-gray-700 rounded-full h-2">
                                    <div class="skill-progress rounded-full" style="width: 85%"></div>
                                </div>
                            </div>
                        </div>
                    </div>
                    
                    <div>
                        <h3 class="text-2xl font-semibold mb-8 text-green-400">Specialized Skills</h3>
                        <div class="grid grid-cols-2 gap-6">
                            <div class="glass-effect rounded-xl p-6 text-center floating-card">
                                <i class="fas fa-chart-line text-3xl text-green-400 mb-4"></i>
                                <h4 class="font-semibold mb-2">Data Analysis</h4>
                                <p class="text-sm text-gray-400">Advanced</p>
                            </div>
                            
                            <div class="glass-effect rounded-xl p-6 text-center floating-card">
                                <i class="fas fa-microchip text-3xl text-green-400 mb-4"></i>
                                <h4 class="font-semibold mb-2">Arduino/IoT</h4>
                                <p class="text-sm text-gray-400">Intermediate</p>
                            </div>
                            
                            <div class="glass-effect rounded-xl p-6 text-center floating-card">
                                <i class="fas fa-database text-3xl text-green-400 mb-4"></i>
                                <h4 class="font-semibold mb-2">Database</h4>
                                <p class="text-sm text-gray-400">Intermediate</p>
                            </div>
                            
                            <div class="glass-effect rounded-xl p-6 text-center floating-card">
                                <i class="fas fa-project-diagram text-3xl text-green-400 mb-4"></i>
                                <h4 class="font-semibold mb-2">System Design</h4>
                                <p class="text-sm text-gray-400">Intermediate</p>
                            </div>
                        </div>
                        
                        <div class="mt-12">
                            <h3 class="text-2xl font-semibold mb-8 text-green-400">Development Tools</h3>
                            <div class="flex flex-wrap gap-3">
                                <span class="bg-gray-800 border border-green-500 px-4 py-2 rounded-full text-sm">Git</span>
                                <span class="bg-gray-800 border border-green-500 px-4 py-2 rounded-full text-sm">VS Code</span>
                                <span class="bg-gray-800 border border-green-500 px-4 py-2 rounded-full text-sm">Arduino IDE</span>
                                <span class="bg-gray-800 border border-green-500 px-4 py-2 rounded-full text-sm">Jupyter</span>
                                <span class="bg-gray-800 border border-green-500 px-4 py-2 rounded-full text-sm">MySQL</span>
                                <span class="bg-gray-800 border border-green-500 px-4 py-2 rounded-full text-sm">Linux</span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Projects Section -->
        <section id="projects" class="py-20">
            <div class="container mx-auto px-8">
                <div class="text-center mb-16">
                    <h2 class="text-4xl font-bold mb-4">
                        <span class="text-green-400 code-font">&lt;</span>
                        Featured Projects
                        <span class="text-green-400 code-font">/&gt;</span>
                    </h2>
                    <div class="w-20 h-1 bg-green-500 mx-auto"></div>
                </div>
                
                <div class="grid lg:grid-cols-2 gap-8">
                    <div class="glass-effect rounded-2xl overflow-hidden floating-card">
                        <div class="p-8">
                            <div class="flex items-center mb-6">
                                <div class="w-12 h-12 bg-green-500 rounded-lg flex items-center justify-center mr-4">
                                    <i class="fas fa-hotel text-black text-xl"></i>
                                </div>
                                <div>
                                    <h3 class="text-xl font-semibold">Hotel Management System</h3>
                                    <p class="text-sm text-gray-400 code-font">Full-Stack Application</p>
                                </div>
                            </div>
                            
                            <p class="text-gray-300 mb-6 leading-relaxed">
                                A comprehensive hotel management system built to handle reservations, customer management, and administrative tasks efficiently. Features include booking management, customer database, and reporting system.
                            </p>
                            
                            <div class="mb-6">
                                <h4 class="text-sm font-semibold text-green-400 mb-3">Tech Stack:</h4>
                                <div class="flex flex-wrap gap-2">
                                    <span class="bg-blue-900 text-blue-300 px-3 py-1 rounded-full text-xs">Python</span>
                                    <span class="bg-green-900 text-green-300 px-3 py-1 rounded-full text-xs">Database</span>
                                    <span class="bg-purple-900 text-purple-300 px-3 py-1 rounded-full text-xs">GUI</span>
                                    <span class="bg-orange-900 text-orange-300 px-3 py-1 rounded-full text-xs">Management</span>
                                </div>
                            </div>
                            
                            <div class="flex space-x-4">
                                <a href="https://github.com/nishatsalsabilanisha/Hotel-Management-System" target="_blank" class="flex items-center bg-green-500 text-black px-4 py-2 rounded-lg font-semibold hover:bg-green-400 transition-colors duration-300">
                                    <i class="fab fa-github mr-2"></i>
                                    View Code
                                </a>
                                <button class="flex items-center border border-green-500 text-green-500 px-4 py-2 rounded-lg font-semibold hover:bg-green-500 hover:text-black transition-all duration-300">
                                    <i class="fas fa-external-link-alt mr-2"></i>
                                    Live Demo
                                </button>
                            </div>
                        </div>
                    </div>
                    
                    <div class="glass-effect rounded-2xl overflow-hidden floating-card">
                        <div class="p-8">
                            <div class="flex items-center mb-6">
                                <div class="w-12 h-12 bg-red-500 rounded-lg flex items-center justify-center mr-4">
                                    <i class="fas fa-heartbeat text-white text-xl"></i>
                                </div>
                                <div>
                                    <h3 class="text-xl font-semibold">IoT Health Monitoring</h3>
                                    <p class="text-sm text-gray-400 code-font">Hardware + Software</p>
                                </div>
                            </div>
                            
                            <p class="text-gray-300 mb-6 leading-relaxed">
                                Affordable and customer-friendly paralysis patient healthcare monitoring system based on IoT technology. Uses Arduino sensors to monitor vital signs and send real-time data to healthcare providers.
                            </p>
                            
                            <div class="mb-6">
                                <h4 class="text-sm font-semibold text-green-400 mb-3">Tech Stack:</h4>
                                <div class="flex flex-wrap gap-2">
                                    <span class="bg-red-900 text-red-300 px-3 py-1 rounded-full text-xs">Arduino</span>
                                    <span class="bg-blue-900 text-blue-300 px-3 py-1 rounded-full text-xs">IoT</span>
                                    <span class="bg-green-900 text-green-300 px-3 py-1 rounded-full text-xs">Sensors</span>
                                    <span class="bg-yellow-900 text-yellow-300 px-3 py-1 rounded-full text-xs">Healthcare</span>
                                </div>
                            </div>
                            
                            <div class="flex space-x-4">
                                <button class="flex items-center bg-gray-700 text-gray-300 px-4 py-2 rounded-lg font-semibold cursor-not-allowed">
                                    <i class="fas fa-lock mr-2"></i>
                                    Private Repo
                                </button>
                                <button onclick="scrollToSection('contact')" class="flex items-center border border-green-500 text-green-500 px-4 py-2 rounded-lg font-semibold hover:bg-green-500 hover:text-black transition-all duration-300">
                                    <i class="fas fa-envelope mr-2"></i>
                                    Contact for Details
                                </button>
                            </div>
                        </div>
                    </div>
                </div>
                
                <div class="text-center mt-12">
                    <p class="text-gray-400 mb-4">More projects coming soon...</p>
                    <a href="https://github.com/nishatsalsabilanisha" target="_blank" class="inline-flex items-center text-green-400 hover:text-green-300 transition-colors duration-300">
                        <i class="fab fa-github mr-2"></i>
                        View All Repositories
                        <i class="fas fa-external-link-alt ml-2 text-sm"></i>
                    </a>
                </div>
            </div>
        </section>

        <!-- Contact Section -->
        <section id="contact" class="py-20 bg-gray-900">
            <div class="container mx-auto px-8">
                <div class="text-center mb-16">
                    <h2 class="text-4xl font-bold mb-4">
                        <span class="text-green-400 code-font">&lt;</span>
                        Let's Connect
                        <span class="text-green-400 code-font">/&gt;</span>
                    </h2>
                    <div class="w-20 h-1 bg-green-500 mx-auto"></div>
                    <p class="text-gray-400 mt-4 max-w-2xl mx-auto">
                        Ready to collaborate on exciting projects or discuss opportunities? 
                        Let's build something amazing together!
                    </p>
                </div>
                
                <div class="grid lg:grid-cols-2 gap-12">
                    <div>
                        <div class="terminal-window">
                            <div class="terminal-header">
                                <span class="dot dot-red"></span>
                                <span class="dot dot-yellow"></span>
                                <span class="dot dot-green"></span>
                                <span class="code-font text-sm text-gray-400 ml-4">contact-info.json</span>
                            </div>
                            <div class="p-6 code-font text-sm">
                                <div class="text-white">
                                    <span class="text-blue-400">{</span><br>
                                    &nbsp;&nbsp;<span class="text-green-400">"name"</span>: <span class="text-yellow-400">"Nishat Salsabil Anisha"</span>,<br>
                                    &nbsp;&nbsp;<span class="text-green-400">"email"</span>: <span class="text-yellow-400">"nishatsalsabilanisha@gmail.com"</span>,<br>
                                    &nbsp;&nbsp;<span class="text-green-400">"phone"</span>: <span class="text-yellow-400">"+880 1771407297"</span>,<br>
                                    &nbsp;&nbsp;<span class="text-green-400">"location"</span>: <span class="text-yellow-400">"Dhaka, Bangladesh"</span>,<br>
                                    &nbsp;&nbsp;<span class="text-green-400">"address"</span>: <span class="text-yellow-400">"258/3 Sultanganj Road, Rayer Bazar"</span>,<br>
                                    &nbsp;&nbsp;<span class="text-green-400">"postal_code"</span>: <span class="text-yellow-400">"1209"</span>,<br>
                                    &nbsp;&nbsp;<span class="text-green-400">"availability"</span>: <span class="text-green-300">true</span>,<br>
                                    &nbsp;&nbsp;<span class="text-green-400">"response_time"</span>: <span class="text-yellow-400">"24 hours"</span><br>
                                    <span class="text-blue-400">}</span>
                                </div>
                            </div>
                        </div>
                        
                        <div class="mt-8 space-y-4">
                            <a href="mailto:nishatsalsabilanisha@gmail.com" class="flex items-center p-4 glass-effect rounded-lg hover:bg-green-500 hover:text-black transition-all duration-300 group">
                                <i class="fas fa-envelope text-2xl mr-4 text-green-400 group-hover:text-black"></i>
                                <div>
                                    <p class="font-semibold">Email</p>
                                    <p class="text-sm text-gray-400 group-hover:text-black">nishatsalsabilanisha@gmail.com</p>
                                </div>
                            </a>
                            
                            <a href="tel:+8801771407297" class="flex items-center p-4 glass-effect rounded-lg hover:bg-green-500 hover:text-black transition-all duration-300 group">
                                <i class="fas fa-phone text-2xl mr-4 text-green-400 group-hover:text-black"></i>
                                <div>
                                    <p class="font-semibold">Phone</p>
                                    <p class="text-sm text-gray-400 group-hover:text-black">+880 1771407297</p>
                                </div>
                            </a>
                            
                            <div class="flex space-x-4 pt-4">
                                <a href="https://www.linkedin.com/in/nishat-salsabil-bb71182b4?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=android_app" target="_blank" class="w-12 h-12 bg-blue-600 rounded-lg flex items-center justify-center hover:bg-blue-500 transition-colors duration-300">
                                    <i class="fab fa-linkedin text-white text-xl"></i>
                                </a>
                                <a href="https://github.com/nishatsalsabilanisha" target="_blank" class="w-12 h-12 bg-gray-700 rounded-lg flex items-center justify-center hover:bg-gray-600 transition-colors duration-300">
                                    <i class="fab fa-github text-white text-xl"></i>
                                </a>
                            </div>
                        </div>
                    </div>
                    
                    <div class="glass-effect rounded-2xl p-8">
                        <h3 class="text-2xl font-semibold mb-6 text-green-400">Send Message</h3>
                        <form class="space-y-6" onsubmit="handleFormSubmit(event)">
                            <div class="grid md:grid-cols-2 gap-4">
                                <div>
                                    <label class="block text-sm font-semibold text-gray-300 mb-2">Name</label>
                                    <input type="text" required class="w-full bg-gray-800 border border-gray-600 rounded-lg px-4 py-3 text-white focus:border-green-500 focus:outline-none transition-colors duration-300">
                                </div>
                                <div>
                                    <label class="block text-sm font-semibold text-gray-300 mb-2">Email</label>
                                    <input type="email" required class="w-full bg-gray-800 border border-gray-600 rounded-lg px-4 py-3 text-white focus:border-green-500 focus:outline-none transition-colors duration-300">
                                </div>
                            </div>
                            <div>
                                <label class="block text-sm font-semibold text-gray-300 mb-2">Subject</label>
                                <input type="text" required class="w-full bg-gray-800 border border-gray-600 rounded-lg px-4 py-3 text-white focus:border-green-500 focus:outline-none transition-colors duration-300">
                            </div>
                            <div>
                                <label class="block text-sm font-semibold text-gray-300 mb-2">Message</label>
                                <textarea rows="5" required class="w-full bg-gray-800 border border-gray-600 rounded-lg px-4 py-3 text-white focus:border-green-500 focus:outline-none transition-colors duration-300 resize-none"></textarea>
                            </div>
                            <button type="submit" class="w-full bg-green-500 text-black py-3 rounded-lg font-semibold hover:bg-green-400 transition-colors duration-300 neon-glow">
                                <i class="fas fa-paper-plane mr-2"></i>
                                Send Message
                            </button>
                        </form>
                        <div class="mt-4 text-center">
                            <p class="text-gray-400 text-sm">
                                <i class="fas fa-info-circle mr-1"></i>
                                Demo form - Please use contact information above for direct communication
                            </p>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <!-- Footer -->
    <footer class="bg-black border-t border-gray-800 py-8 ml-20">
        <div class="container mx-auto px-8 text-center">
            <div class="flex justify-center items-center space-x-4 mb-4">
                <span class="code-font text-green-400">&lt;/&gt;</span>
                <p class="text-gray-400">Built with passion by Nishat Salsabil Anisha</p>
                <span class="code-font text-green-400">&lt;/&gt;</span>
            </div>
            <p class="text-gray-500 text-sm">&copy; 2024 All rights reserved. Made with ❤️ and lots of ☕</p>
        </div>
    </footer>

    <script>
        // Matrix rain effect
        const canvas = document.getElementById('matrix');
        const ctx = canvas.getContext('2d');

        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;

        const matrix = "ABCDEFGHIJKLMNOPQRSTUVWXYZ123456789@#$%^&*()*&^%+-/~{[|`]}";
        const matrixArray = matrix.split("");

        const fontSize = 10;
        const columns = canvas.width / fontSize;

        const drops = [];
        for(let x = 0; x < columns; x++) {
            drops[x] = 1;
        }

        function drawMatrix() {
            ctx.fillStyle = 'rgba(0, 0, 0, 0.04)';
            ctx.fillRect(0, 0, canvas.width, canvas.height);
            
            ctx.fillStyle = '#22c55e';
            ctx.font = fontSize + 'px monospace';

            for(let i = 0; i < drops.length; i++) {
                const text = matrixArray[Math.floor(Math.random() * matrixArray.length)];
                ctx.fillText(text, i * fontSize, drops[i] * fontSize);
                
                if(drops[i] * fontSize > canvas.height && Math.random() > 0.975) {
                    drops[i] = 0;
                }
                drops[i]++;
            }
        }

        setInterval(drawMatrix, 35);

        // Smooth scrolling
        function scrollToSection(sectionId) {
            document.getElementById(sectionId).scrollIntoView({
                behavior: 'smooth'
            });
        }

        // Navigation links
        document.querySelectorAll('.nav-link').forEach(link => {
            link.addEventListener('click', function(e) {
                e.preventDefault();
                const targetId = this.getAttribute('href').substring(1);
                scrollToSection(targetId);
            });
        });

        // Skill bar animation
        const observerOptions = {
            threshold: 0.5,
            rootMargin: '0px 0px -100px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    const skillBars = entry.target.querySelectorAll('.skill-progress');
                    skillBars.forEach(bar => {
                        const width = bar.style.width;
                        bar.style.width = '0%';
                        setTimeout(() => {
                            bar.style.width = width;
                        }, 200);
                    });
                }
            });
        }, observerOptions);

        const skillsSection = document.getElementById('skills');
        if (skillsSection) {
            observer.observe(skillsSection);
        }

        // Form submission
        function handleFormSubmit(event) {
            event.preventDefault();
            alert('Thank you for your message! This is a demo form. Please use the contact information provided to reach out directly.');
        }

        // Active navigation highlighting
        window.addEventListener('scroll', () => {
            const sections = document.querySelectorAll('section[id]');
            const navLinks = document.querySelectorAll('.nav-link');
            
            let current = '';
            sections.forEach(section => {
                const sectionTop = section.offsetTop;
                if (scrollY >= (sectionTop - 200)) {
                    current = section.getAttribute('id');
                }
            });

            navLinks.forEach(link => {
                link.classList.remove('bg-green-500', 'text-black');
                if (link.getAttribute('href') === `#${current}`) {
                    link.classList.add('bg-green-500', 'text-black');
                }
            });
        });

        // Resize canvas on window resize
        window.addEventListener('resize', () => {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
        });
    </script>
<script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'96b965b4d2d37e63',t:'MTc1NDU5NzIxNS4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
