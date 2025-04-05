Here's the complete source code for a cybersecurity learning website with a login page, beautiful design, and all topics mentioned:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CyberLearn - Free Cybersecurity Education</title>
    <style>
        :root {
            --primary: #2a2e45;
            --secondary: #5b6cf9;
            --accent: #00e8fc;
            --text: #f0f0f0;
            --bg: #1a1c2a;
            --card-bg: #252842;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: var(--bg);
            color: var(--text);
            line-height: 1.6;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* Header */
        header {
            background-color: var(--primary);
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.2);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 0;
        }
        
        .logo {
            display: flex;
            align-items: center;
            font-size: 1.5rem;
            font-weight: bold;
            color: var(--accent);
        }
        
        .logo span {
            color: var(--text);
        }
        
        .logo-icon {
            margin-right: 10px;
            font-size: 1.8rem;
        }
        
        .nav-links {
            display: flex;
            list-style: none;
        }
        
        .nav-links li {
            margin-left: 1.5rem;
        }
        
        .nav-links a {
            color: var(--text);
            text-decoration: none;
            transition: color 0.3s;
        }
        
        .nav-links a:hover {
            color: var(--accent);
        }
        
        .login-btn {
            background-color: var(--secondary);
            color: white;
            border: none;
            padding: 0.5rem 1.5rem;
            border-radius: 50px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s;
        }
        
        .login-btn:hover {
            background-color: var(--accent);
            color: var(--primary);
            transform: translateY(-2px);
        }
        
        /* Hero Section */
        .hero {
            height: 500px;
            background: linear-gradient(135deg, rgba(42, 46, 69, 0.9), rgba(26, 28, 42, 0.8)), url('/api/placeholder/1200/500') no-repeat center/cover;
            display: flex;
            align-items: center;
            text-align: center;
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
            background: repeating-linear-gradient(
                transparent,
                transparent 50px,
                rgba(91, 108, 249, 0.1) 50px,
                rgba(91, 108, 249, 0.1) 51px
            );
            transform: rotate(45deg);
            z-index: 1;
            animation: grid-move 20s linear infinite;
        }
        
        @keyframes grid-move {
            0% {
                transform: rotate(45deg) translateY(0);
            }
            100% {
                transform: rotate(45deg) translateY(100px);
            }
        }
        
        .hero-content {
            position: relative;
            z-index: 2;
            max-width: 800px;
            margin: 0 auto;
        }
        
        .hero h1 {
            font-size: 3rem;
            margin-bottom: 1rem;
            color: var(--text);
        }
        
        .hero h1 span {
            color: var(--accent);
        }
        
        .hero p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            color: var(--text);
        }
        
        .cta-btn {
            display: inline-block;
            background-color: var(--secondary);
            color: white;
            text-decoration: none;
            padding: 0.8rem 2rem;
            border-radius: 50px;
            font-weight: 600;
            transition: all 0.3s;
            margin: 0 10px;
        }
        
        .cta-btn:hover {
            background-color: var(--accent);
            color: var(--primary);
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
        }
        
        .cta-btn.outline {
            background-color: transparent;
            border: 2px solid var(--accent);
            color: var(--accent);
        }
        
        .cta-btn.outline:hover {
            background-color: var(--accent);
            color: var(--primary);
        }
        
        /* Courses Section */
        .section {
            padding: 4rem 0;
        }
        
        .section-header {
            text-align: center;
            margin-bottom: 3rem;
        }
        
        .section-header h2 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
            color: var(--accent);
        }
        
        .section-header p {
            max-width: 600px;
            margin: 0 auto;
            color: #a0a0a0;
        }
        
        .courses-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 2rem;
        }
        
        .course-card {
            background-color: var(--card-bg);
            border-radius: 10px;
            overflow: hidden;
            transition: transform 0.3s, box-shadow 0.3s;
        }
        
        .course-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.3);
        }
        
        .course-img {
            height: 180px;
            position: relative;
        }
        
        .course-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .course-level {
            position: absolute;
            top: 10px;
            right: 10px;
            background-color: var(--accent);
            color: var(--primary);
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 600;
        }
        
        .course-content {
            padding: 1.5rem;
        }
        
        .course-content h3 {
            font-size: 1.2rem;
            margin-bottom: 0.5rem;
        }
        
        .course-content p {
            color: #a0a0a0;
            margin-bottom: 1rem;
            font-size: 0.9rem;
        }
        
        .course-meta {
            display: flex;
            justify-content: space-between;
            color: var(--accent);
            font-size: 0.9rem;
        }
        
        /* Topics Section */
        .topics-container {
            display: flex;
            flex-wrap: wrap;
            gap: 1.5rem;
            justify-content: center;
        }
        
        .topic-box {
            background-color: var(--card-bg);
            border-radius: 10px;
            padding: 1.5rem;
            width: calc(25% - 1.5rem);
            min-width: 200px;
            text-align: center;
            transition: all 0.3s;
            border-bottom: 3px solid transparent;
        }
        
        .topic-box:hover {
            transform: translateY(-5px);
            border-bottom: 3px solid var(--accent);
        }
        
        .topic-icon {
            font-size: 2.5rem;
            margin-bottom: 1rem;
            color: var(--secondary);
        }
        
        .topic-box h3 {
            margin-bottom: 0.8rem;
        }
        
        .topic-box p {
            color: #a0a0a0;
            font-size: 0.9rem;
        }
        
        /* Login Modal */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.7);
            z-index: 1000;
            align-items: center;
            justify-content: center;
        }
        
        .modal-content {
            background-color: var(--card-bg);
            padding: 2rem;
            border-radius: 10px;
            width: 100%;
            max-width: 400px;
            position: relative;
        }
        
        .close-btn {
            position: absolute;
            top: 15px;
            right: 15px;
            font-size: 1.5rem;
            cursor: pointer;
            color: #a0a0a0;
            transition: color 0.3s;
        }
        
        .close-btn:hover {
            color: var(--accent);
        }
        
        .modal-header {
            text-align: center;
            margin-bottom: 1.5rem;
        }
        
        .modal-header h2 {
            font-size: 1.8rem;
            color: var(--accent);
        }
        
        .form-group {
            margin-bottom: 1.5rem;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            color: var(--text);
        }
        
        .form-input {
            width: 100%;
            padding: 0.8rem;
            border-radius: 5px;
            border: 1px solid #444;
            background-color: rgba(255, 255, 255, 0.1);
            color: var(--text);
            transition: all 0.3s;
        }
        
        .form-input:focus {
            outline: none;
            border-color: var(--secondary);
            box-shadow: 0 0 0 2px rgba(91, 108, 249, 0.3);
        }
        
        .form-btn {
            width: 100%;
            padding: 0.8rem;
            border: none;
            border-radius: 5px;
            background-color: var(--secondary);
            color: white;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
        }
        
        .form-btn:hover {
            background-color: var(--accent);
            color: var(--primary);
        }
        
        .form-footer {
            text-align: center;
            margin-top: 1rem;
            font-size: 0.9rem;
            color: #a0a0a0;
        }
        
        .form-footer a {
            color: var(--accent);
            text-decoration: none;
        }
        
        /* Footer */
        footer {
            background-color: var(--primary);
            padding: 3rem 0 1.5rem;
        }
        
        .footer-content {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            margin-bottom: 2rem;
        }
        
        .footer-column {
            width: 23%;
            min-width: 200px;
            margin-bottom: 1.5rem;
        }
        
        .footer-column h3 {
            color: var(--accent);
            margin-bottom: 1rem;
            font-size: 1.2rem;
        }
        
        .footer-column p {
            color: #a0a0a0;
            margin-bottom: 1rem;
            font-size: 0.9rem;
        }
        
        .footer-links {
            list-style: none;
        }
        
        .footer-links li {
            margin-bottom: 0.5rem;
        }
        
        .footer-links a {
            color: #a0a0a0;
            text-decoration: none;
            transition: color 0.3s;
            font-size: 0.9rem;
        }
        
        .footer-links a:hover {
            color: var(--accent);
        }
        
        .copyright {
            text-align: center;
            padding-top: 1.5rem;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            color: #a0a0a0;
            font-size: 0.9rem;
        }
        
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }
            
            .courses-grid {
                grid-template-columns: 1fr;
            }
            
            .topic-box {
                width: calc(50% - 1rem);
            }
            
            .footer-column {
                width: 48%;
            }
            
            .hero h1 {
                font-size: 2.5rem;
            }
        }
        
        @media (max-width: 576px) {
            .topic-box {
                width: 100%;
            }
            
            .footer-column {
                width: 100%;
            }
            
            .hero h1 {
                font-size: 2rem;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <nav>
                <div class="logo">
                    <div class="logo-icon">🛡️</div>
                    <div>Cyber<span>Learn</span></div>
                </div>
                <ul class="nav-links">
                    <li><a href="#home">Home</a></li>
                    <li><a href="#courses">Courses</a></li>
                    <li><a href="#topics">Topics</a></li>
                    <li><a href="#about">About</a></li>
                    <li><a href="#contact">Contact</a></li>
                </ul>
                <button class="login-btn" id="login-button">Login / Register</button>
            </nav>
        </div>
    </header>
    
    <section class="hero" id="home">
        <div class="hero-content container">
            <h1>Master <span>Cybersecurity</span> Skills For Free</h1>
            <p>Learn ethical hacking, network security, cryptography, and more with our comprehensive free courses designed for beginners and experts alike.</p>
            <div>
                <a href="#courses" class="cta-btn">Explore Courses</a>
                <a href="#topics" class="cta-btn outline">Browse Topics</a>
            </div>
        </div>
    </section>
    
    <section class="section" id="courses">
        <div class="container">
            <div class="section-header">
                <h2>Featured Courses</h2>
                <p>Start your cybersecurity journey with our most popular free courses</p>
            </div>
            <div class="courses-grid">
                <div class="course-card">
                    <div class="course-img">
                        <img src="/api/placeholder/300/180" alt="Cybersecurity Fundamentals">
                        <span class="course-level">Beginner</span>
                    </div>
                    <div class="course-content">
                        <h3>Cybersecurity Fundamentals</h3>
                        <p>Learn the basic concepts and principles of cybersecurity, including threats, vulnerabilities, and security controls.</p>
                        <div class="course-meta">
                            <span>12 Modules</span>
                            <span>4.8 ★★★★★</span>
                        </div>
                    </div>
                </div>
                <div class="course-card">
                    <div class="course-img">
                        <img src="/api/placeholder/300/180" alt="Ethical Hacking">
                        <span class="course-level">Intermediate</span>
                    </div>
                    <div class="course-content">
                        <h3>Ethical Hacking</h3>
                        <p>Master the techniques and tools used by white hat hackers to identify and fix security vulnerabilities.</p>
                        <div class="course-meta">
                            <span>15 Modules</span>
                            <span>4.9 ★★★★★</span>
                        </div>
                    </div>
                </div>
                <div class="course-card">
                    <div class="course-img">
                        <img src="/api/placeholder/300/180" alt="Network Security">
                        <span class="course-level">Intermediate</span>
                    </div>
                    <div class="course-content">
                        <h3>Network Security</h3>
                        <p>Learn how to secure networks, implement firewalls, and detect intrusion attempts in real-time.</p>
                        <div class="course-meta">
                            <span>14 Modules</span>
                            <span>4.7 ★★★★★</span>
                        </div>
                    </div>
                </div>
                <div class="course-card">
                    <div class="course-img">
                        <img src="/api/placeholder/300/180" alt="Web Application Security">
                        <span class="course-level">Advanced</span>
                    </div>
                    <div class="course-content">
                        <h3>Web Application Security</h3>
                        <p>Discover common web vulnerabilities and how to protect applications from attacks like XSS and CSRF.</p>
                        <div class="course-meta">
                            <span>16 Modules</span>
                            <span>4.8 ★★★★★</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
    
    <section class="section" id="topics" style="background-color: rgba(42, 46, 69, 0.5);">
        <div class="container">
            <div class="section-header">
                <h2>Cybersecurity Topics</h2>
                <p>Explore our comprehensive library of cybersecurity topics</p>
            </div>
            <div class="topics-container">
                <div class="topic-box">
                    <div class="topic-icon">🔐</div>
                    <h3>Cryptography</h3>
                    <p>Learn encryption techniques and cryptographic protocols to secure data.</p>
                </div>
                <div class="topic-box">
                    <div class="topic-icon">🔍</div>
                    <h3>Digital Forensics</h3>
                    <p>Discover methods for collecting and analyzing digital evidence.</p>
                </div>
                <div class="topic-box">
                    <div class="topic-icon">🛡️</div>
                    <h3>Malware Analysis</h3>
                    <p>Understand how to analyze and defend against malicious software.</p>
                </div>
                <div class="topic-box">
                    <div class="topic-icon">🌐</div>
                    <h3>Cloud Security</h3>
                    <p>Learn how to secure resources and data in cloud environments.</p>
                </div>
                <div class="topic-box">
                    <div class="topic-icon">📱</div>
                    <h3>Mobile Security</h3>
                    <p>Explore security challenges specific to mobile devices and applications.</p>
                </div>
                <div class="topic-box">
                    <div class="topic-icon">🤖</div>
                    <h3>IoT Security</h3>
                    <p>Understand security implications of Internet of Things devices.</p>
                </div>
                <div class="topic-box">
                    <div class="topic-icon">📊</div>
                    <h3>Security Analytics</h3>
                    <p>Learn to use data analytics for threat detection and prevention.</p>
                </div>
                <div class="topic-box">
                    <div class="topic-icon">👤</div>
                    <h3>Social Engineering</h3>
                    <p>Discover techniques used to manipulate people into divulging information.</p>
                </div>
            </div>
        </div>
    </section>
    
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>About CyberLearn</h3>
                    <p>CyberLearn provides free, high-quality cybersecurity education to help individuals develop the skills needed to protect digital assets and information systems.</p>
                </div>
                <div class="footer-column">
                    <h3>Quick Links</h3>
                    <ul class="footer-links">
                        <li><a href="#home">Home</a></li>
                        <li><a href="#courses">Courses</a></li>
                        <li><a href="#topics">Topics</a></li>
                        <li><a href="#about">About Us</a></li>
                        <li><a href="#contact">Contact</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Resources</h3>
                    <ul class="footer-links">
                        <li><a href="#">Blog</a></li>
                        <li><a href="#">Tutorials</a></li>
                        <li><a href="#">Tools</a></li>
                        <li><a href="#">Community</a></li>
                        <li><a href="#">FAQ</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Connect With Us</h3>
                    <ul class="footer-links">
                        <li><a href="#">Twitter</a></li>
                        <li><a href="#">LinkedIn</a></li>
                        <li><a href="#">GitHub</a></li>
                        <li><a href="#">Discord</a></li>
                        <li><a href="#">YouTube</a></li>
                    </ul>
                </div>
            </div>
            <div class="copyright">
                <p>&copy; 2025 CyberLearn. All rights reserved.</p>
            </div>
        </div>
    </footer>
    
    <!-- Login Modal -->
    <div class="modal" id="login-modal">
        <div class="modal-content">
            <span class="close-btn" id="close-modal">&times;</span>
            <div class="modal-header">
                <h2>Login to CyberLearn</h2>
            </div>
            <form id="login-form">
                <div class="form-group">
                    <label for="email">Email</label>
                    <input type="email" id="email" class="form-input" placeholder="Enter your email" required>
                </div>
                <div class="form-group">
                    <label for="password">Password</label>
                    <input type="password" id="password" class="form-input" placeholder="Enter your password" required>
                </div>
                <button type="submit" class="form-btn">Login</button>
                <div class="form-footer">
                    <p>Don't have an account? <a href="#" id="show-register">Register</a></p>
                </div>
            </form>
        </div>
    </div>
    
    <script>
        // Modal functionality
        const modal = document.getElementById('login-modal');
        const loginBtn = document.getElementById('login-button');
        const closeBtn = document.getElementById('close-modal');
        
        loginBtn.addEventListener('click', () => {
            modal.style.display = 'flex';
        });
        
        closeBtn.addEventListener('click', () => {
            modal.style.display = 'none';
        });
        
        window.addEventListener('click', (e) => {
            if (e.target === modal) {
                modal.style.display = 'none';
            }
        });
        
        // Form submission (for demonstration purposes)
        const loginForm = document.getElementById('login-form');
        loginForm.addEventListener('submit', (e) => {
            e.preventDefault();
            alert('Login functionality would be implemented in a real application.');
        });
    </script>
</body>
</html>
```

