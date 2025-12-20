# 00-intro-css

```html
<!DOCTYPE html>
<!--
  CLASE: Aplicación de estilos y responsividad (Parte I)
  EJERCICIO 00 — INTRO A CSS (Live Coding guiado)

  Este archivo está pensado para EXPLICAR a estudiantes que:
  - Ayer solo vieron HTML.
  - Hoy comienzan con CSS desde cero.

  Objetivos (alineado al PPT):
  1) Entender qué es CSS y por qué se usa (separar contenido vs diseño).
  2) Aprender la "estructura" de una regla CSS: selector { propiedad: valor; }
  3) Ver 3 formas de aplicar CSS: en línea, embebido y archivo externo.
  4) Conocer el modelo de caja: margin / border / padding / content.
  5) Practicar tipografía básica: font-family, font-size, font-weight, line-height, text-align.
  6) Conocer Flexbox para alinear y distribuir elementos.
  7) Ver un ejemplo MUY simple de responsividad con @media.

  ✅ IMPORTANTE: En este ejercicio usamos CSS en un ARCHIVO EXTERNO (mejor práctica),
  pero adentro dejamos un ejemplo chiquitito de "estilo en línea" SOLO para mostrar la diferencia.

  Ruta del CSS:
  ./assets/css/styles.css

  SUGERENCIA PARA EL LIVE CODING (cómo lo dictas):
  - Paso A: abre index.html en el navegador (sin tocar nada).
  - Paso B: abre assets/css/styles.css y muestra:
      1) Reset básico
      2) Regla por etiqueta (body, h1, p)
      3) Regla por clase (.card, .badge)
      4) Regla por ID (#destacado)
      5) Modelo de caja en .box-demo
      6) Flexbox en .nav y .cards
      7) Media query al final (responsivo)
  - Paso C: mini desafío en clase:
      1) Cambiar el color de fondo del header.
      2) Aumentar el padding de .card.
      3) Cambiar el justify-content del menú.
      4) Editar el @media para que la "grilla" cambie antes (por ejemplo 700px).

  ------------------------------------------------------------
  TIP docente (frase simple para explicar CSS):
  "HTML es la estructura / contenido. CSS es la ropa / estilo."
-->
<html lang="es">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>00 - Intro a CSS (Live Coding)</title>

    <!--
      ✅ Forma recomendada: archivo externo.
      Ventajas:
      - Orden: HTML queda limpio.
      - Reutilización: el mismo CSS sirve para varias páginas.
      - Mantención: un cambio en CSS puede afectar todo el sitio.
    -->
    <link rel="stylesheet" href="assets/css/styles.css" />
  </head>

  <body>
    <!-- Header -->
    <header class="site-header">
      <div class="wrap">
        <h1>Intro a CSS</h1>
        <p class="subtitle">
          Hoy pasamos de <strong>HTML</strong> a <strong>CSS</strong>: diseño, tipografías, cajas y una pizca de responsividad.
        </p>

        <!--
          ⚠️ Ejemplo de estilo en línea (NO recomendado para proyectos reales).
          Lo usamos para mostrar la idea:
          - "style" vive dentro del HTML.
          - Cuesta mantenerlo cuando crece el proyecto.

          Luego comparamos con clases (recomendado).
        -->
        <a
          href="#demo"
          class="btn"
          style="border: 2px dashed rgba(255,255,255,0.5);"
          >Ir a la demo (tiene un borde inline)</a
        >
      </div>
    </header>

    <main class="wrap" id="demo">
      <!--
        Tarjetas (cards)
        Vamos a practicar selectores:
        - Por etiqueta: p { ... }
        - Por clase: .card { ... }
        - Por ID: #destacado { ... }
      -->
      <section class="cards" aria-label="Tarjetas de explicación">

        <article class="card">
          <p class="badge">1) Regla CSS</p>
          <h2>¿Cómo se escribe CSS?</h2>
          <p>
            Una regla CSS tiene esta forma:
            <code>selector { propiedad: valor; }</code>
          </p>
          <p>
            Ejemplo: <code>p { color: blue; }</code> aplica a <strong>todos</strong> los &lt;p&gt;.
          </p>
        </article>

        <article class="card" id="destacado">
          <p class="badge">2) Selectores</p>
          <h2>Etiqueta, clase e ID</h2>
          <ul>
            <li><strong>Etiqueta</strong>: <code>p</code>, <code>h1</code>, <code>header</code>...</li>
            <li><strong>Clase</strong>: <code>.card</code> (se puede repetir en muchos elementos)</li>
            <li><strong>ID</strong>: <code>#destacado</code> (idealmente único en la página)</li>
          </ul>
          <p class="note">
            Este artículo tiene <code>id="destacado"</code> para mostrar estilos más específicos.
          </p>
        </article>

        <article class="card">
          <p class="badge">3) Cascada</p>
          <h2>¿Por qué se llama “Cascading”?</h2>
          <p>
            Porque si dos reglas afectan al mismo elemento,
            el navegador decide cuál gana según:
          </p>
          <ol>
            <li><strong>Especificidad</strong> (ID &gt; clase &gt; etiqueta)</li>
            <li><strong>Orden</strong> (la regla que aparece después puede sobreescribir)</li>
          </ol>
        </article>
        
      </section>

      <!-- Modelo de caja -->
      <section class="card" aria-label="Modelo de caja">
        <p class="badge">4) Modelo de caja</p>
        <h2>Margin, border y padding</h2>
        <p>
          Piensa en cada elemento como una caja:
          <strong>contenido</strong> dentro,
          luego <strong>padding</strong> (relleno),
          luego <strong>border</strong> (borde),
          y por fuera <strong>margin</strong> (espacio externo).
        </p>

        <div class="box-row">
          <div class="box-demo">
            <p><strong>Caja A</strong></p>
            <p class="small">Tiene margin / border / padding</p>
          </div>

          <div class="box-demo box-demo--alt">
            <p><strong>Caja B</strong></p>
            <p class="small">Mismo concepto, distinto estilo</p>
          </div>
        </div>

        <p class="note">
          En el CSS busca <code>.box-demo</code> para ver dónde está el margen, el borde y el padding.
        </p>
      </section>

      <!-- Flexbox + Responsividad -->
      <section class="card" aria-label="Flexbox y responsividad">
        <p class="badge">5) Flexbox + @media</p>
        <h2>Menú simple (Flexbox)</h2>

        <!-- Menú: en CSS lo hacemos flex -->
        <nav class="nav" aria-label="Navegación de ejemplo">
          <a href="#">Inicio</a>
          <a href="#">Cursos</a>
          <a href="#">Ejercicios</a>
          <a href="#">Contacto</a>
        </nav>

        <p>
          En pantallas grandes, el menú se ve horizontal.
          En pantallas pequeñas, se apila.
          Eso lo controlamos con una regla <code>@media</code>.
        </p>

        <p class="note">
          Busca en el CSS: <code>.nav { display: flex; ... }</code> y luego la sección <code>@media (...)</code>.
        </p>
      </section>

      <footer class="footer">
        <p>
          ✅ Listo: ya viste lo esencial para comenzar.
          Ahora puedes abrir los ejercicios 01–04 en la carpeta <code>01-aplicando-css-al-html</code>.
        </p>
      </footer>
    </main>
  </body>
</html>

```
# CSS

