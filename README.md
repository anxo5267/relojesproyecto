<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="description" content="Este es un catálogo de relojes de lujo" />
  <meta name="keywords" content="relojes,lujo,ap,audemars,piguet,patek,phillipe,rolex" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <meta name="author" content="Anxo Barros" />
  <title>AB Jewellery</title>
  <link href="https://fonts.googleapis.com/css2?family=EB+Garamond:wght@400;700&display=swap" rel="stylesheet" />
  <style>
    body {
      margin: 0;
      padding: 0;
      background-color: #FFFAFF;
      color: #1A1A1A;
      font-family: 'EB Garamond', serif;
      text-align: center;
      transition: background-color 0.3s ease, color 0.3s ease;
    }
    /* Modo oscuro */
    body.dark-mode {
      background-color: #121212;
      color: #eee;
    }

    header {
      font-size: 36px;
      font-weight: bold;
      margin-top: 40px;
      color: #3E78B2;
      display: flex;
      justify-content: center;
      align-items: center;
      position: relative;
    }

    /* Botón modo oscuro */
    #modo-btn {
      position: absolute;
      right: 20px;
      top: 50%;
      transform: translateY(-50%);
      background: none;
      border: none;
      cursor: pointer;
      font-size: 24px;
      color: #3E78B2;
      transition: color 0.3s ease;
      padding: 4px;
      width: 36px;
      height: 36px;
      display: flex;
      align-items: center;
      justify-content: center;
      border-radius: 6px;
    }
    #modo-btn:hover {
      color: #2a5a9e;
      background-color: #d4bbaf22;
    }

    header a {
      color: inherit;
      text-decoration: none;
      cursor: pointer;
      flex-grow: 1;
    }

    header a:hover {
      text-decoration: underline;
    }

    .video-container {
      margin: 30px auto;
      display: none; /* Oculto por defecto */
    }

    .video-container iframe {
      display: block;
      margin: 0 auto;
      width: 95vw;
      max-width: 1000px;
      height: 562px;
    }

    nav {
      margin-top: 30px;
    }

    nav a {
      margin: 0 20px;
      color: #1A1A1A;
      font-size: 20px;
      text-decoration: none;
      border-bottom: 2px solid transparent;
      transition: all 0.3s ease;
    }

    nav a:hover {
      color: #3E78B2;
      border-bottom: 2px solid #3E78B2;
    }

    body.dark-mode nav a {
      color: #ccc;
    }
    body.dark-mode nav a:hover {
      color: #7da5d7;
      border-bottom-color: #7da5d7;
    }

    .seccion {
      display: none; /* Oculto por defecto */
      margin-top: 40px;
      padding: 20px;
      border-top: 1px solid #D4BBA0;
    }
    body.dark-mode .seccion {
      border-top-color: #555;
    }

    .seccion img {
      width: 250px;
      height: 250px;
      object-fit: contain;
      display: block;
      margin: 0 auto 15px auto;
      border: 3px solid #3E78B2;
      border-radius: 5px;
    }

    ul {
      list-style: none;
      padding: 0;
      font-size: 22px;
    }

    ul li {
      margin: 10px 0 30px 0;
    }

    .boton-ver-mas {
      display: inline-block;
      margin-top: 15px;
      padding: 10px 20px;
      background-color: #D4BBA0;
      color: #3E78B2;
      text-decoration: none;
      font-size: 18px;
      font-weight: bold;
      border-radius: 5px;
      transition: background-color 0.3s ease;
    }

    .boton-ver-mas:hover {
      background-color: #C0A890;
    }
    body.dark-mode .boton-ver-mas {
      background-color: #5a4d3b;
      color: #c3b591;
    }
    body.dark-mode .boton-ver-mas:hover {
      background-color: #7e7050;
    }

    /* Estilos específicos para la tabla */
    #comparacion table {
      width: 90%; /* Hace la tabla más grande */
      max-width: 1000px; /* Ancho máximo para pantallas grandes */
      margin: 30px auto;
      border-collapse: collapse;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    }

    #comparacion th {
      background-color: #3E78B2; /* Fondo azul para los encabezados */
      color: #FFFFFF; /* Letras blancas para contraste */
      padding: 15px;
      text-align: left;
      font-size: 1.2em; /* Hace las letras un poco más grandes */
    }

    #comparacion td {
      background-color: #F5F5DC; /* Fondo beige para las celdas de datos */
      color: #1A1A1A;
      padding: 12px 15px;
      text-align: left;
      border-bottom: 1px solid #ddd;
    }

    body.dark-mode #comparacion th {
        background-color: #2a5a9e; /* Azul más oscuro en modo oscuro */
    }

    body.dark-mode #comparacion td {
        background-color: #333; /* Fondo más oscuro en modo oscuro */
        color: #eee;
    }

    #comparacion tr:nth-child(even) td {
      background-color: #EEE8D5; /* Ligeramente diferente beige para filas pares */
    }

    body.dark-mode #comparacion tr:nth-child(even) td {
        background-color: #444; /* Fondo más oscuro en modo oscuro para filas pares */
    }

    /* Estilos específicos para la sección de historia */
    #historia h3 {
      font-size: 1.8em; /* Títulos de etapa más grandes */
      color: #3E78B2; /* Mismo azul que el título de la página */
      margin-top: 30px;
      margin-bottom: 15px;
    }

    body.dark-mode #historia h3 {
        color: #7da5d7; /* Azul más claro en modo oscuro */
    }

    #historia p {
      font-size: 1.1em; /* Información en párrafos con tamaño de letra variable */
      line-height: 1.6;
      text-align: justify; /* Justifica el texto para una mejor lectura */
      margin: 0 auto 15px auto;
      max-width: 800px; /* Limita el ancho del párrafo para legibilidad */
    }

    #historia ul {
        list-style: disc; /* Vuelve a poner viñetas de disco */
        text-align: left; /* Alinea las listas a la izquierda */
        margin: 0 auto 20px auto;
        max-width: 780px; /* Asegura que la lista se alinee con los párrafos */
        padding-left: 40px; /* Espacio para las viñetas */
    }

    #historia ul li {
        font-size: 1.05em; /* Tamaño de letra ligeramente diferente */
        margin-bottom: 8px;
    }
  </style>
