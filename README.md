<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Escuela 32 Caudillos Riojanos</title>
  <style>
    body {
      margin: 0;
      font-family: 'Segoe UI', Arial, sans-serif;
      background: #f9f9f9;
      color: #222;
    }
    header {
      background: linear-gradient(90deg, #ff6600, #ffcc00);
      color: white;
      text-align: center;
      padding: 2rem;
      font-size: 1.5rem;
      font-weight: bold;
      box-shadow: 0 4px 10px rgba(0,0,0,0.2);
    }
    nav {
      display: flex;
      justify-content: center;
      background: #333;
      flex-wrap: wrap;
    }
    nav a {
      color: white;
      padding: 1rem;
      text-decoration: none;
      transition: background 0.3s;
    }
    nav a:hover {
      background: #ff6600;
    }
    section {
      padding: 2rem;
      max-width: 1000px;
      margin: auto;
    }
    h2 {
      color: #ff6600;
      border-bottom: 2px solid #ff6600;
      padding-bottom: 5px;
    }
    .galeria {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 1rem;
    }
    .galeria img, .galeria video {
      width: 100%;
      border-radius: 10px;
      box-shadow: 0 2px 6px rgba(0,0,0,0.2);
    }
    .actividad {
      background: white;
      margin: 1rem 0;
      padding: 1rem;
      border-radius: 10px;
      box-shadow: 0 2px 6px rgba(0,0,0,0.1);
    }
    footer {
      background: #333;
      color: white;
      text-align: center;
      padding: 1rem;
      margin-top: 2rem;
    }
    input, button {
      padding: 0.5rem;
      margin-top: 0.5rem;
    }
    button {
      background: #ff6600;
      border: none;
      color: white;
      cursor: pointer;
      border-radius: 5px;
    }
    button:hover {
      background: #cc5200;
    }
  </style>
</head>
<body>

  <header>
    Escuela N°32 “Caudillos Riojanos” – Paraje Cebollar, La Rioja <br>
    <small>Director: Humberto Cáceres – Año 2025</small>
  </header>

  <nav>
    <a href="#inicio">Inicio</a>
    <a href="#galeria">Fotos y Videos</a>
    <a href="#actividades">Actividades</a>
    <a href="#contacto">Contacto</a>
  </nav>

  <section id="inicio">
    <h2>Bienvenidos</h2>
    <p>
      Esta es la página oficial de la <b>Escuela 32 Caudillos Riojanos</b>, ubicada en zona rural 
      Paraje Cebollar, La Rioja. Aquí compartimos nuestras actividades, fotos y videos 
      que realizamos junto a nuestros estudiantes.
    </p>
  </section>

  <section id="galeria">
    <h2>Galería de Fotos y Videos</h2>
    <div class="galeria">
      <img src="foto1.jpg" alt="Actividad escolar">
      <img src="foto2.jpg" alt="Evento en la escuela">
      <video controls>
        <source src="video1.mp4" type="video/mp4">
        Tu navegador no soporta video.
      </video>
    </div>
  </section>

  <section id="actividades">
    <h2>Actividades Día a Día</h2>
    <div id="lista-actividades"></div>
    <h3>Agregar Nueva Actividad</h3>
    <input type="text" id="nuevaActividad" placeholder="Escribe la actividad...">
    <button onclick="agregarActividad()">Publicar</button>
  </section>

  <section id="contacto">
    <h2>Contacto</h2>
    <p><b>Email:</b> escuela32caudillosriojanos@educacionlarioja.com</p>
    <p><b>Teléfono:</b> 3804805889</p>
    <p><b>Dirección:</b> Paraje Cebollar, La Rioja - Argentina</p>
  </section>

  <footer>
    © HC 2025 Escuela 32 Caudillos Riojanos - Todos los derechos reservados.
  </footer>

  <script>
    function agregarActividad() {
      let texto = document.getElementById("nuevaActividad").value;
      if (texto.trim() !== "") {
        let div = document.createElement("div");
        div.className = "actividad";
        let fecha = new Date().toLocaleDateString("es-AR", { 
          day: "2-digit", month: "long", year: "numeric" 
        });
        div.innerHTML = "<b>" + fecha + ":</b> " + texto;
        document.getElementById("lista-actividades").prepend(div);
        document.getElementById("nuevaActividad").value = "";
      }
    }
  </script>

</body>
</html>
