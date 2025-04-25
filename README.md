# Portfolio-Project


<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Parth Deshmukh - Portfolio</title>
  <style>
    :root {
      --bg-color: #ffffff;
      --text-color: #2d2e32;
      --primary: #0051ff;
      --secondary: #f8f9fa;
      --border-color: rgba(0,0,0,0.1);
      --card-bg: #f9f9f9;
    }

    [data-theme="dark"] {
      --bg-color: #121212;
      --text-color: #e0e0e0;
      --primary: #5e8bff;
      --secondary: #1e1e1e;
      --border-color: rgba(255,255,255,0.1);
      --card-bg: #1e1e1e;
    }

    body {
      font-family: 'Segoe UI', sans-serif;
      margin: 0;
      padding: 0;
      background-color: var(--bg-color);
      color: var(--text-color);
      text-align: center;
      transition: all 0.3s ease;
    }

    .name-container {
      position: relative;
      margin: 1rem 0;
      perspective: 1000px;
    }

    .name-gradient {
      background: linear-gradient(45deg, #0051ff, #00c3ff, #ff00ff);
      background-size: 200% 200%;
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      animation: gradient-flow 8s ease infinite;
      font-family: 'Segoe UI', sans-serif;
      font-weight: 700;
      font-size: 3.5rem;
      letter-spacing: -1.5px;
    }

    @keyframes gradient-flow {
      0% { background-position: 0% 50%; }
      50% { background-position: 100% 50%; }
      100% { background-position: 0% 50%; }
    }

    .name-underline {
      width: 60%;
      height: 4px;
      background: var(--primary);
      margin: 0 auto;
      border-radius: 2px;
      transform: scaleX(0);
      animation: underline-grow 1s ease-out forwards;
      animation-delay: 0.5s;
    }

    @keyframes underline-grow {
      from { transform: scaleX(0); }
      to { transform: scaleX(1); }
    }

    .greeting {
      font-size: 1.8rem;
      color: var(--text-color);
      margin-bottom: -1rem;
      opacity: 0;
      animation: fadeIn 1s ease forwards;
      animation-delay: 0.3s;
    }

    .aspiration {
      font-size: 1.4rem;
      color: var(--primary);
      margin: 1.5rem 0;
      font-weight: 500;
      opacity: 0;
      animation: slideUp 1s ease forwards;
      animation-delay: 1s;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(10px); }
      to { opacity: 1; transform: translateY(0); }
    }

    @keyframes slideUp {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }

    nav {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 20px 10%;
      border-bottom: 1px solid var(--border-color);
    }

    .logo {
      font-weight: 800;
      font-size: 22px;
      color: var(--text-color);
    }

    .nav-links {
      list-style: none;
      display: flex;
      gap: 30px;
      margin: 0;
      padding: 0;
    }

    .nav-links li a {
      text-decoration: none;
      color: var(--text-color);
      font-size: 16px;
      transition: color 0.3s;
      position: relative;
    }

    .nav-links li a:hover {
      color: var(--primary);
    }

    .theme-toggle {
      background: var(--card-bg);
      border: 1px solid var(--border-color);
      cursor: pointer;
      padding: 8px;
      border-radius: 50%;
      width: 40px;
      height: 40px;
      margin-left: 20px;
      transition: all 0.3s ease;
    }

    .theme-toggle:hover {
      transform: rotate(15deg);
      border-color: var(--primary);
    }

    .hero {
      padding: 80px 20px 40px;
      max-width: 800px;
      margin: 0 auto;
    }

    .hero h1 {
      font-size: 24px;
      font-weight: 600;
      margin: 2rem auto;
      line-height: 1.4;
      max-width: 700px;
    }

    .hero button {
      background: var(--text-color);
      color: var(--bg-color);
      padding: 12px 30px;
      font-size: 16px;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      transition: all 0.3s ease;
      font-weight: 600;
    }

    .hero button:hover {
      background: var(--primary);
      transform: translateY(-2px);
    }

    .bio {
      max-width: 800px;
      margin: 40px auto;
      padding: 25px;
      font-size: 17px;
      line-height: 1.6;
      background-color: var(--card-bg);
      border-radius: 12px;
      border: 1px solid var(--border-color);
      text-align: left;
    }

    .bio h2 {
      font-size: 22px;
      margin-bottom: 15px;
      color: var(--primary);
      text-align: center;
    }

    .about-container {
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 30px;
      margin-top: 20px;
    }

    .about-image {
      flex-shrink: 0;
    }

    .profile-photo {
      width: 250px;
      height: 250px;
      border-radius: 50%;
      object-fit: cover;
      object-position: top;
      border: 3px solid var(--primary);
    }

    .about-content {
      max-width: 500px;
    }

    .projects {
      display: flex;
      justify-content: center;
      flex-wrap: wrap;
      gap: 30px;
      padding: 40px 10%;
    }

    .project {
      background: var(--card-bg);
      padding: 25px;
      width: 280px;
      border: 1px solid var(--border-color);
      border-radius: 12px;
      text-align: left;
      transition: transform 0.3s ease;
    }

    .project:hover {
      transform: translateY(-5px);
    }

    .project h2 {
      color: var(--primary);
      margin-top: 0;
      font-size: 18px;
    }

    #skills {
      padding: 40px 10%;
    }

    .skill-item {
      background: var(--card-bg);
      padding: 20px;
      margin: 15px auto;
      width: 60%;
      border-radius: 12px;
      border: 1px solid var(--border-color);
    }

    .skill-item h4 {
      color: var(--primary);
      margin-bottom: 10px;
    }

    .icon {
      width: 40px;
      height: 40px;
      transition: all 0.3s ease;
    }

    [data-theme="dark"] .icon {
      filter: invert(0.9);
    }

    .skills-container {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
      justify-content: center;
    }
    .skill-badge {
      background-color: var(--primary);
      color: #fff;
      padding: 8px 16px;
      border-radius: 20px;
      font-size: 14px;
      font-weight: 500;
      transition: transform 0.3s ease;
    }
    .skill-badge:hover {
      transform: scale(1.05);
    }

    #certifications {
      padding: 40px 10%;
      margin-top: 20px;
    }
    #certifications h2 {
      font-size: 26px;
      color: var(--primary);
      margin-bottom: 20px;
      text-align: center;
    }
    .certifications-container {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 20px;
    }
    .certification-item {
      background: var(--card-bg);
      border: 1px solid var(--border-color);
      border-radius: 12px;
      padding: 20px;
      width: 280px;
      text-align: left;
      transition: transform 0.3s ease;
    }
    .certification-item:hover {
      transform: translateY(-5px);
    }
    .certification-item h3 {
      color: var(--primary);
      margin: 0 0 10px;
      font-size: 20px;
    }
    .certification-item p {
      font-size: 15px;
      margin-bottom: 15px;
    }
    .cert-btn {
      background: #6a0dad;
      color: #fff;
      border: none;
      padding: 8px 14px;
      border-radius: 6px;
      text-decoration: none;
      cursor: pointer;
      transition: background 0.3s ease;
      display: inline-block;
    }
    .cert-btn:hover {
      background: #5a0dad;
    }

    /* Enhanced Interests Section */
    #interests {
      padding: 40px 10%;
      margin-top: 20px;
    }
    #interests h2 {
      font-size: 26px;
      color: var(--primary);
      margin-bottom: 30px;
      text-align: center;
    }
    .interests-container {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 25px;
      padding: 0 15px;
    }
    .interest-item {
      position: relative;
      overflow: hidden;
      border-radius: 15px;
      border: 1px solid var(--border-color);
      background: var(--card-bg);
      transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
    }
    .interest-item:hover {
      transform: translateY(-7px);
      box-shadow: 0 8px 12px rgba(0, 0, 0, 0.15);
    }
    .interest-item img {
      width: 100%;
      height: 220px;
      object-fit: cover;
      object-position: center;
      border-bottom: 3px solid var(--primary);
    }
    .interest-item p {
      padding: 15px;
      margin: 0;
      font-size: 1.1rem;
      font-weight: 600;
      text-align: center;
      color: var(--text-color);
    }

    .contact-form {
      padding: 40px 10%;
      background-color: var(--secondary);
    }

    .contact-form input,
    .contact-form textarea {
      background: var(--card-bg);
      color: var(--text-color);
      border: 1px solid var(--border-color);
      width: 100%;
      max-width: 500px;
      margin: 8px 0;
      padding: 12px;
      border-radius: 6px;
    }

    footer {
      padding: 20px;
      font-size: 14px;
      color: var(--text-color);
      border-top: 1px solid var(--border-color);
      margin-top: 40px;
    }

    @media (max-width: 768px) {
      nav {
        padding: 20px 5%;
      }
      .theme-toggle {
        margin-left: 10px;
      }
      .name-gradient {
        font-size: 2.5rem;
      }
      .skill-item {
        width: 90%;
      }
      .greeting {
        font-size: 1.5rem;
      }
      .aspiration {
        font-size: 1.2rem;
      }
      .about-container {
        flex-direction: column;
        text-align: center;
      }
      .interests-container {
        grid-template-columns: 1fr;
      }
    }
  </style>
