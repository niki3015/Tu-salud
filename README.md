# Tu-salud
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Salud Rural Conectada</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f0f8f5;
      margin: 0;
      padding: 0;
    }
    header, footer {
      background: #00897b;
      color: white;
      padding: 1em;
      text-align: center;
    }
    nav {
      display: flex;
      justify-content: space-around;
      background: #00695c;
      padding: 0.5em;
    }
    nav a {
      color: white;
      text-decoration: none;
      font-weight: bold;
    }
    .container {
      padding: 1em;
    }
    h2 {
      color: #00695c;
    }
    input, textarea, select, button {
      width: 100%;
      padding: 0.5em;
      margin: 0.5em 0;
      border-radius: 5px;
      border: 1px solid #ccc;
    }
    .lang-switch {
      text-align: right;
      margin-top: -1em;
      padding-right: 1em;
    }
    .lang-switch button {
      background: none;
      border: none;
      color: white;
      font-weight: bold;
      cursor: pointer;
    }
  </style>
</head>
<body>
  <header>
    <h1 id="title">Salud Rural Conectada</h1>
    <div class="lang-switch">
      <button onclick="setLanguage('es')">Español</button> |
      <button onclick="setLanguage('qu')">Quechua</button>
    </div>
  </header>

  <nav>
    <a href="#inicio" id="navInicio">Inicio</a>
    <a href="#revision" id="navRevision">Revisión</a>
    <a href="#clases" id="navClases">Primeros Auxilios</a>
    <a href="#contacto" id="navContacto">Contacto</a>
  </nav>

  <div class="container">
    <section id="inicio">
      <h2 id="inicioTitulo">Bienvenido/a</h2>
      <p id="inicioTexto">Accede a servicios de salud y aprende primeros auxilios desde tu celular.</p>
    </section>

    <section id="revision">
      <h2 id="revisionTitulo">Revisión Básica de Salud</h2>
      <form>
        <label id="nombreLabel">Nombre completo:</label>
        <input type="text" required>

        <label id="sintomasLabel">¿Qué síntomas tienes?</label>
        <textarea required></textarea>

        <label id="temperaturaLabel">Temperatura (°C):</label>
        <input type="number" step="0.1">

        <label id="presionLabel">Presión arterial (si sabes):</label>
        <input type="text">

        <button type="submit" id="enviarBtn">Enviar revisión</button>
      </form>
    </section>

    <section id="clases">
      <h2 id="clasesTitulo">Clases Básicas de Primeros Auxilios</h2>
      <ul id="clasesLista">
        <li>Cómo detener una hemorragia</li>
        <li>Qué hacer en caso de desmayo</li>
        <li>Atención a quemaduras leves</li>
        <li>Maniobra de Heimlich (ahogamiento)</li>
      </ul>
    </section>

    <section id="contacto">
      <h2 id="contactoTitulo">Contacto</h2>
      <p id="contactoTexto">Para más información, acude al centro de salud más cercano o llama al 123.</p>
    </section>
  </div>

  <footer>
    <p>&copy; 2025 Salud Rural Conectada</p>
  </footer>

  <script>
    const textos = {
      es: {
        title: "Salud Rural Conectada",
        navInicio: "Inicio",
        navRevision: "Revisión",
        navClases: "Primeros Auxilios",
        navContacto: "Contacto",
        inicioTitulo: "Bienvenido/a",
        inicioTexto: "Accede a servicios de salud y aprende primeros auxilios desde tu celular.",
        revisionTitulo: "Revisión Básica de Salud",
        nombreLabel: "Nombre completo:",
        sintomasLabel: "¿Qué síntomas tienes?",
        temperaturaLabel: "Temperatura (°C):",
        presionLabel: "Presión arterial (si sabes):",
        enviarBtn: "Enviar revisión",
        clasesTitulo: "Clases Básicas de Primeros Auxilios",
        clasesLista: [
          "Cómo detener una hemorragia",
          "Qué hacer en caso de desmayo",
          "Atención a quemaduras leves",
          "Maniobra de Heimlich (ahogamiento)"
        ],
        contactoTitulo: "Contacto",
        contactoTexto: "Para más información, acude al centro de salud más cercano o llama al 123."
      },
      qu: {
        title: "Sumaq Kawsaypa Ñawpaq Ñiqin",
        navInicio: "Qallariy",
        navRevision: "Rikuy",
        navClases: "Yanapanakuy Yachay",
        navContacto: "Rimanakuy",
        inicioTitulo: "Kawsaykuykiqa Allinmi",
        inicioTexto: "Cellularmanta hamuq saludwan yanapanakuyta riqsichi",
        revisionTitulo: "Rikuy Kawsaykunata",
        nombreLabel: "Sutinchayki:",
        sintomasLabel: "Imanallataq unuykuyki?",
        temperaturaLabel: "Chiri/sumaq (°C):",
        presionLabel: "Yaykunata ñawinchay (kunanpaq):",
        enviarBtn: "Rikuyta apachiy",
        clasesTitulo: "Yanapanakuy Yachaynin",
        clasesLista: [
          "Wasiypi yawarninta sayachiy",
          "Mana kuyuchiykuchkanmi imachus ruwasqa",
          "Q'iwanchikta atipay",
          "Heimlich yanapanakuy (ch'akinakuy)"
        ],
        contactoTitulo: "Rimanakuy",
        contactoTexto: "Aswan yachayninta munankiqa, qhipa kawsay wasiypi riyta munaykuyku." 
      }
    };

    function setLanguage(lang) {
      const t = textos[lang];
      document.getElementById("title").textContent = t.title;
      document.getElementById("navInicio").textContent = t.navInicio;
      document.getElementById("navRevision").textContent = t.navRevision;
      document.getElementById("navClases").textContent = t.navClases;
      document.getElementById("navContacto").textContent = t.navContacto;
      document.getElementById("inicioTitulo").textContent = t.inicioTitulo;
      document.getElementById("inicioTexto").textContent = t.inicioTexto;
      document.getElementById("revisionTitulo").textContent = t.revisionTitulo;
      document.getElementById("nombreLabel").textContent = t.nombreLabel;
      document.getElementById("sintomasLabel").textContent = t.sintomasLabel;
      document.getElementById("temperaturaLabel").textContent = t.temperaturaLabel;
      document.getElementById("presionLabel").textContent = t.presionLabel;
      document.getElementById("enviarBtn").textContent = t.enviarBtn;
      document.getElementById("clasesTitulo").textContent = t.clasesTitulo;

      const lista = document.getElementById("clasesLista");
      lista.innerHTML = "";
      t.clasesLista.forEach(item => {
        const li = document.createElement("li");
        li.textContent = item;
        lista.appendChild(li);
      });

      document.getElementById("contactoTitulo").textContent = t.contactoTitulo;
      document.getElementById("contactoTexto").textContent = t.contactoTexto;
    }
  </script>
</body>
</html>


Listo, ya tienes una página web funcional llamada “Salud Rural Conectada” ✅

🧩 Qué incluye:

Secciones: Inicio, Revisión de salud, Clases de primeros auxilios, Contacto.

Botón para cambiar entre Español y Quechua.

Formularios y contenido adaptado a celulares.

Código simple y ligero, ideal para zonas con internet limitado.


¿Quieres que te ayude a subirla a Internet (gratis con GitHub Pages, por ejemplo)? ¿O quieres agregar videos, mapas de centros de salud o chat médico en el futuro?

