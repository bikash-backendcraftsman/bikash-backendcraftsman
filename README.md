<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GitHub Profile Preview</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Noto Sans', Helvetica, Arial, sans-serif;
            background: #0d1117;
            color: #c9d1d9;
            padding: 20px;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            background: #161b22;
            border-radius: 6px;
            padding: 40px;
            box-shadow: 0 8px 24px rgba(0,0,0,0.4);
        }

        .header {
            text-align: center;
            margin-bottom: 40px;
        }

        .header h1 {
            font-size: 2.5em;
            margin-bottom: 20px;
            background: linear-gradient(135deg, #2e9ef7 0%, #9b59b6 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .typing-animation {
            font-size: 1.8em;
            color: #2e9ef7;
            margin: 20px 0;
            font-weight: 600;
            height: 50px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 15px;
            flex-wrap: wrap;
            margin-top: 20px;
        }

        .badge {
            display: inline-block;
            padding: 8px 16px;
            border-radius: 6px;
            text-decoration: none;
            font-weight: 600;
            font-size: 14px;
            transition: transform 0.2s, box-shadow 0.2s;
        }

        .badge:hover {
            transform: translateY(-2px);
            box-shadow: 0 4px 12px rgba(46, 158, 247, 0.4);
        }

        .linkedin { background: #0077B5; color: white; }
        .devto { background: #0A0A0A; color: white; }
        .medium { background: #12100E; color: white; }
        .portfolio { background: #FF5722; color: white; }
        .email { background: #D14836; color: white; }

        .about {
            background: #21262d;
            padding: 25px;
            border-radius: 8px;
            margin: 30px 0;
            border-left: 4px solid #2e9ef7;
        }

        .about blockquote {
            font-style: italic;
            color: #8b949e;
            margin-bottom: 15px;
            font-size: 1.1em;
        }

        .about ul {
            list-style: none;
            padding-left: 0;
        }

        .about li {
            padding: 8px 0;
            color: #c9d1d9;
        }

        .section-title {
            font-size: 2em;
            margin: 40px 0 20px 0;
            text-align: center;
            color: #58a6ff;
            position: relative;
        }

        .section-title:before {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 3px;
            background: linear-gradient(90deg, transparent, #2e9ef7, transparent);
        }

        .tech-stack {
            margin: 30px 0;
        }

        .tech-category {
            margin: 25px 0;
        }

        .tech-category h3 {
            color: #58a6ff;
            margin-bottom: 15px;
            font-size: 1.3em;
        }

        .tech-badges {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
        }

        .tech-badge {
            display: inline-block;
            padding: 8px 16px;
            border-radius: 6px;
            font-weight: 600;
            font-size: 13px;
            transition: transform 0.2s;
        }

        .tech-badge:hover {
            transform: scale(1.05);
        }

        .dsa-section {
            background: #21262d;
            padding: 30px;
            border-radius: 8px;
            margin: 30px 0;
        }

        .dsa-table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
        }

        .dsa-table th,
        .dsa-table td {
            padding: 15px;
            text-align: left;
            border-bottom: 1px solid #30363d;
        }

        .dsa-table th {
            color: #58a6ff;
            font-weight: 600;
        }

        .dsa-table tr:hover {
            background: #161b22;
        }

        .problem-count {
            font-size: 1.2em;
            font-weight: bold;
            color: #2e9ef7;
        }

        .total-problems {
            text-align: center;
            margin-top: 30px;
            font-size: 2em;
            color: #58a6ff;
            font-weight: bold;
            padding: 20px;
            background: linear-gradient(135deg, #1a1f2e 0%, #21262d 100%);
            border-radius: 8px;
            border: 2px solid #30363d;
        }

        .certifications {
            background: #21262d;
            padding: 30px;
            border-radius: 8px;
            margin: 30px 0;
        }

        .cert-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }

        .cert-card {
            background: #161b22;
            padding: 20px;
            border-radius: 8px;
            border: 1px solid #30363d;
            transition: transform 0.2s, border-color 0.2s;
        }

        .cert-card:hover {
            transform: translateY(-5px);
            border-color: #2e9ef7;
        }

        .cert-card h4 {
            color: #58a6ff;
            margin-bottom: 10px;
        }

        .cert-card p {
            color: #8b949e;
            font-size: 0.9em;
            margin: 5px 0;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin: 30px 0;
        }

        .stat-card {
            background: #21262d;
            padding: 20px;
            border-radius: 8px;
            text-align: center;
            border: 1px solid #30363d;
        }

        .stat-card img {
            max-width: 100%;
            height: auto;
            border-radius: 6px;
        }

        .footer {
            text-align: center;
            margin-top: 50px;
            padding-top: 30px;
            border-top: 1px solid #30363d;
            color: #8b949e;
        }

        .footer p {
            margin: 10px 0;
            font-style: italic;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .container > * {
            animation: fadeIn 0.6s ease-out;
        }

        .view-count {
            display: inline-block;
            background: #6e40c9;
            color: white;
            padding: 8px 20px;
            border-radius: 20px;
            font-weight: bold;
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>👋 Hi there! I'm [Your Name]</h1>
            
            <div class="typing-animation" id="typing-text"></div>

            <div class="social-links">
                <a href="#" class="badge linkedin">🔗 LinkedIn</a>
                <a href="#" class="badge devto">📝 Dev.to</a>
                <a href="#" class="badge medium">✍️ Medium</a>
                <a href="#" class="badge portfolio">🌐 Portfolio</a>
                <a href="#" class="badge email">📧 Email</a>
            </div>
        </div>

        <div class="about">
            <blockquote>Passionate developer who loves building scalable applications and solving complex problems. Always learning, always coding!</blockquote>
            
            <ul>
                <li>🔭 Currently working on <strong>[Your Current Project]</strong></li>
                <li>🌱 Learning <strong>[Technologies you're learning]</strong></li>
                <li>💬 Ask me about <strong>Web Development, DSA, System Design</strong></li>
                <li>⚡ Fun fact: <strong>[Something interesting about you]</strong></li>
            </ul>
        </div>

        <h2 class="section-title">💻 Tech Stack</h2>
        
        <div class="tech-stack">
            <div class="tech-category">
                <h3>Languages</h3>
                <div class="tech-badges">
                    <span class="tech-badge" style="background: #F7DF1E; color: black;">JavaScript</span>
                    <span class="tech-badge" style="background: #3776AB; color: white;">Python</span>
                    <span class="tech-badge" style="background: #ED8B00; color: white;">Java</span>
                    <span class="tech-badge" style="background: #00599C; color: white;">C++</span>
                    <span class="tech-badge" style="background: #007ACC; color: white;">TypeScript</span>
                    <span class="tech-badge" style="background: #00ADD8; color: white;">Go</span>
                </div>
            </div>

            <div class="tech-category">
                <h3>Frontend</h3>
                <div class="tech-badges">
                    <span class="tech-badge" style="background: #61DAFB; color: black;">React</span>
                    <span class="tech-badge" style="background: #000000; color: white;">Next.js</span>
                    <span class="tech-badge" style="background: #4FC08D; color: white;">Vue.js</span>
                    <span class="tech-badge" style="background: #DD0031; color: white;">Angular</span>
                    <span class="tech-badge" style="background: #38B2AC; color: white;">TailwindCSS</span>
                </div>
            </div>

            <div class="tech-category">
                <h3>Backend</h3>
                <div class="tech-badges">
                    <span class="tech-badge" style="background: #43853D; color: white;">Node.js</span>
                    <span class="tech-badge" style="background: #404D59; color: white;">Express.js</span>
                    <span class="tech-badge" style="background: #092E20; color: white;">Django</span>
                    <span class="tech-badge" style="background: #000000; color: white;">Flask</span>
                    <span class="tech-badge" style="background: #6DB33F; color: white;">Spring Boot</span>
                </div>
            </div>

            <div class="tech-category">
                <h3>Databases & DevOps</h3>
                <div class="tech-badges">
                    <span class="tech-badge" style="background: #4EA94B; color: white;">MongoDB</span>
                    <span class="tech-badge" style="background: #316192; color: white;">PostgreSQL</span>
                    <span class="tech-badge" style="background: #2496ED; color: white;">Docker</span>
                    <span class="tech-badge" style="background: #326CE5; color: white;">Kubernetes</span>
                    <span class="tech-badge" style="background: #232F3E; color: white;">AWS</span>
                </div>
            </div>
        </div>

        <h2 class="section-title">📊 DSA Progress</h2>
        
        <div class="dsa-section">
            <h3 style="text-align: center; color: #58a6ff; margin-bottom: 20px;">🎯 Coding Platforms</h3>
            
            <table class="dsa-table">
                <thead>
                    <tr>
                        <th>Platform</th>
                        <th>Problems Solved</th>
                        <th>Profile Link</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>🟠 LeetCode</td>
                        <td><span class="problem-count">500+</span></td>
                        <td><a href="#" style="color: #58a6ff;">Visit Profile →</a></td>
                    </tr>
                    <tr>
                        <td>🔵 CodeForces</td>
                        <td><span class="problem-count">300+</span></td>
                        <td><a href="#" style="color: #58a6ff;">Visit Profile →</a></td>
                    </tr>
                    <tr>
                        <td>🟢 HackerRank</td>
                        <td><span class="problem-count">200+</span></td>
                        <td><a href="#" style="color: #58a6ff;">Visit Profile →</a></td>
                    </tr>
                    <tr>
                        <td>🟢 GeeksforGeeks</td>
                        <td><span class="problem-count">400+</span></td>
                        <td><a href="#" style="color: #58a6ff;">Visit Profile →</a></td>
                    </tr>
                </tbody>
            </table>

            <div class="total-problems">
                📈 Total Problems Solved: 1400+
            </div>
        </div>

        <h2 class="section-title">🏆 Certifications</h2>
        
        <div class="certifications">
            <div class="cert-grid">
                <div class="cert-card">
                    <h4>AWS Certified Solutions Architect</h4>
                    <p>📍 Amazon Web Services</p>
                    <p>📅 2024</p>
                    <p><a href="#" style="color: #58a6ff;">View Credential →</a></p>
                </div>
                
                <div class="cert-card">
                    <h4>Google Cloud Professional</h4>
                    <p>📍 Google Cloud</p>
                    <p>📅 2024</p>
                    <p><a href="#" style="color: #58a6ff;">View Credential →</a></p>
                </div>
                
                <div class="cert-card">
                    <h4>MongoDB Certified Developer</h4>
                    <p>📍 MongoDB University</p>
                    <p>📅 2023</p>
                    <p><a href="#" style="color: #58a6ff;">View Credential →</a></p>
                </div>
                
                <div class="cert-card">
                    <h4>Meta Frontend Developer</h4>
                    <p>📍 Meta (Coursera)</p>
                    <p>📅 2023</p>
                    <p><a href="#" style="color: #58a6ff;">View Credential →</a></p>
                </div>
            </div>
        </div>

        <h2 class="section-title">📈 GitHub Stats</h2>
        
        <div class="stats-grid">
            <div class="stat-card">
                <img src="https://github-readme-stats.vercel.app/api?username=torvalds&show_icons=true&theme=tokyonight&hide_border=true&count_private=true" alt="GitHub Stats">
            </div>
            <div class="stat-card">
                <img src="https://github-readme-streak-stats.herokuapp.com/?user=torvalds&theme=tokyonight&hide_border=true" alt="GitHub Streak">
            </div>
        </div>

        <div class="stat-card" style="margin-top: 20px;">
            <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=torvalds&layout=compact&theme=tokyonight&hide_border=true" alt="Top Languages">
        </div>

        <h2 class="section-title">🎯 Current Goals for 2025</h2>
        
        <div class="about">
            <ul>
                <li>☐ Contribute to 10+ open source projects</li>
                <li>☐ Master System Design</li>
                <li>☐ Solve 1000+ DSA problems</li>
                <li>☐ Build 5 full-stack projects</li>
                <li>☐ Write 20+ technical blogs</li>
            </ul>
        </div>

        <div class="footer">
            <div class="view-count">👀 Profile Views: 1,234</div>
            <p style="margin-top: 20px; font-size: 1.1em;">💬 Feel free to reach out if you want to collaborate on projects or just chat about tech!</p>
            <p>"Code is like humor. When you have to explain it, it's bad." – Cory House</p>
        </div>
    </div>

    <script>
        // Typing animation
        const phrases = [
            'Full Stack Developer 💻',
            'Problem Solver 🚀',
            'Lifelong Learner 📚'
        ];
        
        let phraseIndex = 0;
        let charIndex = 0;
        let isDeleting = false;
        const typingElement = document.getElementById('typing-text');
        
        function type() {
            const currentPhrase = phrases[phraseIndex];
            
            if (isDeleting) {
                typingElement.textContent = currentPhrase.substring(0, charIndex - 1);
                charIndex--;
            } else {
                typingElement.textContent = currentPhrase.substring(0, charIndex + 1);
                charIndex++;
            }
            
            if (!isDeleting && charIndex === currentPhrase.length) {
                setTimeout(() => isDeleting = true, 2000);
            } else if (isDeleting && charIndex === 0) {
                isDeleting = false;
                phraseIndex = (phraseIndex + 1) % phrases.length;
            }
            
            const speed = isDeleting ? 50 : 100;
            setTimeout(type, speed);
        }
        
        type();
    </script>
</body>
</html>
