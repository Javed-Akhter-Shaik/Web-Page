<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>VR Portfolio - Javed</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: linear-gradient(to bottom, #0f2027, #203a43, #2c5364);
      color: #fff;
      text-align: center;
    }

    /* Navbar */
    nav {
      background: rgba(0,0,0,0.8);
      padding: 15px;
      display: flex;
      justify-content: center;
      gap: 40px;
      position: sticky;
      top: 0;
      z-index: 1000;
    }
    nav a {
      text-decoration: none;
      color: #fff;
      font-weight: bold;
      font-size: 1.1em;
    }
    nav a:hover {
      color: #00ffcc;
    }

    h1 {
      margin-top: 40px;
      font-size: 2.5em;
    }
    h2 {
      margin: 30px 0 15px;
    }

    /* Portfolio grid */
    .portfolio-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(420px, 1fr));
      gap: 20px;
      padding: 40px;
      max-width: 1300px;
      margin: 0 auto;
    }

    .project-card {
      background: rgba(0,0,0,0.7);
      border-radius: 15px;
      padding: 20px;
      text-align: left;
      transition: transform 0.2s;
    }
    .project-card:hover {
      transform: translateY(-5px);
    }
    .project-card h3 {
      color: #00ffcc;
    }
    .project-video {
      width: 100%;
      height: 250px;
      border-radius: 10px;
    }
    .project-details {
      margin-top: 15px;
      font-size: 0.95em;
      line-height: 1.6em;
    }
    .tech-stack {
      margin-top: 10px;
      font-style: italic;
      color: #b3e6ff;
    }

    /* About */
    .about {
      margin: 50px auto;
      max-width: 900px;
      padding: 20px;
      font-size: 1.1em;
    }

    /* Resume button */
    .resume-btn {
      background: #00ffcc;
      color: #000;
      font-weight: bold;
      padding: 12px 25px;
      border-radius: 8px;
      border: none;
      cursor: pointer;
      font-size: 1em;
    }
    .resume-btn:hover {
      background: #00cc99;
    }

    /* Footer */
    footer {
      margin-top: 50px;
      padding: 20px;
      background: rgba(0,0,0,0.8);
    }
    footer a {
      margin: 0 15px;
      text-decoration: none;
      color: #00ffcc;
    }
  </style>
</head>
<body>

  <nav>
    <a href="#portfolio">Portfolio</a>
    <a href="#about">About</a>
    <a href="#contact">Contact</a>
  </nav>

  <h1>Hi, I am Javed</h1>
  <p>XR Developer – VR/AR Prototyper – AI-driven Robotics</p>

  <h2 id="portfolio">Portfolio</h2>
  <div class="portfolio-grid">

    <!-- Example Project -->
    <div class="project-card">
      <iframe class="project-video" src="https://www.youtube.com/embed/YOUR_VIDEO_ID" frameborder="0" allowfullscreen></iframe>
      <h3>Interactive Gear Box Assembly</h3>
      <div class="project-details">
        Step-by-step immersive VR guide for gearbox assembly.  
        Enhances learning, improves efficiency in tasks, and reduces errors in gearbox maintenance.
        <p class="tech-stack">Tech stack: Unity3D, C#, VR Interaction, Physics-based Assembly</p>
      </div>
    </div>

    <div class="project-card">
      <img class="project-video" src="gearbox_inspection.png" alt="Inspection Project Snapshot">
      <h3>Inspection of Mechanical Components in VR</h3>
      <div class="project-details">
        Interactive VR environment to compare master and target models in real-time.  
        Missing components are detected and highlighted instantly.
        <p class="tech-stack">Tech stack: Unity3D, VR UI, Real-time Comparison, Physics Colliders</p>
      </div>
    </div>

    <div class="project-card">
      <img class="project-video" src="measurement.png" alt="Measurement Snapshot">
      <h3>Real-time Measurement</h3>
      <div class="project-details">
        Build an immersive VR environment to interact with components and dynamically measure distances and dimensions in real-time.
        <p class="tech-stack">Tech stack: Unity3D, VR Interaction, Measurement Tools</p>
      </div>
    </div>

    <div class="project-card">
      <img class="project-video" src="npc.png" alt="NPC Snapshot">
      <h3>Smart Non-Player Character (NPC)</h3>
      <div class="project-details">
        Voice-driven dialogue with intelligent NPCs in VR. Integrates Speech-to-Text (STT), LLM processing, and Text-to-Speech (TTS).
        <p class="tech-stack">Tech stack: Unity3D, HuggingFace, Groq Llama, Speechify</p>
      </div>
    </div>

    <div class="project-card">
      <img class="project-video" src="tabletennis.png" alt="VR Table Tennis Snapshot">
      <h3>VR Table Tennis</h3>
      <div class="project-details">
        Physics-accurate immersive VR table tennis experience.  
        Simulates natural feel, responsiveness, and excitement of real-world ping pong.
        <p class="tech-stack">Tech stack: Unity3D, VR Physics, Spatial Audio</p>
      </div>
    </div>

    <div class="project-card">
      <img class="project-video" src="gorilla.png" alt="Gorilla vs 100 Men Snapshot">
      <h3>Gorilla vs 100 Men</h3>
      <div class="project-details">
        Action-packed VR combat game where players control a gorilla against waves of enemies. Features physics-based grabbing and throwing.
        <p class="tech-stack">Tech stack: Unity3D, Physics Hand Interaction, VR Combat</p>
      </div>
    </div>

  </div>

  <h2 id="about">About</h2>
  <div class="about">
    Experienced XR Developer specializing in Unity, C#, and AI-driven robotics.  
    Passionate about building immersive VR/AR applications and mentoring XR development.  
    Always eager to expand knowledge and collaborate on innovative projects.
    <br><br>
    <button class="resume-btn">Download Resume</button>
  </div>

  <h2 id="contact">Contact</h2>
  <p>Feel free to reach out, I’d love to connect with you!<br>
  Based in: Chennai, India</p>

  <footer>
    <a href="#">GitHub</a> |
    <a href="#">LinkedIn</a> |
    <a href="mailto:your@email.com">Email</a>
  </footer>

</body>
</html>