</head>
<body>
  <nav>
    <div class="logo">Parth Deshmukh</div>
    <div style="display: flex; align-items: center;">
      <ul class="nav-links">
        <li><a href="#home">Home</a></li>
        <li><a href="#about">About</a></li>
        <li><a href="#projects">Projects</a></li>
        <li><a href="#skills">Skills</a></li>
        <li><a href="#certifications">Certifications</a></li>
        <li><a href="#interests">Interests</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
      <button class="theme-toggle">🌙</button>
    </div>
  </nav>

  <section class="hero" id="home">
    <h2 class="greeting">Hi I'm</h2>
    <div class="name-container">
      <div class="name-gradient">Parth Deshmukh</div>
      <div class="name-underline"></div>
    </div>
    <p class="aspiration">Aspiring Full-Stack Developer & Machine Learning Enthusiast</p>
    <h1>Turning data into insights and ideas into reality through intelligent code</h1>
    <button>Explore More</button>
  </section>

  <section class="bio" id="about">
    <h2>About Me</h2>
    <div class="about-container">
      <div class="about-image">
        <img src="profile.jpg" alt="Profile Photo" class="profile-photo">
      </div>
      <div class="about-content">
        <p>
          Hi, I'm Parth — a first-year B.Tech student in the IT branch with a strong passion for computer applications and technology.  
          I'm driven by curiosity, always eager to learn, and committed to giving 100% to every project I take on.  
          Whether it's coding, building systems, or exploring new tools, I’m excited to grow my skills and contribute meaningfully to the world of tech.
        </p>
      </div>
    </div>
  </section>

  <section class="projects" id="projects">
    <div class="project">
      <h2>Student Management System</h2>
      <p><strong>Tech Stack:</strong> C, Oracle Database</p>
      <p>A console-based app to manage student records: enrollment, grades, attendance.</p>
      <ul>
        <li>Add, update, delete records</li>
        <li>Attendance tracking</li>
        <li>Grade calculation</li>
        <li>Secure login for admin/teachers</li>
      </ul>
    </div>

    <div class="project">
      <h2>Library Management System</h2>
      <p><strong>Tech Stack:</strong> C, Oracle Database</p>
      <p>System to manage books, student memberships, and issue/return logs.</p>
      <ul>
        <li>Book search and categorization</li>
        <li>Fine calculation</li>
        <li>Admin dashboard with reports</li>
      </ul>
    </div>

    <div class="project">
      <h2>Expense Tracker</h2>
      <p><strong>Tech Stack:</strong> C, Oracle Database</p>
      <p>CLI tool for tracking daily expenses and monthly analysis.</p>
      <ul>
        <li>Expense categorization</li>
        <li>Spending analysis</li>
        <li>Data encryption</li>
      </ul>
    </div>
  </section>

  <section id="skills">
    <h2>Skills</h2>

    <div class="skill-item">
      <h4><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/c/c-original.svg" class="icon" alt="C"> Programming Languages</h4>
      <div class="icon-row">
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" alt="Python" class="icon" />
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/java/java-original.svg" alt="Java" class="icon" />
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/cplusplus/cplusplus-original.svg" alt="C++" class="icon" />
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg" alt="JavaScript" class="icon" />
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg" alt="HTML" class="icon" />
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg" alt="CSS" class="icon" />
      </div>
    </div>

    <div class="skill-item">
      <h4><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg" class="icon" alt="Git"> Software Tools</h4>
      <div class="icon-row">
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg" alt="Git" class="icon" />
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vscode/vscode-original.svg" alt="VS Code" class="icon" />
        <img src="https://img.icons8.com/color/48/000000/microsoft-office-2019.png" alt="MS Office" class="icon" />
        <img src="https://img.icons8.com/color/48/000000/adobe-photoshop.png" alt="Photoshop" class="icon" />
      </div>
    </div>

    <div class="skill-item">
      <h4>🧠 Soft Skills</h4>
      <div class="skills-container">
        <span class="skill-badge">Teamwork</span>
        <span class="skill-badge">Problem Solving</span>
        <span class="skill-badge">Communication</span>
        <span class="skill-badge">Time Management</span>
        <span class="skill-badge">Leadership</span>
      </div>
    </div>

    <div class="skill-item">
      <h4><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/react/react-original.svg" class="icon" alt="React"> Web Development</h4>
      <div class="icon-row">
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/react/react-original.svg" alt="React" class="icon" />
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nodejs/nodejs-original.svg" alt="Node.js" class="icon" />
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/express/express-original.svg" alt="Express" class="icon" />
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mongodb/mongodb-original.svg" alt="MongoDB" class="icon" />
      </div>
    </div>
  </section>

  <section id="certifications">
    <h2>Certifications</h2>
    <div class="certifications-container">
      <div class="certification-item">
        <h3>Oracle SQL</h3>
        <p>Completed via Great Learning Academy – December 2024</p>
        <a href="Parth%20rajesh%20deshmukh.pdf" target="_blank" class="cert-btn">View Certificate</a>
      </div>
      <div class="certification-item">
        <h3>AI Workshop</h3>
        <p>Workshop on Exploring AI for the Next-Gen Engineer – April 12, 2025</p>
        <a href="Exploring%20AI%20Workshop%20Certificate.pdf" target="_blank" class="cert-btn">View Certificate</a>
      </div>
      <div class="certification-item">
        <h3>Python Essentials 1</h3>
        <p>Completed via MIT Academy of Engineering, Alandi Pune through Cisco Networking Academy – 08 Apr 2025</p>
        <a href="_certificate_202401080071-mitaoe-ac-in_a328a69c-3e98-452d-8d27-1fa4d301065f.pdf" target="_blank" class="cert-btn">View Certificate</a>
      </div>
      <div class="certification-item">
        <h3>Python Essentials 2</h3>
        <p>Completed via Networking Academy through the Cisco Networking Academy program – 27 Mar 2025</p>
        <a href="_certificate_202401080071-mitaoe-ac-in_fb8437d1-6050-47c9-9bfb-d2194717754e.pdf" target="_blank" class="cert-btn">View Certificate</a>
      </div>
    </div>
  </section>

  <section id="interests">
    <h2>My Interests</h2>
    <div class="interests-container">
      <div class="interest-item">
        <img src="space_exploration.jpg" alt="Space Exploration">
        <p>Space Exploration</p>
      </div>
      <div class="interest-item">
        <img src="code_development.jpg" alt="Code Development">
        <p>Code Development</p>
      </div>
      <div class="interest-item">
        <img src="machine_learning.jpg" alt="Machine Learning">
        <p>Machine Learning</p>
      </div>
      <div class="interest-item">
        <img src="tech_innovation.jpg" alt="Technology Innovation">
        <p>Technology Innovation</p>
      </div>
    </div>
  </section>

  <section class="contact-form" id="contact">
    <h2>Contact Me</h2>
    <form>
      <input type="text" placeholder="Your Name" required />
      <input type="email" placeholder="Your Email" required />
      <textarea placeholder="Your Message" rows="5" required></textarea>
      <button type="submit">Send</button>
    </form>
  </section>

  <footer>
    <p>© 2025 Parth Deshmukh. All rights reserved.</p>
  </footer>

  <script>
    const themeToggle = document.querySelector('.theme-toggle');
    const body = document.body;

    const currentTheme = localStorage.getItem('theme') || 'light';
    body.setAttribute('data-theme', currentTheme);
    themeToggle.textContent = currentTheme === 'dark' ? '☀' : '🌙';

    themeToggle.addEventListener('click', () => {
      const isDark = body.getAttribute('data-theme') === 'dark';
      body.setAttribute('data-theme', isDark ? 'light' : 'dark');
      themeToggle.textContent = isDark ? '🌙' : '☀';
      localStorage.setItem('theme', isDark ? 'light' : 'dark');
    });
  </script>
</body>
</html>