</head>
<body>
  <header>
    <a href="#" onclick="mostrarInicio()">AB Jewellery</a>
    <button id="modo-btn" aria-label="Cambiar modo claro/oscuro" title="Cambiar modo claro/oscuro">☀️</button>
  </header>

  <nav>
    <a href="#" onclick="mostrar('ap')">Audemars Piguet</a>
    <a href="#" onclick="mostrar('patek')">Patek Philippe</a>
    <a href="#" onclick="mostrar('vacheron')">Vacheron Constantin</a>
    <a href="#" onclick="mostrar('rolex')">Rolex</a>
    <a href="#" onclick="mostrar('hublot')">Hublot</a>
    <a href="#" onclick="mostrar('comparacion')">Comparación de modelos</a>
    <a href="#" onclick="mostrar('historia')">Historia de los Relojes</a>
  </nav>

  <div id="ap" class="seccion">
    <h2>Audemars Piguet</h2>
    <ul>
      <li>
        <img src="https://dynamicmedia.audemarspiguet.com/is/image/audemarspiguet/watch-931?size=582,0&fmt=avif-alpha&dpr=off" alt="Reloj Audemars Piguet Code 11.59 Minute Repeater Supersonnerie" />
        Code 11.59 by Audemars Piguet
        <br />
        <a href="https://www.audemarspiguet.com/com/es/watch-collection/code-1159/26395NR.OO.D002KB.01.html" target="_blank" class="boton-ver-mas">Ver Más</a>
      </li>
      <li>
        <img src="https://dynamicmedia.audemarspiguet.com/is/image/audemarspiguet/watch-932?size=568,0&dpr=off&fmt=avif-alpha&dpr=off" alt="Reloj Audemars Piguet Royal Oak Automático" />
        Royal Oak Automático
        <br />
        <a href="https://www.audemarspiguet.com/com/es/watch-collection/royal-oak/15510ST.OO.1320ST.08.html" target="_blank" class="boton-ver-mas">Ver Más</a>
      </li>
      <li>
        <img src="https://dynamicmedia.audemarspiguet.com/is/image/audemarspiguet/watch-1130?size=568,0&dpr=off&fmt=avif-alpha&dpr=off" alt="Reloj Audemars Piguet Royal Oak Concept Tourbillon Companion" />
        Royal Oak Concept Tourbillon «Companion»
        <br />
        <a href="https://www.audemarspiguet.com/com/es/watch-collection/royal-oak-concept/26656TI.GG.D019VE.01.html" target="_blank" class="boton-ver-mas">Ver Más</a>
      </li>
    </ul>
  </div>

  <div id="patek" class="seccion">
    <h2>Patek Philippe</h2>
    <ul>
      <li>
        <img src="https://static.patek.com/images/articles/face_white/350/5178G_012_1.jpg" alt="Patek Phillipe Grandes Complicaciones 5178G-012" />
        Patek Phillipe Grandes Complicaciones 5178G-012
        <br />
        <a href="https://www.patek.com/es/coleccion/grandes-complicaciones/5178G-012" target="_blank" class="boton-ver-mas">Ver Más</a>
      </li>
      <li>
        <img src="https://static.patek.com/images/articles/face_white/350/6119G_001_1.jpg" alt="Patek Philippe Calatrava 6119G-001" />
        Patek Philippe Calatrava 6119G-001
        <br />
        <a href="https://www.patek.com/es/coleccion/calatrava/6119G-001" target="_blank" class="boton-ver-mas">Ver Más</a>
      </li>
      <li>
        <img src="https://static.patek.com/images/articles/face_white/350/7118_1453G_001_1.jpg" alt="Patek Philippe Nautilus 7118/1453G-001" />
        Patek Philippe Nautilus 7118/1453G-001
        <br />
        <a href="https://www.patek.com/es/coleccion/nautilus/7118-1453G-001" target="_blank" class="boton-ver-mas">Ver Más</a>
      </li>
    </ul>
  </div>

  <div id="vacheron" class="seccion">
    <h2>Vacheron Constantin</h2>
    <ul>
      <li>
        <img src="https://www.vacheron-constantin.com/dam/rcq/vac/18/11/42/1/1811421.png.transform.vacproddetailshd.png" alt="Patrimony fecha-día retrógrados" />
        Patrimony fecha-día retrógrados
        <br />
        <a href="https://www.vacheron-constantin.com/ww/es/collections/patrimony/4000u-000r-b516.html" target="_blank" class="boton-ver-mas">Ver Más</a>
      </li>
      <li>
        <img src="https://www.vacheron-constantin.com/dam/rcq/vac/20/14/92/4/2014924.png.transform.vacproddetailshd.png" alt="Fiftysix calendario completo" />
        Fiftysix calendario completo
        <br />
        <a href="https://www.vacheron-constantin.com/ww/es/collections/fiftysix/4000e-000r-b065.html" target="_blank" class="boton-ver-mas">Ver Más</a>
      </li>
      <li>
        <img src="https://www.vacheron-constantin.com/dam/rcq/vac/13/44/25/5/1344255.png.transform.vacproddetailshd.png" alt="Malte Fases lunares" />
        Malte Fases lunares
        <br />
        <a href="https://www.vacheron-constantin.com/ww/es/collections/malte/7000m-000r-b109.html" target="_blank" class="boton-ver-mas">Ver Más</a>
      </li>
    </ul>
  </div>
  <div id="hublot" class="seccion">
    <h2>Hublot</h2>
    <ul>
      <li>
        <img src="https://www.hublot.com/sites/default/files/styles/watch_item_desktop_1x_scale_no_crop_600_6000_/public/2024-06/Arsham-droplet-front-shot-chain-916.NX_.5202.NK-v2.png?itok=Fv8-1fG3" alt="Exceptional Timepieces Arsham Droplet" />
        Exceptional Timepieces Arsham Droplet
        <br />
        <a href="https://www.hublot.com/es-es/watches/exceptional-timepieces/arsham-droplet-73-2-mm" class="boton-ver-mas">Ver Más</a>
      </li>
      <li>
        <img src="https://www.hublot.com/sites/default/files/styles/watch_item_desktop_1x_scale_no_crop_600_6000_/public/2025-01/Spirit-of-Big-Bang-Sky-Blue-Ceramic-42-mm-Soldier-Shot.png?itok=hB2rzeT5" alt="Spirit of Big Bang Sky Blue Ceramic" />
        Spirit of Big Bang Sky Blue Ceramic
        <br />
        <a href="https://www.hublot.com/es-es/watches/big-bang/spirit-of-big-bang-sky-blue-ceramic-42-mm" target="_blank" class="boton-ver-mas">Ver Más</a>
      </li>
      <li>
        <img src="https://www.hublot.com/sites/default/files/styles/watch_item_desktop_1x_scale_no_crop_600_6000_/public/2025-03/hublot-big-bang-20-magic-gold-431.MX_.1330.RX_.png?itok=SVTkGVV0" alt="Big Bang 20th Anniversary Full Magic Gold" />
        Big Bang 20th Anniversary Full Magic Gold
        <br />
        <a href="https://www.hublot.com/es-int/watches/big-bang/big-bang-20th-anniversary-full-magic-gold-43-mm" target="_blank" class="boton-ver-mas">Ver Más</a>
      </li>
    </ul>
  </div>

  <div id="rolex" class="seccion">
    <h2>Rolex</h2>
    <ul>
      <li>
        <img src="https://media.rolex.com/image/upload/q_auto:eco/f_auto/t_v7-majesty/c_limit,w_1200/v1/catalogue/2025/upright-c/m228235-0003" alt="Reloj Rolex Day-Date oro rosa" />
        Day-Date oro rosa
        <br />
        <a href="https://www.rolex.com/es/watches/day-date/m228235-0003" target="_blank" class="boton-ver-mas">Ver Más</a>
      </li>
      <li>
        <img src="https://media.rolex.com/image/upload/q_auto:eco/f_auto/t_v7-majesty/c_limit,w_1200/v1/catalogue/2025/upright-c/m126613lb-0002" alt="Reloj Rolex Submariner Date Bluesy" />
        Rolex Submariner date Bluesy
        <br />
        <a href="https://www.rolex.com/es/watches/submariner/m126613lb-0002" target="_blank" class="boton-ver-mas">Ver Más</a>
      </li>
      <li>
        <img src="https://media.rolex.com/image/upload/q_auto:eco/f_auto/t_v7-majesty/c_limit,w_1200/v1/catalogue/2025/upright-c/m126500ln-0001" alt="Reloj Rolex Cosmograph Daytona" />
        Cosmograph Daytona
        <br />
        <a href="https://www.rolex.com/es/watches/cosmograph-daytona/m126500ln-0001" target="_blank" class="boton-ver-mas">Ver Más</a>
      </li>
    </ul>
  </div>

