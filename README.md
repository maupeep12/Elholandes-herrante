# Elholandes-herrante
Restaurante temático de piratas
import os
import zipfile

# Ruta de salida
base_dir = "/mnt/data/elholandes_herrante_listo"
os.makedirs(base_dir, exist_ok=True)

# Contenido del archivo HTML con galería
index_html = """
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <title>El Holandés Herrante</title>
    <link rel="stylesheet" href="style.css">
    <link rel="icon" href="logo.png">
    <audio autoplay loop>
        <source src="sound.mp3" type="audio/mpeg">
        Tu navegador no soporta audio.
    </audio>
</head>
<body>
    <header>
        <img src="logo.png" alt="Logo del Holandés Herrante" class="logo">
        <h1>El Holandés Herrante</h1>
        <p>Francisco Rodríguez 121, Puerto Vallarta, Jalisco</p>
        <p>Horario: 12:00 p.m. - 12:00 a.m.</p>
        <nav>
            <a href="#menu">Menú</a> | 
            <a href="#galeria">Galería</a> | 
            <a href="https://instagram.com/elholandesherrante" target="_blank">Instagram</a>
        </nav>
    </header>

    <section id="intro">
        <h2>¡Bienvenidos a bordo!</h2>
        <p>Un restaurante temático de piratas para toda la familia, lleno de aventuras, tesoros y sabores únicos.</p>
    </section>

    <section id="menu">
        <h2>Mapa del Tesoro (Menú)</h2>
        <ul>
            <li><strong>Alas del Kraken</strong> - 250g - $140 MXN - 620 cal</li>
            <li><strong>Hamburguesa del Capitán</strong> - 300g - $180 MXN - 850 cal</li>
            <li><strong>Tacos de Sirena</strong> - 200g - $120 MXN - 450 cal</li>
            <li><strong>Combo Pirata</strong>: Hamburguesa + papas + bebida - 600g - $250 MXN - 1100 cal</li>
            <li><strong>Mar y Tierra</strong>: Camarones + carne - 400g - $280 MXN - 980 cal</li>
            <li><strong>Ensalada del Navegante</strong> - 180g - $110 MXN - 220 cal</li>
            <li><strong>Pescado al Vapor del Caribe</strong> - 250g - $160 MXN - 300 cal</li>
        </ul>
    </section>

    <section id="galeria">
        <h2>Galería del Banquete Pirata</h2>
        <div class="carousel">
            <img src="img1.jpg" alt="Hamburguesa del Capitán">
            <img src="img2.jpg" alt="Tacos de Sirena">
            <img src="img3.jpg" alt="Combo Pirata">
            <img src="img4.jpg" alt="Pescado al Vapor">
            <img src="img5.jpg" alt="Ensalada del Navegante">
        </div>
    </section>

    <footer>
        <p>©️ 2025 El Holandés Herrante. Todos los derechos reservados.</p>
    </footer>
</body>
</html>
"""

# Estilo CSS
style_css = """
body {
    background: linear-gradient(#001f3f, #0074D9);
    color: #fff;
    font-family: 'Trebuchet MS', sans-serif;
    margin: 0;
    padding: 0;
}
header {
    text-align: center;
    background-color: #001f3f;
    padding: 20px;
}
.logo {
    width: 100px;
}
nav a {
    color: #7FDBFF;
    margin: 0 10px;
    text-decoration: none;
}
section {
    padding: 20px;
}
.carousel {
    display: flex;
    overflow-x: auto;
    gap: 10px;
    padding: 10px;
}
.carousel img {
    height: 200px;
    border-radius: 8px;
}
footer {
    text-align: center;
    background-color: #001f3f;
    padding: 10px;
    font-size: 0.9em;
}
"""

# Guardar los archivos HTML y CSS
with open(os.path.join(base_dir, "index.html"), "w", encoding="utf-8") as f:
    f.write(index_html)

with open(os.path.join(base_dir, "style.css"), "w", encoding="utf-8") as f:
    f.write(style_css)

# Crear archivos simulados de imágenes y sonido
placeholder_files = {
    "logo.png": b"",
    "sound.mp3": b"",
    "img1.jpg": b"",
    "img2.jpg": b"",
    "img3.jpg": b"",
    "img4.jpg": b"",
    "img5.jpg": b""
}

for filename, content in placeholder_files.items():
    with open(os.path.join(base_dir, filename), "wb") as f:
        f.write(content)

# Comprimir en ZIP
zip_path = "/mnt/data/elholandes_herrante_listo.zip"
with zipfile.ZipFile(zip_path, 'w') as zipf:
    for foldername, subfolders, filenames in os.walk(base_dir):
        for filename in filenames:
            file_path = os.path.join(foldername, filename)
            arcname = os.path.relpath(file_path, base_dir)
            zipf.write(file_path, arcname)

zip_path
