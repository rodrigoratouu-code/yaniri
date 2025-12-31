<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>TuNoSaBeNa</title>
  <style>
    #particles-js {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: -1;
    }

    body {
      margin: 0;
      font-family: 'Segoe UI', sans-serif;
      background: linear-gradient(90deg, #1f003b, #0d171b, #011242);
      color: #e0dedef6;
      padding: 2em;
      min-height: 100vh;
    }
    header {
      background-color: rgba(255, 255, 255, 0.041);
      padding: 1em;
      text-align: center;
    }
    
    nav ul {
      list-style: none;
      padding: 0;
      display: flex;
      justify-content: center;
      gap: 2em;
      margin: 0;
    }
    nav a {
      text-decoration: none;
      color: #202020;
      font-weight: bold;
      transition: color 0.3s ease;
    }
    nav a:hover {
      color: #0077cc;
    }
    section {
      padding: 2em;
      background-color: rgba(255, 255, 255, 0.048);
      margin: 1em auto;
      border-radius: 8px;
      max-width: 900px;
      box-shadow: 0 2px 8px rgba(0,0,0,0.04);
    }
    .video-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 1em;
    }
    iframe {
      width: 100%;
      height: 200px;
      border: none;
      border-radius: 8px;
      background: #000;
    }
    .redes a {
      display: inline-block;
      padding: 0.5em 1em;
      background-color: #0077cc;
      color: rgb(255, 255, 255);
      border-radius: 5px;
      margin-right: 0.5em;
      margin-bottom: 0.5em;
      text-decoration: none;
      transition: background-color 0.3s ease;
      font-size: 1em;
    }
    .redes a:hover {
      background-color: #005fa3;
    }
    #retro-radio {
      background: linear-gradient(135deg, #ff00cc 0%, #333399 100%);
      padding: 2em;
      margin: 1em auto;
      border-radius: 15px;
      max-width: 900px;
      box-shadow: 0 8px 20px rgba(255, 0, 204, 0.4);
      text-align: center;
      border: 3px solid #ff00cc;
      position: relative;
      overflow: hidden;
    }
    #retro-radio::before {
      content: '';
      position: absolute;
      top: -50%;
      left: -50%;
      width: 200%;
      height: 200%;
      background: linear-gradient(45deg, transparent, rgba(255, 255, 255, 0.1), transparent);
      animation: shine 3s infinite;
    }
    @keyframes shine {
      0% { transform: translateX(-100%) translateY(-100%) rotate(45deg); }
      100% { transform: translateX(100%) translateY(100%) rotate(45deg); }
    }
    #retro-radio h2 {
      font-size: 2.5em;
      color: #fff;
      text-shadow: 0 0 10px #ff00cc, 0 0 20px #ff00cc, 0 0 30px #ff00cc;
      margin-bottom: 0.5em;
      font-weight: bold;
      position: relative;
      z-index: 1;
    }
    #retro-radio p {
      font-size: 1.2em;
      color: #fff;
      margin-bottom: 1.5em;
      position: relative;
      z-index: 1;
    }
    .retro-button {
      display: inline-block;
      padding: 1em 2.5em;
      background: linear-gradient(90deg, #ff0080, #ff00cc, #cc00ff);
      color: #fff;
      border: none;
      border-radius: 50px;
      font-size: 1.3em;
      font-weight: bold;
      text-decoration: none;
      cursor: pointer;
      box-shadow: 0 5px 15px rgba(255, 0, 204, 0.6);
      transition: all 0.3s ease;
      position: relative;
      z-index: 1;
      animation: pulse 2s infinite;
    }
    .retro-button:hover {
      transform: scale(1.1);
      box-shadow: 0 8px 25px rgba(255, 0, 204, 0.9);
    }
    @keyframes pulse {
      0%, 100% { transform: scale(1); }
      50% { transform: scale(1.05); }
    }
    footer {
      text-align: center;
      padding: 1em;
      background-color: rgba(255, 255, 255, 0.356);
      font-size: 1em;
    }
    #galeria-videos {
      padding: 2em 1em;
      background-color: rgba(229, 80, 248, 0.418);
      margin: 1em auto;
      border-radius: 8px;
      max-width: 900px;
    }
    .playlist audio {
      width: 100%;
      margin-bottom: 1em;
      border-radius: 8px;
      background-color: #e7e5e5;
    }
    @keyframes fadeInSlide {
      0% { opacity: 0; transform: translateY(-30px);}
      100% { opacity: 1; transform: translateY(0);}
    }
    @keyframes glow {
      0% { text-shadow: 0 0 5px #ff00cc, 0 0 10px #ff00cc, 0 0 15px #ff00cc;}
      50% { text-shadow: 0 0 20px #ff00cc, 0 0 30px #ff00cc, 0 0 40px #ff00cc;}
      100% { text-shadow: 0 0 5px #ff00cc, 0 0 10px #ff00cc, 0 0 15px #ff00cc;}
    }
    #galeria-videos h2 {
      font-size: 2.2em;
      color: #d8d2d2;
      text-align: center;
      margin-bottom: 20px;
      animation: fadeInSlide 1s ease-out forwards;
      opacity: 0;
      transition: transform 0.3s ease, color 0.3s ease;
    }
    #galeria-videos h2:hover {
      animation: glow 1.5s infinite;
      color: #f846d4;
      transform: scale(1.05);
    }
    audio::-webkit-media-controls-play-button {
      animation: playPulse 1s infinite alternate;
      filter: drop-shadow(0 0 6px #f846d4);
    }
    @keyframes playPulse {
      0% {
        transform: scale(1);
        filter: drop-shadow(0 0 6px #f846d4);
      }
      100% {
        transform: scale(1.18);
        filter: drop-shadow(0 0 16px #f846d4);
      }
    }
    audio::-moz-media-controls-play-button {
      animation: playPulse 1.2s infinite alternate;
      filter: drop-shadow(0 0 6px #f846d4);
    }
    @media (max-width: 900px) {
      section, #galeria-videos {
        max-width: 98vw;
        padding: 1.2em 0.5em;
      }
    }
    @media (max-width: 600px) {
      body {
        padding: 0.5em;
      }
      header h1 {
        font-size: 2.3em;
      }
      #menu-toggle {
        display: block;
      }
      nav ul {
        flex-direction: column;
        gap: 0.5em;
        display: none;
        background: rgba(255,255,255,0.97);
        position: absolute;
        width: 90vw;
        left: 5vw;
        top: 60px;
        border-radius: 8px;
        box-shadow: 0 2px 8px rgba(0,0,0,0.08);
        z-index: 100;
      }
      nav ul.show {
        display: flex;
      }
      section, #galeria-videos {
        margin: 0.5em 0;
        padding: 1em 0.3em;
      }
      iframe {
        height: 160px;
      }
      .redes a {
        display: block;
        margin-right: 0;
      }
    }
  </style>
</head>
<body>
  <div id="particles-js"></div>
  <header>
    <h1 style="color: rgb(241, 287, 17);">SOFI MUSIC</h1>
  </header>
  <section id="catalogo">
    <h2>🎧 RADIO DE TOO UN CHIN🎼</h2>
    <div class="catalogo-card">
      <p>MUSICA PA GO SA .</p>
      <a href="https://rdomiplayer.com/landing/radio/1596/1" target="_blank">
        <button>ESCUCHA RADIO DOMINICANA</button>
      </a>
      <a href="https://play.los40.do/" target="_blank">
        <button>ESCUCHA LOS40 REPÚBLICA DOMINICANA</button>
      </a>
    </div>
  </section>
  <section id="retro-radio">
    <h2>🎸 RETRO HITS 80s & 90s 🎹</h2>
    <p>¡Viaja en el tiempo con los mejores clásicos! Rock, Pop & Oldies 🎵</p>
    <a href="https://www.regresoalos80y90.com" target="_blank" class="retro-button">
      ▶️ ESCUCHA REGRESO A LOS 80s Y 90s
    </a>
  </section>
  <section id="galeria-videos">
    <h2>SOFI MUSIC  </h2>
    <p>Canciones que animan 'Quieres mas' Ya sabes dónde encontrarme, MI CUÑAAA FELIZ CUMPLEAÑOS</p>
    <div class="playlist">
      <div>
        <h3>LATINO MIX 2023</h3>
        <audio controls>
          <source src="https://dl.dropboxusercontent.com/scl/fi/tzka46nhcclxieizxnn0i/LATINO-MIX-2023.mp3?rlkey=kpa8xwmaso8kdcm0j1zt6squd&st=f54ztlwt" type="audio/mpeg">
          Tu navegador no soporta el audio.
        </audio>
      </div>
      <div>
        <h3>Salsa Vieja</h3>
        <audio controls>
          <source src="https://dl.dropboxusercontent.com/scl/fi/mxxv0bwdrz93cgqqlfrpt/Salsa-Vieja-MP3.mp3?rlkey=c5nrbj8j22ybjxxnxw98fm66d&st=rsec3mr0" type="audio/mpeg">
          Tu navegador no soporta el audio.
        </audio>
      </div>
    </div>
  </section>
  <section id="videos">
    <h2>VIDEOS SOFI </h2>
    <div class="video-grid">
      <div class="video-item">
        <iframe width="1316" height="740" src="https://www.youtube.com/embed/Lms0IAqYXHU" title="24 dic dominicano dj don sebass" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
        <iframe width="1316" height="740" src="https://www.youtube.com/embed/40AJMQob25o?list=RD40AJMQob25o" title="Que Dios Te Bendiga, Peter Manjarrés Y Sergio Luis Rodríguez - Video Letra" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
        <iframe width="1316" height="740" src="https://www.youtube.com/embed/_2WwE-qjhRM?list=RDEM1xXA6mZ4SNhXwET7NBaAHg" title="SALSA CLASICA VOL 12 🥁  LAS 12 MEJORES SALSA | MEZCLADA EN VIVO POR DJ ADONI ♥️🍺🥃  ( SALSA MIX )" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
        <iframe width="1316" height="740" src="https://www.youtube.com/embed/8xx4zEPsuCM?list=RDEM1xXA6mZ4SNhXwET7NBaAHg" title="SALSA MIX VOL 9 ❤️ Las mejores salsa | Mezclada en vivo por DJ ADONI 🍺🥃" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
        <iframe width="1316" height="740" src="https://www.youtube.com/embed/NImbF9L7tHo?list=RDEM1xXA6mZ4SNhXwET7NBaAHg" title="BACHATA CORTA VENAS VOL 13 💔🥃 LAS MEJORES BACHATAS 🎤 MEZCLADA POR DJ ADONI ( BACHATA MIX )" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
        <iframe width="1316" height="740" src="https://www.youtube.com/embed/MjCBfWMJgA8?list=RDEM1xXA6mZ4SNhXwET7NBaAHg" title="SALSA Y BACHATA MIX 🥃 PARA BEBER / MEZCLADA POR DJ ADONI 🎤 SALSA MIX - BACHATA MIX" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
        <iframe width="1316" height="740" src="https://www.youtube.com/embed/bkHsxHZ8BAA?list=RDEM1xXA6mZ4SNhXwET7NBaAHg" title="BACHATA CORTA VENAS VOL 11 💔🥃 15 DE LA MEJORES BACHATAS 🎤 MEZCLADA POR DJ ADONI ( BACHATA MIX )" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
        <iframe width="1316" height="740" src="https://www.youtube.com/embed/rclLZUdozeg?list=RDrclLZUdozeg" title="SALSA CLASICA VOL 14 🥁 SALSA ROMANTICA MIX | MEZCLADA EN VIVO POR DJ ADONI" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
        <iframe width="1316" height="740" src="https://www.youtube.com/embed/sci2ZEA8dpc" title="SALSA CLASICA VOL 16 🥁 SALSA ROMANTICA MIX | MEZCLADA EN VIVO POR DJ ADONI" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
        <iframe width="1316" height="740" src="https://www.youtube.com/embed/Nx-CvlAoSRM" title="DETO UN CHIN VOL 19 🕺💃BACHATA MIX | SALSA MIX | MERENGUE MIX | DEMBOW MIX 🎧 DJ ADONI" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
        <iframe width="1316" height="740" src="https://www.youtube.com/embed/2EtroJD5v8w" title="🎄MIX NAVIDEÑO 🎅 LOS MEJORES MERENGUE , SALSA, BACHATA NAVIDEÑA 🎅🏽 MEZCLANDO EN VIVO ADONIII 🗣" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
        <iframe width="1316" height="740" src="https://www.youtube.com/embed/40AJMQob25o?list=RD40AJMQob25o" title="Que Dios Te Bendiga, Peter Manjarrés Y Sergio Luis Rodríguez - Video Letra" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
        <iframe width="1318" height="740" src="https://www.youtube.com/embed/MRIOIJ_jzrc?list=RDMRIOIJ_jzrc" title="Diciembre 24 de Parranda Colombiana   🇨🇴  🎄 ⛪ *̣ ☆" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
      </div>      
    </div>
  </section>
  <section id="recomendacion-navegador">
    <h2>🧭 Recomendación de Mi Cuñao Rodrigo</h2>
    <p>Para una mejor experiencia, abre este sitio en Navegadores  <strong>Google Chrome</strong>, <strong>Mozilla Firefox</strong> o <strong>Microsoft Edge</strong>.</p>
  </section>
  <section id="contacto">
    <h2>Contáctanos</h2>
    <div id="chat">
      <p>Chat en vivo próximamente...</p>
    </div>
    <div class="redes">
      <a href="https://web.whatsapp.com/" target="_blank" rel="noopener">Watsapp</a>  
      <a href="https://facebook.com" target="_blank" rel="noopener">Facebook</a>
      <a href="https://twitter.com" target="_blank" rel="noopener">Twitter</a>
      <a href="https://instagram.com" target="_blank" rel="noopener">Instagram</a>
    </div>
  </section>
  <footer>
    <p>&copy; 2025 SOFI ROSA. Todos los derechos reservados.</p>
  </footer>
  <script>
    const menuToggle = document.getElementById('menu-toggle');
    const navList = document.querySelector('nav ul');
    if (menuToggle) {
      menuToggle.addEventListener('click', () => {
        navList.classList.toggle('show');
      });
    }
    window.addEventListener('DOMContentLoaded', () => {
      const h2 = document.querySelector('#galeria-videos h2');
      if (h2) h2.style.opacity = '1';
    });
  </script>
  <script src="https://cdn.jsdelivr.net/npm/tsparticles@2.11.1/tsparticles.bundle.min.js"></script>
  <script>
    tsParticles.load("particles-js", {
      fullScreen: {
        enable: true,
        zIndex: -1
      },
      particles: {
        number: {
          value: 20
        },
        color: {
          value: "#ffffff"
        },
        shape: {
          type: "circle"
        },
        opacity: {
          value: 0.09
        },
        size: {
          value: 6
        },
        move: {
          enable: true,
          speed: 1,
          direction: "none",
          outModes: {
            default: "bounce"
          },
          attract: {
            enable: true,
            rotateX: 600,
            rotateY: 1200
          }
        }
      },
      background: {
        color: "transparent"
      }
    });
  </script>
</body>
</html>