<div id="historia" class="seccion">
  <h2>La Historia de los Relojes — Una Narrativa en Cinco Etapas</h2>

  <h3>Etapa 1: El despertar de la necesidad — medir el tiempo en la antigüedad</h3>
  <p>Desde tiempos antiguos, el ser humano ha sentido la necesidad de comprender el paso del tiempo. Los primeros métodos de medición fueron naturales y rudimentarios:</p>
  <ul>
    <li>Los egipcios usaban **relojes de sol** para dividir el día.</li>
    <li>Las **clepsidras**, relojes de agua desarrollados en Mesopotamia y China, marcaban el tiempo por el flujo constante del líquido.</li>
    <li>Aunque no eran precisos, fueron avances fundamentales en la evolución del tiempo medido.</li>
  </ul>

  <h3>Etapa 2: El arte mecánico comienza a latir — los primeros relojes mecánicos en la Edad Media</h3>
  <p>En la Edad Media, alrededor del siglo XIII, aparecieron los primeros relojes mecánicos en Europa. Estos usaban engranajes y pesas para medir el tiempo.</p>
  <ul>
    <li>Los **monasterios** usaban estos relojes para organizar las oraciones y actividades diarias.</li>
    <li>Posteriormente, se instalaron en torres de ciudades, convirtiéndose en símbolos de orden y progreso.</li>
    <li>Aunque no eran muy precisos, marcaron el inicio de la automatización en la medición del tiempo.</li>
  </ul>

  <h3>Etapa 3: El péndulo que cambió el tiempo — precisión y ciencia en el siglo XVII</h3>
  <p>En 1656, Christiaan Huygens revolucionó la relojería con el **reloj de péndulo**, mejorando la precisión significativamente.</p>
  <ul>
    <li>Los marineros podían determinar mejor su longitud en el mar, ayudando a la exploración.</li>
    <li>Nacieron los **relojes de bolsillo**, combinando precisión y elegancia.</li>
    <li>Este avance permitió el desarrollo de la relojería científica.</li>
  </ul>

  <h3>Etapa 4: El reloj en la muñeca — revolución industrial y la democratización del tiempo</h3>
  <p>Con la Revolución Industrial, los relojes se hicieron accesibles a más personas:</p>
  <ul>
    <li>Los **relojes de pulsera** comenzaron como un accesorio femenino.</li>
    <li>Durante la Primera Guerra Mundial, los soldados los adoptaron por su practicidad.</li>
    <li>Los relojes automáticos eliminaron la necesidad de cuerda manual.</li>
  </ul>

  <h3>Etapa 5: La era digital y más allá — relojes inteligentes y el futuro del tiempo</h3>
  <p>En el siglo XXI, los relojes han evolucionado con la tecnología:</p>
  <ul>
    <li>Los **relojes digitales** mejoraron la precisión absoluta.</li>
    <li>Los **smartwatches** ahora monitorean la salud, reciben notificaciones y conectan dispositivos.</li>
    <li>La relojería moderna combina tradición con innovación tecnológica.</li>
  </ul>
