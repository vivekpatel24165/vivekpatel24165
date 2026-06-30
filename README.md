<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>About Me - Enhanced</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap');

    :root {
      --primary: #00f5ff;
      --accent: #ff00ff;
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Inter', sans-serif;
      background: linear-gradient(135deg, #0a0a0a, #1a0033);
      color: #e0e0e0;
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 20px;
      overflow: hidden;
    }

    .profile-card {
      background: rgba(15, 15, 35, 0.95);
      border-radius: 24px;
      max-width: 620px;
      width: 100%;
      padding: 48px 40px;
      box-shadow: 
        0 0 60px rgba(0, 245, 255, 0.3),
        inset 0 0 40px rgba(255, 0, 255, 0.1);
      border: 1px solid rgba(0, 245, 255, 0.2);
      position: relative;
      overflow: hidden;
    }

    .profile-card::before {
      content: '';
      position: absolute;
      top: -50%;
      left: -50%;
      width: 200%;
      height: 200%;
      background: radial-gradient(circle, rgba(0,245,255,0.08) 0%, transparent 70%);
      animation: rotateGlow 25s linear infinite;
      pointer-events: none;
    }

    @keyframes rotateGlow {
      0% { transform: rotate(0deg); }
      100% { transform: rotate(360deg); }
    }

    .header {
      text-align: center;
      margin-bottom: 40px;
    }

    .avatar {
      width: 120px;
      height: 120px;
      background: linear-gradient(45deg, #00f5ff, #ff00ff);
      border-radius: 50%;
      margin: 0 auto 20px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 48px;
      box-shadow: 
        0 0 40px #00f5ff,
        0 0 80px rgba(0, 245, 255, 0.6);
      animation: pulseGlow 3s ease-in-out infinite;
    }

    @keyframes pulseGlow {
      0%, 100% { box-shadow: 0 0 40px #00f5ff, 0 0 80px rgba(0, 245, 255, 0.6); }
      50% { box-shadow: 0 0 60px #ff00ff, 0 0 100px rgba(255, 0, 255, 0.7); }
    }

    h1 {
      font-size: 2.8rem;
      background: linear-gradient(90deg, #00f5ff, #ff00ff);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      margin-bottom: 8px;
      animation: titleGlow 4s ease-in-out infinite alternate;
    }

    @keyframes titleGlow {
      from { text-shadow: 0 0 20px #00f5ff; }
      to { text-shadow: 0 0 40px #ff00ff; }
    }

    .subtitle {
      color: #aaa;
      font-size: 1.1rem;
      margin-bottom: 32px;
    }

    .section {
      margin-bottom: 42px;
    }

    h2 {
      color: var(--primary);
      font-size: 1.4rem;
      margin-bottom: 18px;
      text-transform: uppercase;
      letter-spacing: 2px;
      position: relative;
      display: inline-block;
    }

    h2::after {
      content: '';
      position: absolute;
      bottom: -6px;
      left: 0;
      width: 60%;
      height: 3px;
      background: linear-gradient(to right, var(--primary), transparent);
      border-radius: 3px;
    }

    ul {
      list-style: none;
    }

    li {
      padding: 12px 0;
      display: flex;
      align-items: flex-start;
      gap: 14px;
      font-size: 1.05rem;
      opacity: 0;
      transform: translateY(20px);
      animation: fadeInUp 0.6s forwards;
      position: relative;
    }

    li:nth-child(1) { animation-delay: 0.1s; }
    li:nth-child(2) { animation-delay: 0.2s; }
    li:nth-child(3) { animation-delay: 0.3s; }
    li:nth-child(4) { animation-delay: 0.4s; }
    li:nth-child(5) { animation-delay: 0.5s; }
    li:nth-child(6) { animation-delay: 0.6s; }
    li:nth-child(7) { animation-delay: 0.7s; }

    @keyframes fadeInUp {
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    li::before {
      content: '▶';
      color: var(--primary);
      font-size: 1.1rem;
      flex-shrink: 0;
      animation: glowArrow 2s ease-in-out infinite;
    }

    @keyframes glowArrow {
      0%, 100% { text-shadow: 0 0 8px #00f5ff; }
      50% { text-shadow: 0 0 16px #ff00ff; }
    }

    .tech-stack {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(80px, 1fr));
      gap: 24px;
      margin-top: 20px;
    }

    .tech-item {
      text-align: center;
      transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
      padding: 16px 12px;
      border-radius: 16px;
      background: rgba(255,255,255,0.03);
    }

    .tech-item:hover {
      transform: translateY(-12px) scale(1.08);
      background: rgba(0, 245, 255, 0.1);
      box-shadow: 
        0 0 30px rgba(0, 245, 255, 0.5),
        0 20px 40px rgba(0, 0, 0, 0.4);
    }

    .tech-logo {
      width: 62px;
      height: 62px;
      margin: 0 auto 12px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 42px;
      filter: drop-shadow(0 0 12px currentColor);
      transition: all 0.3s ease;
    }

    .tech-item:hover .tech-logo {
      filter: drop-shadow(0 0 25px currentColor);
      transform: scale(1.15);
    }

    .tech-name {
      font-size: 0.95rem;
      font-weight: 500;
      color: #ddd;
    }
  </style>
</head>
<body>
  <div class="profile-card">
    <div class="header">
      <div class="avatar">👨‍💻</div>
      <h1>Hi, I'm [Your Name]</h1>
      <p class="subtitle">Computer Science Student • Aspiring Software Engineer</p>
    </div>

    <div class="section">
      <h2>About Me</h2>
      <ul>
        <li>🎓 Computer Science student from Nepal, currently studying in India.</li>
        <li>💡 Passionate about building software that solves real-world problems.</li>
        <li>📱 Developing Android applications using Flutter, Firebase, and REST APIs.</li>
        <li>💻 Strong foundation in C++, HTML, CSS, and modern development tools.</li>
        <li>🎨 Comfortable designing user interfaces with Figma and developing in VS Code.</li>
        <li>📚 Currently strengthening my knowledge of Data Structures & Algorithms and full-stack development.</li>
        <li>🧠 Calm under pressure, disciplined, and committed to continuous improvement.</li>
        <li>🎯 Goal: To become a Software Engineer at a world-class technology company.</li>
      </ul>
    </div>

    <div class="section">
      <h2>⚡ Tech Stack</h2>
      <div class="tech-stack">
        <div class="tech-item">
          <div class="tech-logo" style="color: #0052cc;">C++</div>
          <div class="tech-name">C++</div>
        </div>
        <div class="tech-item">
          <div class="tech-logo" style="color: #00b4f0;">▶</div>
          <div class="tech-name">Dart</div>
        </div>
        <div class="tech-item">
          <div class="tech-logo" style="color: #e34f26;">&lt;/&gt;</div>
          <div class="tech-name">HTML/CSS</div>
        </div>
        <div class="tech-item">
          <div class="tech-logo" style="color: #02569B;">🦋</div>
          <div class="tech-name">Flutter</div>
        </div>
        <div class="tech-item">
          <div class="tech-logo" style="color: #FFCA28;">🔥</div>
          <div class="tech-name">Firebase</div>
        </div>
        <div class="tech-item">
          <div class="tech-logo" style="color: #00f5ff;">🔗</div>
          <div class="tech-name">REST APIs</div>
        </div>
        <div class="tech-item">
          <div class="tech-logo" style="color: #f05032;">Git</div>
          <div class="tech-name">Git</div>
        </div>
        <div class="tech-item">
          <div class="tech-logo" style="color: #00b4f0;">VS</div>
          <div class="tech-name">VS Code</div>
        </div>
        <div class="tech-item">
          <div class="tech-logo" style="color: #f24e1e;">Figma</div>
          <div class="tech-name">Figma</div>
        </div>
      </div>
    </div>
  </div>

  <script>
    // Simple interaction - click on card for extra glow burst
    document.querySelector('.profile-card').addEventListener('click', function(e) {
      const card = this;
      card.style.transition = 'box-shadow 0.4s';
      card.style.boxShadow = `
        0 0 100px rgba(0, 245, 255, 0.8),
        0 0 140px rgba(255, 0, 255, 0.6)
      `;
      setTimeout(() => {
        card.style.boxShadow = `
          0 0 60px rgba(0, 245, 255, 0.3),
          inset 0 0 40px rgba(255, 0, 255, 0.1)
        `;
      }, 800);
    });
  </script>
</body>
</html>
