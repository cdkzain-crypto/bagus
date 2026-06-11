
<!DOCTYPE html>
<html lang="ms">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <title>Dashboard Masa Glassmorphism</title>
    <style>
        :root {
            --primary-glow: #00d2ff;
            --secondary-glow: #ff00bd;
            --bg-color: #0f172a;
            --glass-bg: rgba(255, 255, 255, 0.05);
            --glass-border: rgba(255, 255, 255, 0.1);
        }

        body {
            background-color: var(--bg-color);
            margin: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            font-family: 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
            color: white;
            overflow: hidden;
            flex-direction: column;
            gap: 40px;
            padding: 20px;
        }

        /* Latar Belakang Animasi Animasi */
        .background-blobs {
            position: absolute;
            width: 100%;
            height: 100%;
            overflow: hidden;
            z-index: -1;
        }

        .blob {
            position: absolute;
            filter: blur(80px);
            border-radius: 50%;
            opacity: 0.5;
            animation: move 20s infinite alternate;
        }

        .blob-1 {
            width: 400px;
            height: 400px;
            background: var(--primary-glow);
            top: -100px;
            left: -100px;
        }

        .blob-2 {
            width: 300px;
            height: 300px;
            background: var(--secondary-glow);
            bottom: -50px;
            right: -50px;
            animation-delay: -5s;
        }

        @keyframes move {
            from {
                transform: translate(0, 0);
            }
            to {
                transform: translate(100px, 100px);
            }
        }

        /* Container Utama Dashboard */
        .dashboard {
            background: var(--glass-bg);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            border: 1px solid var(--glass-border);
            border-radius: 40px;
            padding: 40px;
            display: grid;
            grid-template-columns: auto 1fr;
            gap: 40px;
            box-shadow: 0 25px 50px rgba(0, 0, 0, 0.3);
            align-items: center;
            animation: float 6s ease-in-out infinite;
            width: 480px;
        }

        /* Bahagian Jam Analog */
        .clock-container {
            position: relative;
            width: 200px;
            height: 200px;
            background: rgba(15, 23, 42, 0.5);
            border-radius: 50%;
            border: 2px solid var(--glass-border);
            box-shadow: inset 10px 10px 20px rgba(0,0,0,0.5), inset -5px -5px 15px rgba(255,255,255,0.05);
            display: flex;
            justify-content: center;
            align-items: center;
            overflow: hidden;
            z-index: 9;
        }

        .clock-container::before {
            content: "";
            position: absolute;
            inset: -2px;
            border-radius: 50%;
            background: linear-gradient(45deg, var(--primary-glow), var(--secondary-glow));
            z-index: 9;
            opacity: 0.3;
        }

        .clock-bg {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            border-radius: 50%;
            object-fit: cover;
            z-index: 6;
            opacity: 0.4;
        }

        .clock {
            position: relative;
            z-index: 6;
            width: 100%;
            height: 100%;
        }

        .hand {
            position: absolute;
            bottom: 50%;
            left: 50%;
            transform-origin: bottom;
            border-radius: 10px;
            transform: translateX(-50%);
        }

        .hour {
            width: 6px;
            height: 50px;
            background: #fff;
            z-index: 3;
        }

        .min {
            width: 4px;
            height: 75px;
            background: #cbd5e1;
            z-index: 4;
        }

        .sec {
            width: 2px;
            height: 85px;
            background: var(--secondary-glow);
            z-index: 5;
            box-shadow: 0 0 10px var(--secondary-glow);
        }

        .center-dot {
            position: absolute;
            width: 12px;
            height: 12px;
            background: white;
            border-radius: 50%;
            z-index: 10;
            box-shadow: 0 0 15px white;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
        }

        /* Bahagian Info Digital */
        .info-container {
            display: flex;
            flex-direction: column;
            justify-content: center;
        }

        .digital-clock {
            font-size: 4rem;
            font-weight: 800;
            margin: 0;
            background: linear-gradient(to right, #fff, #94a3b8);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            letter-spacing: -2px;
        }

        .date-display {
            font-size: 1.2rem;
            color: var(--primary-glow);
            text-transform: uppercase;
            letter-spacing: 4px;
            margin-top: -5px;
            font-weight: 500;
        }

        .day-display {
            color: #94a3b8;
            margin-top: 10px;
            font-size: 1rem;
        }

        /* Animasi Terapung */
        @keyframes float {
            0%,
            100% {
                transform: translateY(0);
            }
            50% {
                transform: translateY(-20px);
            }
        }

        /* Responsive */
        @media (max-width: 600px) {
            .dashboard {
                grid-template-columns: 1fr;
                text-align: center;
                padding: 30px;
                width: 100%;
            }
            .clock-container {
                margin: 0 auto;
            }
            .digital-clock {
                font-size: 3rem;
            }
        }

        @media (max-width: 600px) {
            body {
                overflow: auto; /* Boleh scroll di mobile */
            }
            .dashboard {
                grid-template-columns: 1fr;
                text-align: center;
                padding: 30px;
                width: 100%;
            }
            .clock-container {
                margin: 0 auto;
            }
            .digital-clock {
                font-size: 3rem;
            }
        }
        /* Video Latar Belakang */
        body, html {
            margin: 0; padding: 0; height: 100%;
            overflow: auto;
        }
        .video-background {
            position: fixed;
            top: 0; left: 0;
            width: 100%; height: 100%;
            z-index: -1;
            pointer-events: none;
            overflow:auto;
        }
        .video-background iframe {
            width: 177.77vh; /* 100 * (16/9) aspect */
            height: 100vh;
            position: absolute;
            top: 0; left: 50%;
            transform: translateX(-50%);
        }
        .content {
            position: relative;
            z-index: 1;
            color: white;
            font-size: 2rem;
            padding: 20px;
        }
    
    
    </style>
    
<div class="video-background">
  <iframe 
    src="https://www.youtube.com/embed/DzOkotpHdX8?autoplay=1&mute=1&loop=1&playlist=DzOkotpHdX8&controls=0&showinfo=0&modestbranding=1&iv_load_policy=3" 
    frameborder="0" 
    allow="autoplay; encrypted-media" 
    allowfullscreen>
  </iframe>
</div>

<div class="content">
 
</div>

</head>
 <p>H2⃣®</p>
<body>
<p style="position:absolute; bottom:10px; width: 100%; text-align:center; color:white; font-weight:bold; user-select:none;">
  H<span style="color:red;">2⃣</span>®
</p>
<p style="position: absolute; bottom: 40px; width: 100%; text-align: center; color: white; font-weight: bold; user-select: none;">
    Built for function: Dashboard Masa Glassmorphism
  </p>
    <div class="background-blobs">
        <div class="blob blob-1"></div>
        <div class="blob blob-2"></div>
    </div>

    <div class="dashboard">
        <div class="clock-container">
            <img src="https://i.postimg.cc/dtNyR0pb/IMG_8571.png" alt="Background Jam" class="clock-bg" />
            <div class="clock">
                <div class="hand hour" id="hour"></div>
                <div class="hand min" id="min"></div>
                <div class="hand sec" id="sec"></div>
                <div class="center-dot"></div>
            </div>
        </div>

        <div class="info-container">
            <div class="date-display" id="date">01 JANUARI 2026</div>
            <div class="digital-clock" id="digital">00:00:00</div>
            <div class="day-display" id="day">AHAD</div>
<p style="position:absolute; bottom:10px; width: 100%; text-align:center; color:white; font-weight:bold; user-select:none;">
  H<span style="color:red;">2⃣</span>®
</p>
    </div>
  </div>
    <!-- Section 1 -->
    <section>
        <h2></h2>
        <p> "Perut dah berbunyi? Jom tengok menu istimewa hari ini!.</p>
    <div class="overlay">
   </p>
    </div>
  </div>

    </section>

    <!-- Section 2 -->
    <section>
        <h2><marquee behavior="scroll" direction="left" scrollamount="5" aria-live="polite" aria-atomic="true" style="margin-bottom:12px;">
  Selamat Datang Tuan-Tuan & Puan-Puan <strong>tekan button untuk melihat menu</strong> ( untuk rujukkan) 
</marquee> UPDATED--(TIME SHEET)</h2>
        <a href="https://controlcenterbtu26.oneapp.dev/" class="cta-button" style="color:#fff; text-decoration:none; padding:10px 20px; background:red; border-radius:8px; display:inline-block; margin-top:20px;">
 BINTULU MOLEK
</a>
    </section>

    <script>
        function updateClock() {
            const now = new Date();
            
            // Data Masa
            const seconds = now.getSeconds();
            const minutes = now.getMinutes();
            const hours = now.getHours();

            // Update Jam Analog
            const secDeg = (seconds / 60) * 360;
            const minDeg = (minutes / 60) * 360 + (seconds / 60) * 6;
            const hourDeg = ((hours % 12) / 12) * 360 + (minutes / 60) * 30;

            document.getElementById('sec').style.transform = `translateX(-50%) rotate(${secDeg}deg)`;
            document.getElementById('min').style.transform = `translateX(-50%) rotate(${minDeg}deg)`;
            document.getElementById('hour').style.transform = `translateX(-50%) rotate(${hourDeg}deg)`;

            // Update Jam Digital
            const h = hours.toString().padStart(2, '0');
            const m = minutes.toString().padStart(2, '0');
            const s = seconds.toString().padStart(2, '0');
            document.getElementById('digital').innerText = `${h}:${m}:${s}`;

            // Update Tarikh & Hari
            const days = ["AHAD", "ISNIN", "SELASA", "RABU", "KHAMIS", "JUMAAT", "SABTU"];
            const months = ["JANUARI", "FEBRUARI", "MAC", "APRIL", "MEI", "JUN", "JULAI", "OGOS", "SEPTEMBER", "OKTOBER", "NOVEMBER", "DISEMBER"];
            
            document.getElementById('day').innerText = days[now.getDay()];
            document.getElementById('date').innerText = `${now.getDate()} ${months[now.getMonth()]} ${now.getFullYear()}`;
        }

        setInterval(updateClock, 1000);
        updateClock();
    </script>

<script defer src="https://static.cloudflareinsights.com/beacon.min.js/v833ccba57c9e4d2798f2e76cebdd09a11778172276447" integrity="sha512-57MDmcccJXYtNnH+ZiBwzC4jb2rvgVCEokYN+L/nLlmO8rfYT/gIpW2A569iJ/3b+0UEasghjuZH/ma3wIs/EQ==" data-cf-beacon='{"version":"2024.11.0","token":"e3c1c9af36de41759418005494a48906","r":1,"server_timing":{"name":{"cfCacheStatus":true,"cfEdge":true,"cfExtPri":true,"cfL4":true,"cfOrigin":true,"cfSpeedBrain":true},"location_startswith":null}}' crossorigin="anonymous"></script>
</body>
</html>