</div>


<div id="comparacion" class="seccion">
  <h2>Comparación de Modelos</h2>
  <p>Aquí puedes ver una comparación de los materiales y precios de todos los modelos de relojes disponibles.</p>
  
  <table border="1">
    <tr>
      <th>Marca</th>
      <th>Modelo</th>
      <th>Material</th>
      <th>Precio Aproximado</th>
    </tr>
    <tr>
      <td>Audemars Piguet</td>
      <td>Code 11.59 Minute Repeater Supersonnerie</td>
      <td>Oro rosa y titanio</td>
      <td>$80,000</td>
    </tr>
    <tr>
      <td>Audemars Piguet</td>
      <td>Royal Oak Automático</td>
      <td>Acero inoxidable</td>
      <td>$25,000</td>
    </tr>
    <tr>
      <td>Audemars Piguet</td>
      <td>Royal Oak Concept Tourbillon «Companion»</td>
      <td>Titanio</td>
      <td>$150,000</td>
    </tr>
    <tr>
      <td>Patek Philippe</td>
      <td>Grandes Complicaciones 5178G-012</td>
      <td>Oro blanco</td>
      <td>$120,000</td>
    </tr>
    <tr>
      <td>Patek Philippe</td>
      <td>Calatrava 6119G-001</td>
      <td>Oro blanco</td>
      <td>$30,000</td>
    </tr>
    <tr>
      <td>Patek Philippe</td>
      <td>Nautilus 7118/1453G-001</td>
      <td>Oro blanco y diamantes</td>
      <td>$70,000</td>
    </tr>
    <tr>
      <td>Vacheron Constantin</td>
      <td>Patrimony fecha-día retrógrados</td>
      <td>Oro rosa</td>
      <td>$52,893</td>
    </tr>
    <tr>
      <td>Vacheron Constantin</td>
      <td>Fiftysix calendario completo</td>
      <td>Oro rosa</td>
      <td>$47,646</td>
    </tr>
    <tr>
      <td>Vacheron Constantin</td>
      <td>Malte Fases lunares</td>
      <td>Oro rosa</td>
      <td>$43,256</td>
    </tr>
      <td>Rolex</td>
      <td>Day-Date oro rosa</td>
      <td>Oro rosa</td>
      <td>$40,000</td>
    </tr>
    <tr>
      <td>Rolex</td>
      <td>Submariner Date Bluesy</td>
      <td>Acero inoxidable y oro amarillo</td>
      <td>$15,000</td>
    </tr>
    <tr>
      <td>Rolex</td>
      <td>Cosmograph Daytona</td>
      <td>Acero inoxidable</td>
      <td>$14,000</td>
    </tr>
    <tr>
      <td>Hublot</td>
      <td>Exceptional Timepieces Arsham Droplet</td>
      <td>Titanio</td>
      <td>$92,000</td>
    </tr>
    <tr>
      <td>Hublot</td>
      <td>Spirit of Big Bang Sky Blue Ceramic</td>
      <td>Cerámica</td>
      <td>$28,500</td>
    </tr>
    <tr>
      <td>Hublot</td>
      <td>Big Bang 20th Anniversary Full Magic Gold</td>
      <td>Oro</td>
      <td>$42,200</td>
    </tr>
  </table>
