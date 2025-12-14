<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Arka Maitra | Full-Stack Developer</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', system-ui, -apple-system, sans-serif;
        }

        :root {
            --primary: #6366f1;
            --primary-dark: #4f46e5;
            --secondary: #10b981;
            --dark: #0f172a;
            --dark-light: #1e293b;
            --text: #e2e8f0;
            --text-muted: #94a3b8;
            --glass: rgba(30, 41, 59, 0.7);
            --shadow: 0 10px 25px -5px rgba(0, 0, 0, 0.3);
            --transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        }

        body {
            background: linear-gradient(135deg, #0f172a 0%, #1e1b4b 100%);
            color: var(--text);
            min-height: 100vh;
            overflow-x: hidden;
            line-height: 1.6;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
        }

        /* Header & Profile */
        .header {
            text-align: center;
            padding: 3rem 0;
            position: relative;
        }

        .profile-container {
            position: relative;
            display: inline-block;
            margin-bottom: 2rem;
        }

        .profile-img {
            width: 180px;
            height: 180px;
            border-radius: 50%;
            object-fit: cover;
            border: 4px solid var(--primary);
            box-shadow: var(--shadow), 0 0 40px rgba(99, 102, 241, 0.3);
            transition: var(--transition);
            position: relative;
            z-index: 2;
        }

        .profile-img:hover {
            transform: scale(1.05);
            box-shadow: var(--shadow), 0 0 60px rgba(99, 102, 241, 0.5);
        }

        .profile-ring {
            position: absolute;
            top: -10px;
            left: -10px;
            right: -10px;
            bottom: -10px;
            border: 2px solid var(--secondary);
            border-radius: 50%;
            animation: pulse 3s infinite;
            z-index: 1;
        }

        @keyframes pulse {
            0%, 100% { opacity: 0.7; transform: scale(1); }
            50% { opacity: 0.3; transform: scale(1.05); }
        }

        .name {
            font-size: 3.5rem;
            font-weight: 800;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            margin-bottom: 0.5rem;
            letter-spacing: -0.5px;
        }

        .tagline {
            font-size: 1.2rem;
            color: var(--text-muted);
            margin-bottom: 2rem;
            font-weight: 300;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            margin-top: 2rem;
        }

        .social-icon {
            width: 45px;
            height: 45px;
            background: var(--glass);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--text);
            font-size: 1.2rem;
            text-decoration: none;
            transition: var(--transition);
            border: 1px solid rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
        }

        .social-icon:hover {
            background: var(--primary);
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(99, 102, 241, 0.3);
        }

        /* Cards */
        .card {
            background: var(--glass);
            border-radius: 20px;
            padding: 2rem;
            margin-bottom: 2.5rem;
            border: 1px solid rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            box-shadow: var(--shadow);
            transition: var(--transition);
        }

        .card:hover {
            transform: translateY(-5px);
            border-color: rgba(99, 102, 241, 0.3);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.4);
        }

        .section-title {
            font-size: 1.8rem;
            margin-bottom: 1.5rem;
            color: var(--text);
            position: relative;
            display: inline-block;
        }

        .section-title::after {
            content: '';
            position: absolute;
            left: 0;
            bottom: -8px;
            width: 50px;
            height: 3px;
            background: linear-gradient(90deg, var(--primary), transparent);
            border-radius: 3px;
        }

        /* About */
        .about-text {
            font-size: 1.1rem;
            line-height: 1.8;
            color: var(--text-muted);
        }

        .highlight {
            color: var(--secondary);
            font-weight: 500;
        }

        /* Skills Grid */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 2rem;
        }

        .skill-category {
            margin-bottom: 2rem;
        }

        .category-title {
            font-size: 1.3rem;
            margin-bottom: 1rem;
            color: var(--primary);
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .category-title i {
            font-size: 1.2rem;
        }

        .tech-icons {
            display: flex;
            flex-wrap: wrap;
            gap: 1rem;
        }

        .tech-icon {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            width: 80px;
            height: 80px;
            background: rgba(15, 23, 42, 0.6);
            border-radius: 16px;
            transition: var(--transition);
            border: 1px solid rgba(255, 255, 255, 0.05);
            padding: 0.5rem;
        }

        .tech-icon:hover {
            background: var(--primary-dark);
            transform: translateY(-5px);
            border-color: var(--primary);
        }

        .tech-icon img {
            width: 36px;
            height: 36px;
            margin-bottom: 8px;
            filter: brightness(0.9);
        }

        .tech-icon span {
            font-size: 0.8rem;
            color: var(--text-muted);
            text-align: center;
        }

        /* Stats */
        .stats {
            display: flex;
            justify-content: space-around;
            flex-wrap: wrap;
            gap: 2rem;
            margin-top: 2rem;
        }

        .stat-item {
            text-align: center;
        }

        .stat-number {
            font-size: 2.5rem;
            font-weight: 700;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }

        .stat-label {
            font-size: 0.9rem;
            color: var(--text-muted);
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-top: 5px;
        }

        /* Footer */
        .footer {
            text-align: center;
            padding: 2rem;
            margin-top: 3rem;
            border-top: 1px solid rgba(255, 255, 255, 0.05);
            color: var(--text-muted);
            font-size: 0.9rem;
        }

        .accent {
            color: var(--secondary);
        }

        /* Responsive */
        @media (max-width: 768px) {
            .container {
                padding: 1.5rem;
            }
            
            .name {
                font-size: 2.5rem;
            }
            
            .skills-grid {
                grid-template-columns: 1fr;
            }
            
            .tech-icons {
                justify-content: center;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Header Section -->
        <header class="header">
            <div class="profile-container">
                <div class="profile-ring"></div>
                <img src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=774&q=80" 
                     alt="Arka Maitra" class="profile-img">
            </div>
            
            <h1 class="name">Arka Maitra</h1>
            <p class="tagline">Full-Stack Developer & Digital Architect</p>
            
            <div class="social-links">
                <a href="#" class="social-icon"><i class="fab fa-github"></i></a>
                <a href="#" class="social-icon"><i class="fab fa-linkedin-in"></i></a>
                <a href="#" class="social-icon"><i class="fab fa-twitter"></i></a>
                <a href="#" class="social-icon"><i class="fas fa-envelope"></i></a>
            </div>
        </header>

        <!-- About Section -->
        <section class="card">
            <h2 class="section-title">About Me</h2>
            <p class="about-text">
                I'm a passionate <span class="highlight">full-stack developer</span> with expertise in building scalable web applications and robust system architectures. 
                My focus lies in creating elegant solutions to complex problems using modern web technologies, 
                cloud infrastructure, and database-driven design principles.
            </p>
            <p class="about-text">
                Beyond code, I engage in philosophical discourse, explore the frontiers of <span class="highlight">artificial intelligence</span>, 
                and capture the world's beauty through my lens. I believe in the intersection of technology and artistry.
            </p>
        </section>

        <!-- Technologies Section -->
        <section class="card">
            <h2 class="section-title">Technologies & Tools</h2>
            
            <div class="skills-grid">
                <!-- Programming Languages -->
                <div class="skill-category">
                    <h3 class="category-title"><i class="fas fa-code"></i> Programming Languages</h3>
                    <div class="tech-icons">
                        <div class="tech-icon">
                            <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg" alt="JavaScript">
                            <span>JavaScript</span>
                        </div>
                        <div class="tech-icon">
                            <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" alt="Python">
                            <span>Python</span>
                        </div>
                        <div class="tech-icon">
                            <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/php/php-original.svg" alt="PHP">
                            <span>PHP</span>
                        </div>
                    </div>
                </div>

                <!-- Frontend -->
                <div class="skill-category">
                    <h3 class="category-title"><i class="fas fa-palette"></i> Frontend</h3>
                    <div class="tech-icons">
                        <div class="tech-icon">
                            <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/react/react-original.svg" alt="React">
                            <span>React</span>
                        </div>
                        <div class="tech-icon">
                            <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nextjs/nextjs-original.svg" alt="Next.js">
                            <span>Next.js</span>
                        </div>
                        <div class="tech-icon">
                            <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/tailwindcss/tailwindcss-plain.svg" alt="Tailwind">
                            <span>Tailwind</span>
                        </div>
                        <div class="tech-icon">
                            <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/redux/redux-original.svg" alt="Redux">
                            <span>Redux</span>
                        </div>
                    </div>
                </div>

                <!-- Backend & Database -->
                <div class="skill-category">
                    <h3 class="category-title"><i class="fas fa-server"></i> Backend & Database</h3>
                    <div class="tech-icons">
                        <div class="tech-icon">
                            <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nodejs/nodejs-original.svg" alt="Node.js">
                            <span>Node.js</span>
                        </div>
                        <div class="tech-icon">
                            <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/express/express-original.svg" alt="Express">
                            <span>Express</span>
                        </div>
                        <div class="tech-icon">
                            <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/django/django-original.svg" alt="Django">
                            <span>Django</span>
                        </div>
                        <div class="tech-icon">
                            <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original.svg" alt="MySQL">
                            <span>MySQL</span>
                        </div>
                    </div>
                </div>

                <!-- DevOps & Tools -->
                <div class="skill-category">
                    <h3 class="category-title"><i class="fas fa-cogs"></i> DevOps & Tools</h3>
                    <div class="tech-icons">
                        <div class="tech-icon">
                            <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/docker/docker-original.svg" alt="Docker">
                            <span>Docker</span>
                        </div>
                        <div class="tech-icon">
                            <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/kubernetes/kubernetes-plain.svg" alt="Kubernetes">
                            <span>K8s</span>
                        </div>
                        <div class="tech-icon">
                            <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg" alt="Git">
                            <span>Git</span>
                        </div>
                        <div class="tech-icon">
                            <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/aws/aws-original.svg" alt="AWS">
                            <span>AWS</span>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Stats Section -->
        <section class="card">
            <h2 class="section-title">By The Numbers</h2>
            <div class="stats">
                <div class="stat-item">
                    <div class="stat-number">50+</div>
                    <div class="stat-label">Projects Completed</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">5+</div>
                    <div class="stat-label">Years Experience</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">100%</div>
                    <div class="stat-label">Client Satisfaction</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">∞</div>
                    <div class="stat-label">Passion for Code</div>
                </div>
            </div>
        </section>

        <!-- Footer -->
        <footer class="footer">
            <p>© 2023 <span class="accent">Arka Maitra</span>. Crafted with precision and passion.</p>
            <p>Let's build something amazing together. <a href="mailto:hello@arkamaitra.com" style="color: var(--primary); text-decoration: none;">Get in touch →</a></p>
        </footer>
    </div>

    <script>
        // Add subtle interactive effects
        document.addEventListener('DOMContentLoaded', function() {
            // Add hover effect to cards
            const cards = document.querySelectorAll('.card');
            cards.forEach(card => {
                card.addEventListener('mouseenter', function() {
                    this.style.transform = 'translateY(-8px)';
                });
                
                card.addEventListener('mouseleave', function() {
                    this.style.transform = 'translateY(0)';
                });
            });
            
            // Add scroll animation
            const observerOptions = {
                threshold: 0.1,
                rootMargin: '0px 0px -50px 0px'
            };
            
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.style.opacity = '1';
                        entry.target.style.transform = 'translateY(0)';
                    }
                });
            }, observerOptions);
            
            // Observe elements for animation
            const elementsToAnimate = document.querySelectorAll('.card, .profile-container');
            elementsToAnimate.forEach(el => {
                el.style.opacity = '0';
                el.style.transform = 'translateY(20px)';
                el.style.transition = 'opacity 0.5s ease, transform 0.5s ease';
                observer.observe(el);
            });
        });
    </script>
</body>
</html>
