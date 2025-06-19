[Uploading index 
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>El Holandés Herrante</title>
  <style>
    body {
      margin: 0;
      font-family: 'Georgia', serif;
      background: linear-gradient(#1e3c72, #2a5298);
      color: #f4f4f4;
    }
    header { background: #112244; text-align: center; padding: 30px; }
    header h1 { font-size: 3em; color: #fcd462; }
    nav { background: #0c1a2b; padding: 10px; text-align: center; }
    nav a { color: #f4f4f4; margin: 0 15px; text-decoration: none; font-weight: bold; }
    section { padding: 30px; background: rgba(0,0,0,0.2); margin: 20px; border-radius: 10px; }
    h2 { color: #ffd700; }
    .menu-item { margin-bottom:20px; border-bottom:1px solid #ccc; padding-bottom:10px; }
    .nutricional-info { font-size:0.9em; color:#bbf7d0; }
    footer { background:#0c1a2b; color:#aaa; text-align:center; padding:20px; }
    .imagen, .mapa { width:100%; height:300px; background:#333; margin:20px 0; border-radius:10px; text-align:center; line-height:300px; color:#ccc; }
    a.btn { display:inline-block; background:#fcd462;color:#000;padding:10px 20px;text-decoration:none;margin:10px 0;border-radius:8px; }
  </style>

  <!-- Sonidos -->
  <audio id="olas" autoplay loop>
    <source src="sounds/ocean_waves_seagulls.mp3" type="audio/mp3" />
  </audio>
  <audio id="sable" preload="auto">
    <source src="sounds/sword_clash.mp3" type="audio/mp3" />
  </audio>
  <audio id="musica" loop>
    <source src="sounds/ocean_waves_seagulls.mp3" type="audio/mp3" />
  </audio>

  <script>
    window.onload = () => {
      const musica = document.getElementById("musica");
      const btn = document.createElement("button");
      btn.textContent = "🎵 Música del Mar";
      btn.style = "position:fixed;top:10px;right:10px;padding:10px;background:#fcd462;color:#000;border:none;border-radius:5px;cursor:pointer;z-index:1000";
      btn.onclick = () => musica.paused ? musica.play() : musica.pause();
      document.body.appendChild(btn);

      const sable = document.getElementById("sable");
      document.querySelectorAll("a, button").forEach(el => {
        el.addEventListener("mouseenter", () => {
          sable.currentTime = 0;
          sable.play();
        });
      });
    };
  </script>
</head>
<body>

<header>
  <h1>El Holandés Herrante</h1>
  <p>¡Donde el tesoro no se entierra, se sirve en la mesa!</p>
</header>

<nav>
  <a href="#nosotros">Nosotros</a>
  <a href="#menu">Menú</a>
  <a href="#actividades">Actividades</a>
  <a href="#reservaciones">Reservaciones</a>
  <a href="#contacto">Contacto</a>
</nav>

<section id="nosotros">
  <h2>¿Quiénes somos?</h2>
  <p>Un restaurante temático de piratas ubicado en Francisco Rodríguez 121, Puerto Vallarta. Disfruta de aventuras culinarias en un ambiente familiar, con búsquedas del tesoro, bailes temáticos y un menú en forma de mapa.</p>
  <div class="imagen">Imagen del restaurante</div>
</section>

<section id="menu">
  <h2>Menú del Tesoro</h2>

  <h3>🏴‍☠️ Menú Fijo</h3>
  <div class="menu-item">
    <strong>Sopa del Corsario</strong> - 250g - $120<br />
    <em>Crema de mariscos con toque de ron especiado.</em>
  </div>
  <div class="menu-item">
    <strong>Filete del Capitán</strong> - 350g - $240<br />
    <em>Filete de res en salsa de pimienta negra con puré de papa.</em>
  </div>
  <div class="menu-item">
    <strong>Pastel de Ron</strong> - 150g - $90<br />
    <em>Pastel húmedo con ron y frutos secos.</em>
  </div>

  <h3>⚓ Menú Promocional</h3>
  <div class="menu-item">
    <strong>Botín del Día</strong> - 400g - $180<br />
    <em>Pescado fresco al ajo con arroz caribeño y ensalada.</em>
  </div>
  <div class="menu-item">
    <strong>Combo Bucanero</strong> - 500g - $160<br />
    <em>Hamburguesa de camarón, papas gajo y soda.</em>
  </div>

  <h3>🐙 Menú Clásico</h3>
  <div class="menu-item">
    <strong>Alas de Kraken</strong> - 300g - $130<br />
    <em>Alitas picantes estilo pirata con salsa BBQ oscura.</em>
  </div>
  <div class="menu-item">
    <strong>Tacos del Náufrago</strong> - 250g - $110<br />
    <em>3 tacos de pescado empanizado con salsa tártara.</em>
  </div>
  <div class="menu-item">
    <strong>Aros del Abismo</strong> - 200g - $95<br />
    <em>Aros de calamar empanizados con salsa de limón y chipotle.</em>
  </div>

  <h3>🍃 Menú Nutricional</h3>
  <div class="menu-item">
    <strong>Ensalada del Mar</strong> - 300g - $125<br />
    <em>Ensalada de atún, espinaca, mango, nuez y vinagreta cítrica.</em><br />
    <div class="nutricional-info">Calorías: 320 | Proteínas: 22g | Grasas: 14g | Carbohidratos: 24g</div>
  </div>
  <div class="menu-item">
    <strong>Pechuga de Gaviota</strong> - 350g - $135<br />
    <em>Pechuga asada con verduras al vapor y quinoa.</em><br />
    <div class="nutricional-info">Calorías: 410 | Proteínas: 36g | Grasas: 10g | Carbohidratos: 35g</div>
  </div>
</section>

<section id="actividades">
  <h2>⚔️ Actividades Piratas</h2>
  <ul>
    <li>🔍 Búsqueda del Tesoro para niños y adultos</li>
    <li>💃 Bailes temáticos con música del mar</li>
    <li>📜 Eventos especiales en fechas piratas</li>
  </ul>
  <div class="imagen">Imagen de eventos</div>
</section>

<section id="reservaciones">
  <h2>📅 Reservaciones</h2>
  <p>Haz tu reservación ahora mismo:</p>
  <a href="https://wa.me/5255064004" class="btn">Reservar por WhatsApp</a>
</section>

<section id="contacto">
  <h2>📍 Contacto</h2>
  <p><strong>Dirección:</strong> Francisco Rodríguez 121, Puerto Vallarta, Jalisco</p>
  <p><strong>Horario:</strong> Todos los días de 12:00 p.m. a 12:00 a.m.</p>
  <p><strong>Instagram:</strong> <a href="https://instagram.com/elholandesherrante" target="_blank">@elholandesherrante</a></p>
  <p><strong>Teléfono:</strong> 55064004</p>
  <div class="mapa">Mapa interactivo</div>
</section>

<footer>
  <p>© 2025 El Holandés Herrante. Todos los derechos reservados.</p>
</footer>

</body>
</html>
2.html…]()
