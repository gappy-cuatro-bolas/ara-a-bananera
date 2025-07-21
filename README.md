<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Araña Bananera</title>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { box-sizing: border-box; }
    html { scroll-behavior: smooth; }
    body {
      font-family: 'Poppins', sans-serif;
      font-size: 1.1rem;
      line-height: 1.7;
      background-color: #121212;
      color: #eaeaea;
      transition: background-color 0.3s ease, color 0.3s ease;
      padding-top: 200px;
    }
    main > section:first-of-type { margin-top: 7rem; }

    header {
      position: fixed; top: 0; left: 0; width: 100%;
      background: linear-gradient(to bottom, #1a1a1a, #222);
      border-bottom: 1px solid #444;
      box-shadow: 0 4px 12px rgba(0, 204, 153, 0.3);
      padding: 1.5rem 2rem;
      text-align: center; z-index: 1000;
    }
    header h1 {
      font-size: 2.8rem;
      color: #00cca6;
      text-shadow: 0 0 12px rgba(0, 204, 153, 0.8), 0 0 30px rgba(0, 204, 153, 0.5);
      font-weight: 700;
    }
    header p {
      color: #ccc; font-size: 1.3rem; margin-top: 0.4rem;
    }

    #toggle-theme {
      position: fixed; top: 15px; right: 25px;
      background: #00cca6; border-radius: 20px;
      width: 50px; height: 26px; cursor: pointer;
      box-shadow: 0 0 10px rgba(0, 204, 153, 0.7);
      display: flex; align-items: center; padding: 3px;
      border: none; z-index: 1100;
    }
    #toggle-theme .switch {
      background: #eee; width: 20px; height: 20px;
      border-radius: 50%; transition: transform 0.3s ease;
      box-shadow: 0 0 8px rgba(0,0,0,0.3);
    }
    body.light-mode #toggle-theme { background: #eee; }
    body.light-mode #toggle-theme .switch {
      transform: translateX(25px); background: #00cca6;
    }

    body.light-mode {
      background-color: #f4f4f4;
      color: #111;
    }

    main {
      max-width: 960px; margin: auto; padding: 0 2rem;
    }

    section {
      background-color: #181818; border-radius: 8px;
      padding: 2.8rem 3rem; margin-bottom: 2.5rem;
      box-shadow: 0 3px 15px rgba(0, 204, 153, 0.15);
      border-left: 6px solid #00cca6;
    }
    section:nth-child(even) {
      border-left: none; border-right: 6px solid #00cca6;
      background-color: #202020;
    }
    h2 {
      font-size: 2rem; color: #33e0c8;
      margin-bottom: 1.25rem; border-left: 5px solid #66ebdc;
      padding-left: 1rem;
      text-shadow: 0 0 6px rgba(0, 200, 150, 0.4);
    }
    p {
      color: #dcdcdc; margin-bottom: 1.4rem;
    }

    .gallery {
      display: flex; justify-content: center;
      gap: 1.5rem; flex-wrap: wrap;
    }
    .gallery img {
      max-width: 320px; width: 100%;
      border-radius: 10px; border: 1px solid #555;
      cursor: pointer;
      transition: transform 0.3s ease, box-shadow 0.3s ease;
    }
    .gallery img:hover {
      transform: scale(1.07);
      box-shadow: 0 0 20px rgba(0, 204, 153, 0.5);
    }

    footer {
      background-color: #1c1c1c;
      text-align: center; padding: 2rem 1rem;
      font-size: 1rem; color: #999;
      border-top: 1px solid #444;
      max-width: 960px; margin: 0 auto 2rem;
      border-radius: 0 0 10px 10px;
    }

    .lightbox {
      position: fixed; top: 0; left: 0;
      width: 100vw; height: 100vh;
      background: rgba(0,0,0,0.85);
      display: none; justify-content: center; align-items: center;
      z-index: 1200;
    }
    .lightbox.active { display: flex; }
    .lightbox img {
      max-width: 90%; max-height: 85vh;
      border-radius: 10px;
      box-shadow: 0 0 25px rgba(0, 200, 150, 0.8);
    }
    .lightbox .close-btn {
      position: fixed; top: 15px; right: 25px;
      font-size: 3rem; color: #00cca6;
      background: transparent; border: none;
      cursor: pointer; font-weight: 700;
    }
    .lightbox .close-btn:hover {
      color: #66ebdc;
    }

    @media (max-width:768px) {
      header h1 { font-size: 2rem; }
      header p { font-size: 1rem; }
      section { padding: 2rem 1.5rem; }
      h2 { font-size: 1.6rem; padding-left: 0.7rem; }
      .gallery img { max-width: 100%; }
      #toggle-theme { width: 42px; height: 22px; top:10px; right:15px; }
      #toggle-theme .switch { width:18px; height:18px; }
      body.light-mode #toggle-theme .switch { transform: translateX(22px); }
    }
  </style>