</div>


  <script>
    function mostrarInicio() {
      const secciones = document.querySelectorAll('.seccion');
      secciones.forEach((sec) => (sec.style.display = 'none'));
      document.querySelector('.video-container').style.display = 'block';
    }

    function mostrar(id) {
      const secciones = document.querySelectorAll('.seccion');
      secciones.forEach((sec) => (sec.style.display = 'none'));
      document.querySelector('.video-container').style.display = 'none';
      document.getElementById(id).style.display = 'block';
    }

    document.addEventListener('DOMContentLoaded', () => {
      mostrarInicio();

      const modoBtn = document.getElementById('modo-btn');
      const body = document.body;

      // Inicializar icono según modo
      function actualizarIcono() {
        modoBtn.textContent = body.classList.contains('dark-mode') ? '🌙' : '☀️';
      }

      actualizarIcono();

      modoBtn.addEventListener('click', () => {
        body.classList.toggle('dark-mode');
        actualizarIcono();
      });
    });
  </script>

  <div class="video-container">
    <iframe
      width="100%"
      height="100%"
      src="https://www.youtube.com/embed/xisfAByPeVM?autoplay=1&controls=0&showinfo=0&rel=0&modestbranding=1&loop=1"
      title="YouTube video player"
      frameborder="0"
      allowfullscreen
    ></iframe>
  </div>
</body>
</html>



