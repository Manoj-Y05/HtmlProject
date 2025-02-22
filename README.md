<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pha5e Hero Section</title>
    <link rel="stylesheet" href="styles.css">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js" defer></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/ScrollTrigger.min.js" defer></script>
    <script src="script.js" defer></script>
    <style>
        body {
            margin: 0;
            font-family: Arial, sans-serif;
            background: #000;
            color: #fff;
            overflow: hidden;
        }
        .hero {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            text-align: center;
            background: linear-gradient(45deg, #1e1e1e, #333);
            position: relative;
            overflow: hidden;
        }
        .hero-content {
            position: relative;
            z-index: 2;
        }
        .title {
            font-size: 3rem;
            font-weight: bold;
        }
        .subtitle {
            font-size: 1.5rem;
            margin-top: 10px;
        }
        .cta {
            margin-top: 20px;
            padding: 10px 20px;
            font-size: 1rem;
            background: #ff5722;
            border: none;
            color: white;
            cursor: pointer;
            transition: transform 0.3s;
        }
        .cta:hover {
            transform: scale(1.1);
        }
        .background-elements {
            position: absolute;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
        }
        .circle {
            position: absolute;
            width: 100px;
            height: 100px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
        }
    </style>
</head>
<body>
    <section class="hero">
        <div class="background-elements">
            <div class="circle" style="top: 10%; left: 20%;"></div>
            <div class="circle" style="top: 50%; left: 70%;"></div>
            <div class="circle" style="top: 80%; left: 40%;"></div>
        </div>
        <div class="hero-content">
            <h1 class="title">Welcome to Pha5e</h1>
            <p class="subtitle">Experience innovation and creativity.</p>
            <button class="cta">Get Started</button>
        </div>
    </section>
    <script>
        gsap.from(".title", { opacity: 0, y: -50, duration: 1, ease: "power2.out" });
        gsap.from(".subtitle", { opacity: 0, y: 50, duration: 1, delay: 0.5, ease: "power2.out" });
        gsap.from(".cta", { opacity: 0, scale: 0.8, duration: 1, delay: 1, ease: "elastic.out(1, 0.5)" });
        
        document.addEventListener("mousemove", (e) => {
            document.querySelectorAll(".circle").forEach(circle => {
                const speed = circle.getAttribute("data-speed") || 5;
                const x = (window.innerWidth - e.pageX * speed) / 100;
                const y = (window.innerHeight - e.pageY * speed) / 100;
                circle.style.transform = translate(${x}px, ${y}px);
            });
        });
    </script>
</body>
</html>