```css
    /*
    00 — INTRO A CSS (assets/css/styles.css)

    ⚠️ Este archivo tiene MUCHOS comentarios porque está hecho para enseñar.

    RECUERDA: CSS se escribe como:
    selector {
        propiedad: valor;
    }

    ---------------------------------------------------------
    1) Reset y configuración base
    ---------------------------------------------------------
    */

    /* Buena práctica: box-sizing para que padding + border no "rompan" el ancho */
    * {
    box-sizing: border-box;
    }

    /* Estilos generales para toda la página */
    body {
    margin: 0;              /* quitamos margen por defecto del navegador */
    font-family: Arial, sans-serif;
    line-height: 1.6;       /* altura de línea: mejora legibilidad */
    background: #0b1220;
    color: #e5e7eb;
    }

    /* Un contenedor para que el contenido no quede pegado a los bordes */
    .wrap {
    /*
    
    min() no “adivina” si estás en móvil o en desktop.
    Lo único que hace es esto: calcula los dos valores en ese momento y se queda con el más pequeño.
    2) ¿Qué hace min(1100px, 92vw)?
    EJEMPLO
    En cada tamaño de pantalla, el navegador calcula:

        1100px (siempre es 1100, fijo)
        92vw (depende del ancho de pantalla)

    L uego toma el menor.

    */
    width: min(1100px, 92vw);  /* "min" limita el ancho máximo y adapta al viewport */
    margin: 0 auto;            /* centra horizontalmente */
    }

    /*
    ---------------------------------------------------------
    2) Tipografía básica (PPT: font-family / font-size / font-weight / line-height)
    ---------------------------------------------------------
    */

    h1, h2 {
    line-height: 1.2;     /* títulos con menor interlineado */
    }

    h1 {
    margin: 0 0 8px;
    font-size: 32px;      /* tamaño del texto */
    }

    h2 {
    margin: 0 0 10px;
    font-size: 22px;
    }

    p {
    margin: 0 0 10px;
    color: #cbd5e1;
    }

    .subtitle {
    margin-bottom: 14px;
    }

    code {
    font-family: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", monospace;
    font-size: 0.95em;
    background: rgba(255, 255, 255, 0.08);
    padding: 2px 6px;
    border-radius: 8px;
    color: #fff;
    }

    /*
    ---------------------------------------------------------
    3) Header (modelo de caja: padding y border)
    ---------------------------------------------------------
    */

    .site-header {
    background: linear-gradient(135deg, #111827, #1f2937);
    border-bottom: 1px solid rgba(255, 255, 255, 0.12);
    padding: 24px 0; /* padding = relleno interno */
    }

    .btn {
    display: inline-block;        /* para poder aplicar padding bien */
    text-decoration: none;
    color: #111827;
    background: #a5b4fc;
    padding: 10px 14px;
    border-radius: 12px;
    font-weight: bold;
    }

    /*
    ---------------------------------------------------------
    4) Tarjetas (cards) + selectores por clase
    ---------------------------------------------------------
    */

    .cards {
    /* Flexbox: 1 columna en móvil, se adapta con wrap */
    display: flex;
    flex-wrap: wrap;        /* permite que bajen a otra línea */
    gap: 14px;              /* espacio entre tarjetas */
    padding: 18px 0;
    }

    .card {
    background: #111827;
    border: 1px solid rgba(255, 255, 255, 0.10);
    border-radius: 16px;

    /* Modelo de caja */
    padding: 16px;          /* relleno interno */
    margin: 0;              /* no necesitamos margen extra */
    box-shadow: 0 10px 25px rgba(0, 0, 0, 0.20);

    /* Tamaño flexible: base 320px pero puede crecer 
        flex-grow: 1;
        flex-shrink: 1;
        flex-basis: 320px;

        1) flex-grow: 1
        En ingles significa crecer, aumentar
        Puede crecer si sobra espacio en la fila.
        Si hay espacio “extra”, el elemento se agranda.
        El 1 es una “proporción”.
        Si todos los items tienen grow: 1, crecen por igual.

        2) flex-shrink: 1
        En Ingles Encogerse/Reducirse
        Puede achicarse si falta espacio.
        Si la pantalla es más pequeña y no caben, el elemento reduce su tamaño.
        1 significa “sí, achícate si es necesario”.
        Si fuera 0, sería “no te achiques” (y eso puede provocar overflow/scroll horizontal).

        3) flex-basis: 320px
        En ingles es Base
        Es el tamaño base ideal antes de crecer o achicarse.
        Piensa: “quiero que mida alrededor de 320px si se puede”.
        Luego grow y shrink deciden si se ajusta.

        flex-grow: 1;
        flex-shrink: 1;
        flex-basis: 320px;
    
    */
    flex: 1 1 320px;

    }

    /* Selector por ID (más específico que clase) */
    #destacado {
    border-color: rgba(99, 102, 241, 0.55);
    background: rgba(99, 102, 241, 0.10);
    }

    .badge {
    display: inline-block;
    font-size: 12px;
    color: #c7d2fe;
    border: 1px solid rgba(99, 102, 241, 0.45);
    background: rgba(99, 102, 241, 0.20);
    padding: 6px 10px;
    border-radius: 999px;
    margin: 0 0 10px;
    }

    .note {
    font-size: 12px;
    color: #94a3b8;
    }

    /*
    ---------------------------------------------------------
    5) Modelo de caja (margin / border / padding)
    ---------------------------------------------------------
    */

    .box-row {
    display: flex;
    /* 
        flex-wrap: nowrap; /* valor por defecto
        flex-wrap controla si los elementos (items) dentro de un contenedor flex
        pueden “bajar” a otra línea cuando ya no caben en una sola fila.
    */
    flex-wrap: wrap;
    gap: 12px;
    margin-top: 10px; /* margin = espacio externo (fuera del elemento) */
    }

    .box-demo {
    /* content */
    background: rgba(16, 185, 129, 0.12);

    /* padding = espacio entre el contenido y el borde */
    padding: 14px;

    /* border = borde del elemento */
    border: 2px solid rgba(16, 185, 129, 0.35);

    /* margin = espacio fuera del borde */
    margin: 6px 0;

    border-radius: 14px;
    flex: 1 1 260px;
    }

    .box-demo--alt {
    background: rgba(251, 191, 36, 0.12);
    border-color: rgba(251, 191, 36, 0.35);
    }

    .small {
    font-size: 13px;
    }

    /*
    ---------------------------------------------------------
    6) Flexbox: menú
    ---------------------------------------------------------
    */

    .nav {
    /* Convertimos el contenedor en "flex container" */
    display: flex;

    /* gap separa los items sin necesidad de margin en cada link */
    gap: 10px;

    /* en pantallas grandes: horizontal */
    flex-direction: row;

    /* si no cabe, que baje a otra línea */
    flex-wrap: wrap;

    padding: 12px;
    border-radius: 14px;
    border: 1px solid rgba(255, 255, 255, 0.10);
    background: rgba(255, 255, 255, 0.04);
    }

    .nav a {
    text-decoration: none;
    color: #e5e7eb;
    border: 1px solid rgba(255, 255, 255, 0.14);
    background: rgba(255, 255, 255, 0.06);
    padding: 8px 12px;
    border-radius: 999px;
    }

    /* Hover = feedback visual cuando pasas el mouse */
    .nav a:hover {
    background: rgba(99, 102, 241, 0.20);
    border-color: rgba(99, 102, 241, 0.45);
    }

    /*
    ---------------------------------------------------------
    7) Responsividad (media query)
    ---------------------------------------------------------

    @media significa:
    "Si se cumple esta condición, aplica estos estilos".

    Aquí decimos:
    - Si la pantalla es chica (max-width: 520px)
    - Cambiamos el menú a columna (vertical)
    */

    @media (max-width: 520px) {
    .nav {
        flex-direction: column; /* menú apilado */
        align-items: stretch;
    }

    .btn {
        width: 100%;
        text-align: center;
    }
    }

    .footer {
    padding: 16px 0 40px;
    color: #94a3b8;
    }

```