</head>
<body>

  <header>
    <h1>Araña Bananera</h1>
    <p>Una de las arañas más grandes y venenosas del mundo</p>
  </header>

  <button id="toggle-theme" aria-label="Modo claro/oscuro" role="switch" aria-checked="false">
    <div class="switch"></div>
  </button>

  <main>
    <section>
      <h2>¿Qué es la Araña Bananera?</h2>
      <p>
        La araña bananera (<em>Phoneutria</em>) es un género de arañas altamente venenosas conocidas por su agresividad y potente neurotoxina. Son nativas de América del Sur y Central, y reciben su nombre por su tendencia a esconderse en racimos de bananas.
      </p>
    </section>
    <section>
      <h2>Características Físicas</h2>
      <p>
        Estas arañas pueden alcanzar hasta 15 cm de envergadura con las patas extendidas. Telen un cuerpo peludo de color marrón claro con manchas oscuras y un vientre negro. Sus quelíceros (colmillos) son grandes y rojizos.
      </p>
    </section>
    <section>
      <h2>Comportamiento y Veneno</h2>
      <p>
        Son extremadamente agresivas cuando se sienten amenazadas, adoptando una postura característica levantando sus patas delanteras. Su veneno contiene una potente neurotoxina que puede ser mortal para humanos, especialmente niños.
      </p>
    </section>
    <section>
      <h2>Hábitat y Distribución</h2>
      <p>
        Viven en selvas tropicales de Brasil, Colombia, Venezuela y otros países sudamericanos. Durante el día se esconden en lugares oscuros y húmedos, como bajo troncos o entre las hojas de plantas de banano.
      </p>
    </section>
    <section>
      <h2>Galería</h2>
      <div class="gallery">
        <img src="https://www.thoughtco.com/thmb/0VJg8wZ8QZJQZJQZJQZJQZJQZJQ=/1500x0/filters:no_upscale():max_bytes(150000):strip_icc()/banana-spider-5c5a8a1b46e0fb0001f5e5f5.jpg" alt="Araña bananera en posición defensiva" loading="lazy" />
        <img src="https://i.natgeofe.com/k/4a4a9a9e-5e5e-4f5f-9f9f-5f5f5f5f5f5f/banana-spider_16x9.jpg" alt="Primer plano de una araña bananera" loading="lazy" />
        <img src="https://www.sciencenews.org/wp-content/uploads/2020/10/100720_ec_banana-spider_feat-1028x579.jpg" alt="Araña bananera mostrando sus colmillos" loading="lazy" />
      </div>
    </section>
  </main>

  <footer>
    <p>© 2025 Sitio educativo sobre la Araña Bananera | Información científica y visual</p>
  </footer>

  <div class="lightbox" role="dialog" aria-modal="true">
    <button class="close-btn" aria-label="Cerrar">×</button>
    <img src="" alt="Imagen ampliada" />
  </div>

  <script>
    const toggle = document.getElementById('toggle-theme'), bodyEl = document.body;
    toggle.addEventListener('click', () => {
      bodyEl.classList.toggle('light-mode');
      toggle.setAttribute('aria-checked', bodyEl.classList.contains('light-mode'));
    });

    const lightbox = document.querySelector('.lightbox'),
          imgBox = lightbox.querySelector('img'),
          btnClose = lightbox.querySelector('.close-btn');

    document.querySelectorAll('.gallery img').forEach(img => {
      img.addEventListener('click', () => {
        imgBox.src = img.src;
        imgBox.alt = img.alt;
        lightbox.classList.add('active');
        btnClose.focus();
      });
    });
    btnClose.addEventListener('click', () => lightbox.classList.remove('active'));
    lightbox.addEventListener('click', e => {
      if (e.target === lightbox) lightbox.classList.remove('active');
    });
    document.addEventListener('keydown', e => {
      if (e.key === 'Escape') lightbox.classList.remove('active');
    });
  </script>
</body>
</html>
