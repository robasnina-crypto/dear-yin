<!DOCTYPE html>  
<html lang="en">  
<head>  
  <meta charset="UTF-8" />  
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />  
  <title>Dear Sun</title>  
  
  <style>  
    body {  
      margin: 0;  
      font-family: "Georgia", serif;  
      background: linear-gradient(180deg, #0f0f14, #1a132d);  
      color: #f5f5f5;  
      min-height: 100vh;  
      overflow: hidden;  
    }  
  
    /* Floating Stars */  
    .stars {  
      position: fixed;  
      inset: 0;  
      overflow: hidden;  
      pointer-events: none;  
      z-index: 0;  
    }  
  
    .star {  
      position: absolute;  
      width: 2px;  
      height: 2px;  
      background: rgba(255, 255, 255, 0.8);  
      border-radius: 50%;  
      animation: float linear infinite;  
    }  
  
    @keyframes float {  
      from {  
        transform: translateY(100vh);  
        opacity: 0;  
      }  
      10% { opacity: 1; }  
      to {  
        transform: translateY(-10vh);  
        opacity: 0;  
      }  
    }  
  
    /* Intro Screen */  
    .intro {  
      position: fixed;  
      inset: 0;  
      display: flex;  
      justify-content: center;  
      align-items: center;  
      background: radial-gradient(circle, #1c1c2b, #0f0f14);  
      cursor: pointer;  
      transition: opacity 1.2s ease;  
      z-index: 10;  
    }  
  
    .intro.hidden {  
      opacity: 0;  
      pointer-events: none;  
    }  
  
    .intro h1 {  
      font-weight: normal;  
      letter-spacing: 2px;  
      animation: pulse 2s infinite;  
    }  
  
    @keyframes pulse {  
      0% { opacity: 0.5; transform: scale(1); }  
      50% { opacity: 1; transform: scale(1.05); }  
      100% { opacity: 0.5; transform: scale(1); }  
    }  
  
    /* Letter */  
    .container {  
      position: relative;  
      z-index: 1;  
      display: flex;  
      justify-content: center;  
      align-items: center;  
      padding: 40px;  
      min-height: 100vh;  
    }  
  
    .letter {  
      max-width: 700px;  
      background: rgba(255, 255, 255, 0.06);  
      padding: 40px;  
      border-radius: 16px;  
      line-height: 1.9;  
      backdrop-filter: blur(6px);  
      box-shadow: 0 20px 60px rgba(255, 182, 193, 0.15);  
      opacity: 0;  
      transform: translateY(20px);  
      transition: opacity 1.5s ease, transform 1.5s ease;  
    }  
  
    .letter.visible {  
      opacity: 1;  
      transform: translateY(0);  
    }  
  
    h2 {  
      text-align: center;  
      font-weight: normal;  
      margin-bottom: 30px;  
      letter-spacing: 1px;  
      color: #ffd6e8;  
    }  
  
    .signature {  
      margin-top: 30px;  
      text-align: right;  
      font-style: italic;  
      color: #ffc1dc;  
    }  
  
    @media (max-width: 600px) {  
      .letter {  
        padding: 25px;  
      }  
    }  
  </style>  
</head>  
  
<body>  
  
  <!-- Floating Stars -->  
  <div class="stars" id="stars"></div>  
  
  <!-- Intro -->  
  <div class="intro" id="intro">  
    <h1>Click to Read</h1>  
  </div>  
  
  <!-- Background Music -->  
  <audio id="bgm" loop>  
    <source src="https://cdn.pixabay.com/audio/2022/10/25/audio_946b8a1f0c.mp3" type="audio/mpeg">  
  </audio>  
  
  <!-- Letter -->  
  <div class="container">  
    <div class="letter" id="letter">  
      <h2>Dear Sun,</h2>  
  
      <p>  
        I will be vague with you: all of my writings—pubmat and songs posted on my notes—  
        are all about you. I know it’s selfish to confess this early on and ruin the  
        established friendship we have with each other, and knowing that you already have  
        someone you like, I know I shouldn’t have continued with this confession.  
      </p>  
  
      <p>  
        But I also don’t want to keep my hopes up for something that I know will never come;  
        I just want to express that my feelings for you are genuine and not infatuation,  
        because if it actually was false feelings, then I wouldn’t have stayed up so late  
        to create those pubmats just for you to notice me.  
      </p>  
  
      <p>  
        I know that after this confession everything will be irreversible; hopefully you  
        take my feelings into consideration and reject me if you see me only as a friend  
        and nothing else. I don’t want to lose my mind admiring something so out of reach.  
      </p>  
  
      <p>  
        My confession won’t be long, but just know that I like you from the way you speak,  
        treat others, and manage to bring light into any room you walk in. Hopefully, our  
        friendship remains intact after this, and we can act as if I never sent this.  
      </p>  
  
      <p>Thank you ^^</p>  
  
      <div class="signature">  
        from<br>  
        Roblox  
      </div>  
    </div>  
  </div>  
  
  <script>  
    const intro = document.getElementById("intro");  
    const letter = document.getElementById("letter");  
    const bgm = document.getElementById("bgm");  
    const starsContainer = document.getElementById("stars");  
  
    for (let i = 0; i < 60; i++) {  
      const star = document.createElement("div");  
      star.classList.add("star");  
      star.style.left = Math.random() * 100 + "vw";  
      star.style.animationDuration = 10 + Math.random() * 20 + "s";  
      star.style.animationDelay = Math.random() * 20 + "s";  
      star.style.opacity = Math.random();  
      starsContainer.appendChild(star);  
    }  
  
    intro.addEventListener("click", () => {  
      intro.classList.add("hidden");  
      letter.classList.add("visible");  
      bgm.volume = 0.4;  
      bgm.play();  
    });  
  </script>  
  
</body>  
</html>  
