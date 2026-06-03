---
name: gaston-presentation-standard
description: Estándar estratégico y tecnológico de Gastón García para la creación y auditoría de presentaciones de inteligencia de clientes e informes comerciales de Legrand.
---

# Estándar de Presentaciones de Inteligencia de Clientes y Negocio - Gastón García

Este Skill guía el desarrollo y auditoría de reportes estratégicos interactivos desarrollados en HTML/CSS/JS. Su propósito es erradicar las diapositivas estáticas tradicionales (PowerPoint) y el lenguaje burocrático de marketing, reemplazándolos por un estándar de **artesanía digital y comunicación respetuosa orientada a la acción comercial**.

---

## 1. El Estándar de Redacción y Tono (Gaston's Tone)

La comunicación debe sonar **honesta, constructiva, clara y basada en la realidad del instalador B2B**. Se prohíbe el uso de "humo corporativo" o diagnósticos de marketing digital agresivos.

### Pautas Clave de Redacción:

1. **Eliminar los imperativos y órdenes directas a otros equipos ("El fin del *debe*"):**
   * *Incorrecto:* "Soporte Técnico debe resolver las dudas...", "Gestión de Producto debe optimizar..."
   * *Correcto:* "Podemos aprovechar la web local para resolver...", "Optimizar la descarga de fichas...", "Añadir enlaces de contacto..."
   * *Razón:* El presentador no da órdenes verticales a otros departamentos; en su lugar, les facilita herramientas y datos para apoyar su trabajo diario.
2. **Reencuadre positivo y de oportunidad (Reframing):**
   * *Incorrecto:* "Alarma: la velocidad de la página es mala", "Fuga de usuarios: descargan el PDF y abandonan la web."
   * *Correcto:* "La base sólida de rendimiento nos da luz verde para enriquecer el contenido", "Los PDFs son la herramienta de trabajo diario del instalador en la obra; los enriqueceremos con llamados a la acción interactivos."
3. **Evitar la jerga de agencia web (No-Marketing-Talk):**
   * *Incorrecto:* "Tasas de rebote, embudos de conversión, linkbuilding, indexación orgánica."
   * *Correcto:* "Tráfico core (interés real), reconocimiento de marca, descargas de recursos técnicos."
4. **Cierre sobrio y silencioso (Sin gritos):**
   * La diapositiva final debe ser minimalista.
   * Reemplazar "¡Muchas Gracias!" por un sobrio "Muchas gracias" (sin exclamación).
   * Usar colores grises atenuados (`var(--soft)` o `#54514a`) en lugar de colores chillones o rojos oscuros para el texto final.

---

## 2. El Estándar Tecnológico y de Diseño (Tech & UX Stack)

Toda presentación es una **aplicación web interactiva responsiva**, no un conjunto de diapositivas estáticas.

### Requisitos Técnicos Obligatorios:

1. **Dualidad de Formato (Slides vs. Documento):**
   * El archivo HTML debe tener un controlador de estado de visualización en JavaScript (con las clases `body.mode-slides` y `body.mode-doc`).
   * Debe permitir proyectar horizontalmente a pantalla completa (modo diapositivas) y, con un solo clic, transformarse en un informe de lectura continua estructurado verticalmente (modo documento, apto para impresión a PDF).
2. **Filtro Dinámico por Roles (Selector de Personas):**
   * Debe incluir un menú desplegable en la barra superior (`#personaSelect`) conectado a la función `highlightPersona()`.
   * Al seleccionar un rol (ej. Soporte Técnico, Gestión de Producto, CX, Marketing), las secciones correspondientes de toda la presentación deben resaltarse visualmente (`box-shadow`, `scale(1.02)`) para responder a las preguntas de la audiencia en tiempo real.
3. **Gráficos Vectoriales Esculpidos (SVG Nativo):**
   * Se prohíbe terminantemente copiar y pegar capturas de pantalla grises u oscuras de Google Analytics o Search Console.
   * Toda la información cuantitativa debe representarse mediante SVGs nativos diseñados con CSS, asegurando nitidez absoluta en pantallas de alta resolución.
