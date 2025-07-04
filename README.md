<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sumit Jaiswal - Full Stack Developer</title>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
            line-height: 1.6;
            color: #333;
            background: #0a0a0a;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        header {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 60px 0;
            position: relative;
            overflow: hidden;
        }

        .header-bg {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1000 1000"><polygon fill="%23ffffff05" points="0,0 1000,300 1000,1000 0,700"/></svg>');
            background-size: cover;
        }

        .header-content {
            position: relative;
            z-index: 2;
            text-align: center;
        }

        .profile-image {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            margin: 0 auto 30px;
            border: 5px solid rgba(255,255,255,0.3);
            background: linear-gradient(45deg, #667eea, #764ba2);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 60px;
            color: white;
            font-weight: bold;
            box-shadow: 0 20px 40px rgba(0,0,0,0.3);
        }

        .name {
            font-size: 3.5rem;
            font-weight: 700;
            margin-bottom: 10px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        }

        .title {
            font-size: 1.5rem;
            opacity: 0.9;
            margin-bottom: 30px;
            font-weight: 300;
        }

        .contact-info {
            display: flex;
            justify-content: center;
            gap: 30px;
            flex-wrap: wrap;
            margin-bottom: 40px;
        }

        .contact-item {
            display: flex;
            align-items: center;
            gap: 8px;
            color: rgba(255,255,255,0.9);
            text-decoration: none;
            transition: all 0.3s ease;
            padding: 8px 16px;
            border-radius: 25px;
            background: rgba(255,255,255,0.1);
            backdrop-filter: blur(10px);
        }

        .contact-item:hover {
            background: rgba(255,255,255,0.2);
            transform: translateY(-2px);
            color: white;
        }

        .cta-button {
            display: inline-block;
            background: rgba(255,255,255,0.2);
            color: white;
            padding: 15px 30px;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            transition: all 0.3s ease;
            border: 2px solid rgba(255,255,255,0.3);
            backdrop-filter: blur(10px);
        }

        .cta-button:hover {
            background: rgba(255,255,255,0.3);
            transform: translateY(-2px);
            box-shadow: 0 10px 30px rgba(0,0,0,0.3);
        }

        /* Main Content */
        main {
            background: #ffffff;
            position: relative;
            z-index: 1;
        }

        .section {
            padding: 80px 0;
            position: relative;
        }

        .section:nth-child(even) {
            background: #f8fafc;
        }

        .section-title {
            font-size: 2.5rem;
            font-weight: 700;
            text-align: center;
            margin-bottom: 60px;
            color: #2d3748;
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background: linear-gradient(135deg, #667eea, #764ba2);
            border-radius: 2px;
        }

        /* About Section */
        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 60px;
            align-items: center;
        }

        .about-text {
            font-size: 1.2rem;
            line-height: 1.8;
            color: #4a5568;
        }

        .about-stats {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 30px;
        }

        .stat-item {
            text-align: center;
            padding: 30px;
            background: white;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            transition: transform 0.3s ease;
        }

        .stat-item:hover {
            transform: translateY(-5px);
        }

        .stat-number {
            font-size: 2.5rem;
            font-weight: 700;
            color: #667eea;
            margin-bottom: 10px;
        }

        .stat-label {
            color: #718096;
            font-weight: 500;
        }

        /* Skills Section */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
        }

        .skill-category {
            background: white;
            padding: 40px;
            border-radius: 20px;
            box-shadow: 0 15px 40px rgba(0,0,0,0.1);
            transition: all 0.3s ease;
        }

        .skill-category:hover {
            transform: translateY(-10px);
            box-shadow: 0 25px 60px rgba(0,0,0,0.15);
        }

        .skill-category h3 {
            font-size: 1.5rem;
            font-weight: 600;
            margin-bottom: 25px;
            color: #2d3748;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .skill-category i {
            font-size: 1.8rem;
            color: #667eea;
        }

        .skill-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
        }

        .skill-tag {
            background: linear-gradient(135deg, #667eea, #764ba2);
            color: white;
            padding: 8px 16px;
            border-radius: 25px;
            font-size: 0.9rem;
            font-weight: 500;
            transition: all 0.3s ease;
        }

        .skill-tag:hover {
            transform: scale(1.05);
            box-shadow: 0 5px 15px rgba(102, 126, 234, 0.4);
        }

        /* Experience Section */
        .experience-timeline {
            position: relative;
            padding-left: 30px;
        }

        .experience-timeline::before {
            content: '';
            position: absolute;
            left: 15px;
            top: 0;
            bottom: 0;
            width: 2px;
            background: linear-gradient(135deg, #667eea, #764ba2);
        }

        .experience-item {
            position: relative;
            background: white;
            padding: 30px;
            border-radius: 15px;
            margin-bottom: 30px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            transition: all 0.3s ease;
        }

        .experience-item:hover {
            transform: translateX(10px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.15);
        }

        .experience-item::before {
            content: '';
            position: absolute;
            left: -37px;
            top: 30px;
            width: 12px;
            height: 12px;
            background: #667eea;
            border-radius: 50%;
            border: 3px solid white;
        }

        .experience-header {
            display: flex;
            justify-content: space-between;
            align-items: flex-start;
            margin-bottom: 20px;
            flex-wrap: wrap;
        }

        .experience-title {
            font-size: 1.3rem;
            font-weight: 600;
            color: #2d3748;
            margin-bottom: 5px;
        }

        .experience-company {
            color: #667eea;
            font-weight: 500;
        }

        .experience-period {
            background: #e2e8f0;
            color: #4a5568;
            padding: 5px 15px;
            border-radius: 20px;
            font-size: 0.9rem;
            font-weight: 500;
        }

        .experience-description {
            color: #4a5568;
            line-height: 1.6;
        }

        /* Projects Section */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 40px;
        }

        .project-card {
            background: white;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 15px 40px rgba(0,0,0,0.1);
            transition: all 0.3s ease;
        }

        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 25px 60px rgba(0,0,0,0.15);
        }

        .project-header {
            background: linear-gradient(135deg, #667eea, #764ba2);
            color: white;
            padding: 30px;
            text-align: center;
        }

        .project-title {
            font-size: 1.5rem;
            font-weight: 600;
            margin-bottom: 10px;
        }

        .project-duration {
            opacity: 0.9;
            font-size: 0.9rem;
        }

        .project-content {
            padding: 30px;
        }

        .project-description {
            color: #4a5568;
            line-height: 1.6;
            margin-bottom: 20px;
        }

        .project-tech {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
        }

        .tech-tag {
            background: #e2e8f0;
            color: #4a5568;
            padding: 5px 12px;
            border-radius: 15px;
            font-size: 0.8rem;
            font-weight: 500;
        }

        /* Contact Section */
        .contact-section {
            background: linear-gradient(135deg, #2d3748, #4a5568);
            color: white;
        }

        .contact-content {
            text-align: center;
        }

        .contact-text {
            font-size: 1.3rem;
            margin-bottom: 40px;
            opacity: 0.9;
            line-height: 1.6;
        }

        .contact-buttons {
            display: flex;
            justify-content: center;
            gap: 20px;
            flex-wrap: wrap;
        }

        .contact-button {
            display: inline-flex;
            align-items: center;
            gap: 10px;
            background: rgba(255,255,255,0.1);
            color: white;
            padding: 15px 30px;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            transition: all 0.3s ease;
            border: 2px solid rgba(255,255,255,0.2);
            backdrop-filter: blur(10px);
        }

        .contact-button:hover {
            background: rgba(255,255,255,0.2);
            transform: translateY(-2px);
            box-shadow: 0 10px 30px rgba(0,0,0,0.3);
        }

        /* Footer */
        footer {
            background: #1a202c;
            color: white;
            text-align: center;
            padding: 40px 0;
        }

        .footer-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 20px;
        }

        .footer-text {
            opacity: 0.8;
        }

        .footer-links {
            display: flex;
            gap: 20px;
        }

        .footer-link {
            color: rgba(255,255,255,0.7);
            text-decoration: none;
            transition: color 0.3s ease;
        }

        .footer-link:hover {
            color: white;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .name {
                font-size: 2.5rem;
            }
            
            .title {
                font-size: 1.2rem;
            }
            
            .contact-info {
                flex-direction: column;
                gap: 15px;
            }
            
            .about-content {
                grid-template-columns: 1fr;
                gap: 40px;
            }
            
            .about-stats {
                grid-template-columns: 1fr;
            }
            
            .skills-grid {
                grid-template-columns: 1fr;
            }
            
            .projects-grid {
                grid-template-columns: 1fr;
            }
            
            .experience-header {
                flex-direction: column;
                align-items: flex-start;
            }
            
            .footer-content {
                flex-direction: column;
                text-align: center;
            }
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

        .animate-in {
            animation: fadeInUp 0.6s ease-out;
        }

        /* Scroll behavior */
        html {
            scroll-behavior: smooth;
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="header-bg"></div>
        <div class="container">
            <div class="header-content">
                <div class="profile-image">
                    SJ
                </div>
                <h1 class="name">Sumit Jaiswal</h1>
                <h2 class="title">Full Stack Software Developer</h2>
                
                <div class="contact-info">
                    <a href="tel:+917323837297" class="contact-item">
                        <i class="fas fa-phone"></i>
                        <span>+91 7323837297</span>
                    </a>
                    <a href="mailto:someitjaiswal.sj.97@gmail.com" class="contact-item">
                        <i class="fas fa-envelope"></i>
                        <span>someitjaiswal.sj.97@gmail.com</span>
                    </a>
                    <div class="contact-item">
                        <i class="fas fa-map-marker-alt"></i>
                        <span>Lucknow, India</span>
                    </div>
                </div>
                
                <a href="#contact" class="cta-button">
                    <i class="fas fa-rocket"></i>
                    Let's Work Together
                </a>
            </div>
        </div>
    </header>

    <!-- Main Content -->
    <main>
        <!-- About Section -->
        <section id="about" class="section">
            <div class="container">
                <h2 class="section-title">About Me</h2>
                <div class="about-content">
                    <div class="about-text">
                        <p>Full Stack Software Developer with 5+ years of hands-on experience building scalable web applications and APIs. Skilled in both frontend and backend technologies including PHP, Laravel, JavaScript, React, MySQL, and RESTful services.</p>
                        <p>Proven expertise in software design, team leadership, and client communication. Adept at working in agile environments and committed to delivering efficient, high-quality solutions that drive business success.</p>
                    </div>
                    <div class="about-stats">
                        <div class="stat-item">
                            <div class="stat-number">5+</div>
                            <div class="stat-label">Years Experience</div>
                        </div>
                        <div class="stat-item">
                            <div class="stat-number">70+</div>
                            <div class="stat-label">Projects Completed</div>
                        </div>
                        <div class="stat-item">
                            <div class="stat-number">15+</div>
                            <div class="stat-label">Technologies</div>
                        </div>
                        <div class="stat-item">
                            <div class="stat-number">100%</div>
                            <div class="stat-label">Client Satisfaction</div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Skills Section -->
        <section id="skills" class="section">
            <div class="container">
                <h2 class="section-title">Technical Skills</h2>
                <div class="skills-grid">
                    <div class="skill-category">
                        <h3><i class="fab fa-php"></i> Backend Development</h3>
                        <div class="skill-tags">
                            <span class="skill-tag">PHP</span>
                            <span class="skill-tag">Laravel</span>
                            <span class="skill-tag">CodeIgniter</span>
                            <span class="skill-tag">Node.js</span>
                            <span class="skill-tag">MySQL</span>
                        </div>
                    </div>
                    
                    <div class="skill-category">
                        <h3><i class="fab fa-js"></i> Frontend Development</h3>
                        <div class="skill-tags">
                            <span class="skill-tag">JavaScript</span>
                            <span class="skill-tag">Vue.js</span>
                            <span class="skill-tag">React</span>
                            <span class="skill-tag">HTML5</span>
                            <span class="skill-tag">CSS3</span>
                        </div>
                    </div>
                    
                    <div class="skill-category">
                        <h3><i class="fas fa-cloud"></i> Cloud & DevOps</h3>
                        <div class="skill-tags">
                            <span class="skill-tag">AWS</span>
                            <span class="skill-tag">Google Cloud</span>
                            <span class="skill-tag">Docker</span>
                            <span class="skill-tag">Firebase</span>
                        </div>
                    </div>
                    
                    <div class="skill-category">
                        <h3><i class="fas fa-tools"></i> Tools & Platforms</h3>
                        <div class="skill-tags">
                            <span class="skill-tag">Bubble.io</span>
                            <span class="skill-tag">Payment Gateways</span>
                            <span class="skill-tag">Push Notifications</span>
                            <span class="skill-tag">RESTful APIs</span>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Experience Section -->
        <section id="experience" class="section">
            <div class="container">
                <h2 class="section-title">Work Experience</h2>
                <div class="experience-timeline">
                    <div class="experience-item">
                        <div class="experience-header">
                            <div>
                                <h3 class="experience-title">Software Developer</h3>
                                <p class="experience-company">Jamtech Technologies Pvt Ltd</p>
                            </div>
                            <span class="experience-period">Jun 2023 - Present</span>
                        </div>
                        <p class="experience-description">
                            Spearheaded software maintenance, API development, and deployment of projects on AWS servers. Proficiently managed multiple projects concurrently, driving continuous enhancement of functionality and performance.
                        </p>
                    </div>
                    
                    <div class="experience-item">
                        <div class="experience-header">
                            <div>
                                <h3 class="experience-title">Software Developer</h3>
                                <p class="experience-company">Gautam Tech Solutions</p>
                            </div>
                            <span class="experience-period">Jun 2022 - Jun 2023</span>
                        </div>
                        <p class="experience-description">
                            Managed multiple software systems, updating and adding new modules. Handled CPanel management and maintained existing applications.
                        </p>
                    </div>
                    
                    <div class="experience-item">
                        <div class="experience-header">
                            <div>
                                <h3 class="experience-title">Full Stack Developer</h3>
                                <p class="experience-company">Bhavya Technologies Pvt Ltd</p>
                            </div>
                            <span class="experience-period">Aug 2020 - Sep 2021</span>
                        </div>
                        <p class="experience-description">
                            Created beautiful websites and web applications working on frontend, backend, logo design, graphic design, and basic SEO optimization.
                        </p>
                    </div>
                    
                    <div class="experience-item">
                        <div class="experience-header">
                            <div>
                                <h3 class="experience-title">PHP Web Developer</h3>
                                <p class="experience-company">Sam Softech Consultancy Pvt Ltd</p>
                            </div>
                            <span class="experience-period">Feb 2019 - Mar 2020</span>
                        </div>
                        <p class="experience-description">
                            Worked on more than 70+ beautiful websites focusing on both backend and frontend development using PHP and related technologies.
                        </p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Projects Section -->
        <section id="projects" class="section">
            <div class="container">
                <h2 class="section-title">Featured Projects</h2>
                <div class="projects-grid">
                    <div class="project-card">
                        <div class="project-header">
                            <h3 class="project-title">GyanPeeth</h3>
                            <span class="project-duration">12 Months</span>
                        </div>
                        <div class="project-content">
                            <p class="project-description">
                                College management software serving Gautam Group. Streamlines administrative tasks, enhances communication, and elevates the academic experience with features like student enrollment, attendance tracking, and grade management.
                            </p>
                            <div class="project-tech">
                                <span class="tech-tag">PHP</span>
                                <span class="tech-tag">Laravel</span>
                                <span class="tech-tag">MySQL</span>
                                <span class="tech-tag">Admin Panel</span>
                            </div>
                        </div>
                    </div>
                    
                    <div class="project-card">
                        <div class="project-header">
                            <h3 class="project-title">Guardian Angel</h3>
                            <span class="project-duration">15 Months</span>
                        </div>
                        <div class="project-content">
                            <p class="project-description">
                                Mobile application for location tracking allowing parents to monitor their children's real-time location, create specific routes, and receive deviation alerts. Built with WordPress backend and Google Maps API integration.
                            </p>
                            <div class="project-tech">
                                <span class="tech-tag">WordPress</span>
                                <span class="tech-tag">Google Maps API</span>
                                <span class="tech-tag">Mobile App</span>
                                <span class="tech-tag">Location Services</span>
                            </div>
                        </div>
                    </div>
                    
                    <div class="project-card">
                        <div class="project-header">
                            <h3 class="project-title">Book Your Own</h3>
                            <span class="project-duration">8 Months</span>
                        </div>
                        <div class="project-content">
                            <p class="project-description">
                                Online Travel Agency (OTA) platform from Punjab, India for hotel bookings. Integrated third-party channel managers including Staah and Axis for comprehensive booking management.
                            </p>
                            <div class="project-tech">
                                <span class="tech-tag">Laravel</span>
                                <span class="tech-tag">Vue.js</span>
                                <span class="tech-tag">Angular</span>
                                <span class="tech-tag">MySQL</span>
                                <span class="tech-tag">Channel Integration</span>
                            </div>
                        </div>
                    </div>
                    
                    <div class="project-card">
                        <div class="project-header">
                            <h3 class="project-title">PitchPrfct</h3>
                            <span class="project-duration">10 Months</span>
                        </div>
                        <div class="project-content">
                            <p class="project-description">
                                Automation application for lead communication with custom workflows, contact management, one-to-one chat functionality, and bulk messaging capabilities. Built entirely using Bubble.io no-code platform.
                            </p>
                            <div class="project-tech">
                                <span class="tech-tag">Bubble.io</span>
                                <span class="tech-tag">No-Code Development</span>
                                <span class="tech-tag">Automation</span>
                                <span class="tech-tag">Chat Application</span>
                            </div>
                        </div>
                    </div>
                    
                    <div class="project-card">
                        <div class="project-header">
                            <h3 class="project-title">Onleetech</h3>
                            <span class="project-duration">3 Months</span>
                        </div>
                        <div class="project-content">
                            <p class="project-description">
                                Online platform connecting customers with qualified technicians. Features real-time matching, subscription model, KYC verification, and video calls with remote access capabilities. Built as a Progressive Web App.
                            </p>
                            <div class="project-tech">
                                <span class="tech-tag">Vue.js</span>
                                <span class="tech-tag">Laravel</span>
                                <span class="tech-tag">PWA</span>
                                <span class="tech-tag">Video Calling</span>
                                <span class="tech-tag">Remote Access</span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Contact Section -->
        <section id="contact" class="section contact-section">
            <div class="container">
                <h2 class="section-title" style="color: white;">Let's Build Something Amazing Together</h2>
                <div class="contact-content">
                    <p class="contact-text">
                        Ready to turn your ideas into reality? I'm always excited to work on new projects and help bring innovative solutions to life. Let's discuss how we can work together to create something exceptional.
                    </p>
                    <div class="contact-buttons">
                        <a href="mailto:someitjaiswal.sj.97@gmail.com" class="contact-button">
                            <i class="fas fa-envelope"></i>
                            Send Email
                        </a>
                        <a href="tel:+917323837297" class="contact-button">
                            <i class="fas fa-phone"></i>
                            Call Me
                        </a>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-text">
                    &copy; 2024 Sumit Jaiswal. All rights reserved.
                </div>
                <div class="footer-links">
                    <a href="#about" class="footer-link">About</a>
                    <a href="#skills" class="footer-link">Skills</a>
                    <a href="#experience" class="footer-link">Experience</a>
                    <a href="#projects" class="footer-link">Projects</a>
                    <a href="#contact" class="footer-link">Contact</a>
                </div>
            </div>
        </div>
    </footer>

    <script>
        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