4. **Paleta de Colores Premium de Legrand:**
   * **Warm Cream** (Fondo principal): `#faf8f5`
   * **Crimson** (Acento corporativo): `#e21a22`
   * **Ink** (Texto oscuro): `#1c1b18`
   * **Soft Gray** (Textos atenuados): `#54514a`
   * **Green** (Aciertos y métricas de éxito): `#20734c`

---

## 3. Instrucción para Creación de Presentaciones

Al solicitar la creación de un nuevo reporte, el agente debe generar la estructura HTML interactiva completa basándose en la siguiente plantilla de JavaScript y CSS:

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>[Título Minimalista del Reporte]</title>
  <style>
    :root {
      --ink: #1c1b18;
      --soft: #54514a;
      --paper: #faf8f5;
      --line: #e3ded5;
      --red: #e21a22;
      --green: #20734c;
      --font-display: 'Plus Jakarta Sans', sans-serif;
      --font-body: 'Inter', sans-serif;
    }
    body.mode-slides { overflow: hidden; }
    body.mode-slides .slide { display: none; height: 100vh; }
    body.mode-slides .slide.active { display: flex; }
    body.mode-doc .slide { display: block; margin-bottom: 40px; }
  </style>
</head>
<body class="mode-slides">
  <!-- Cabecera con selector de roles y visualización -->
  <header class="topbar">
    <select id="personaSelect" onchange="highlightPersona()">
      <option value="none">Vista General</option>
      <option value="support">Soporte Técnico</option>
      <option value="product">Gestión de Producto</option>
      <option value="cx">Experiencia de Cliente (CX)</option>
      <option value="marketing">Marketing</option>
    </select>
    <button onclick="setMode('slides')">Diapositivas</button>
    <button onclick="setMode('doc')">Documento</button>
  </header>

  <!-- Diapositivas -->
  <main class="deck-viewport">
    <section class="slide active" id="slide1">
      <!-- Contenido en base al estándar -->
    </section>
  </main>

  <script>
    // Lógica para setMode y highlightPersona
  </script>
</body>
</html>
```

---

## 4. Instrucción para Auditoría de Presentaciones (Audit Mode)

Cuando el usuario pida revisar o refinar un reporte existente, el agente debe realizar una búsqueda exhaustiva del archivo en base a esta lista de control de tono y diseño:

### Lista de Control de Auditoría:

- [ ] **¿Hay verbos imperativos hacia otros equipos?** Buscar palabras como "debe", "tiene que", "se le exige". Cambiarlas por formas propositivas como "podemos facilitar", "destacar el enlace", "vincular".
- [ ] **¿Hay referencias a operaciones físicas que la web no puede controlar?** Verificar si se pide "asegurar stock" o "controlar la distribución local". Reemplazar por soluciones digitales como "conectar con listado de distribuidores locales autorizados".
- [ ] **¿Hay capturas de pantalla o imágenes incrustadas de herramientas analíticas?** Si se encuentran enlaces a capturas estáticas, proponer su reemplazo inmediato por gráficos SVG interactivos integrados en la hoja de estilos de Legrand.
- [ ] **¿La diapositiva final grita?** Verificar si el cierre tiene signos de exclamación ("¡Muchas Gracias!") o textos redundantes sobre el trabajo en equipo. Eliminar el relleno y cambiar a un título minimalista y sobrio en gris suave.
- [ ] **¿Los gráficos tienen leyendas amontonadas?** Si hay leyendas superpuestas, cambiar el diseño CSS para que se apilen verticalmente y utilicen variables HSL limpias.
- [ ] **¿Se usa lenguaje técnico invasivo?** Reemplazar términos como "rebote", "embudo de ventas", "conversiones rotas" por expresiones centradas en el negocio B2B y en la capacitación ("tiempo de lectura", "sesiones core", "academia legrand").
