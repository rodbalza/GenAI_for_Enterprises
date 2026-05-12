# 🔍 Módulo 2: Prompting y Búsqueda con Perplexity AI

---

## 2.1 — Cómo hacer prompts en Perplexity

### ¿Qué es Perplexity y por qué es diferente?

La mayoría de buscadores, como Google, te devuelven una lista de enlaces que tú tienes que abrir uno a uno. Perplexity funciona de forma completamente distinta: **busca, contrasta y procesa** la información de múltiples fuentes y te entrega directamente la respuesta en el formato que tú necesites, con las fuentes citadas de forma transparente para que puedas verificarlas.

Por eso se le llama **motor de respuestas** (answer engine), y no simplemente motor de búsqueda. Es como tener un asistente investigador que hace el trabajo de síntesis por ti.

> 💡 **Analogía para recordarlo:** Google es como ir a una biblioteca y que el bibliotecario te señale en qué estante están los libros. Perplexity es como que el bibliotecario haya leído los libros por ti y te entregue el resumen con las páginas de referencia.

---

### ¿Qué modelos de IA usa Perplexity? (Marzo–2026)

Perplexity no tiene un único cerebro, sino que combina varios modelos de IA según el tipo de tarea. Es importante que conozcas esto desde el principio:

**Versión gratuita:** usa **Sonar**, el modelo propio de Perplexity. Sonar está construido sobre LLaMA 3.3 70B de Meta y ha sido entrenado y afinado por el equipo de Perplexity específicamente para búsqueda web en tiempo real, con especial énfasis en veracidad y claridad de las respuestas. Es importante conocer este nombre: cuando veas "Sonar" en la interfaz, es el motor nativo de Perplexity.

**Versión Pro y Max:** da acceso a los modelos más potentes del mercado, incluyendo GPT-5, Claude Opus 4, Gemini 2.5 Pro, Grok 4 y modelos experimentales de NVIDIA. Puedes cambiar el modelo en cualquier momento para comparar respuestas.

---

### ¿Por qué el prompting en Perplexity es diferente?

En herramientas como ChatGPT es habitual escribir prompts del tipo "actúa como experto en marketing y dime…". En Perplexity esto **no es necesario** y puede incluso generar ruido innecesario.

¿Por qué? Porque Perplexity ya opera por defecto como un investigador experto que busca en tiempo real. Lo que importa aquí es definir con precisión tres cosas:

**Tarea:** qué quieres investigar o producir.
**Contexto:** para quién es, en qué mercado, en qué idioma, con qué objetivo.
**Formato de salida:** tabla, reporte, lista, presentación.

> ✅ **Regla de oro del prompting en Perplexity:** no le digas quién tiene que ser, dile qué tiene que hacer, para quién y cómo quieres recibir el resultado.

---

### Estructura de un buen prompt paso a paso

Un prompt efectivo en Perplexity suele combinar estos elementos:

**Ejemplo de prompt débil:**
> "Dime cosas sobre el mercado del software en España."

**Ejemplo de prompt fuerte:**
> "Investiga el mercado de software SaaS para pymes en España en 2025. Necesito un reporte ejecutivo con tamaño de mercado, principales actores, tendencias de crecimiento y retos del sector. Formato: tabla comparativa de competidores y resumen en tres párrafos. Idioma: español."

La diferencia está en que el segundo prompt define la tarea (investigar el mercado SaaS), el contexto (España, 2025, pymes), el formato (tabla + resumen) y el idioma.

---

### Los modos de uso en la interfaz actual

La interfaz de Perplexity es intencionalmente simple y gira en torno a la barra de búsqueda central. Estos son los tres elementos que encontrarás junto al campo de texto y que conviene que conozcas desde el primer día:

El botón **"+"** (a la izquierda) despliega el menú de herramientas y fuentes. Desde aquí puedes subir archivos o imágenes, conectar servicios como Google Drive o Gmail, elegir si la búsqueda se hace en la web general, en documentos académicos o en redes sociales, y acceder a **"Investigación profunda"** (Deep Research), que es la función más potente para generar reportes extensos y que se explica en detalle en el apartado 2.2.

El selector **"Modelo"** (a la derecha) te permite elegir qué cerebro de IA procesa tu consulta: el modelo Sonar propio de Perplexity, GPT-5, Claude, Gemini u otros. En la versión gratuita las opciones de modelo son más limitadas; en la versión Pro tienes acceso a todos los modelos disponibles.

El botón **"Computer"** activa el modo agente, donde Perplexity puede navegar por internet de forma autónoma, interactuar con páginas web y ejecutar tareas más complejas sin que tú tengas que ir paso a paso.

> 💡 **Tip :** para el 90 % de tus consultas del día a día, no necesitas tocar ni el modelo ni el modo Computer. Escribe tu pregunta bien formulada y deja que Perplexity elija automáticamente cómo resolverla. Cuando necesites un reporte profundo, usa el botón "+" → "Investigación profunda".

---

### Casos prácticos adaptados al contexto español

#### Caso 1 — Investigar un pódcast de tecnología e IA en España

Imagina que quieres lanzar un podcast sobre inteligencia artificial orientado al mercado español. Un buen prompt sería:

> "Investiga el panorama de pódcasts de tecnología e inteligencia artificial en España en 2025. Quiero un reporte ejecutivo con: oportunidades del nicho en español, equipamiento mínimo para empezar, plataformas de alojamiento y distribución (Spotify for Podcasters, iVoox, Apple Podcasts), mejores prácticas de publicación y estrategias de crecimiento. Formato: checklist de acción + tabla de plataformas."

**Palabras clave útiles para este prompt:** pódcast tecnología IA España, plataformas distribución pódcast, iVoox, Spotify for Podcasters, mejores prácticas publicación.

---

#### Caso 2 — Estimar TAM, SAM y SOM para una startup SaaS de RRHH en España

Antes de ver el prompt, es importante que entiendas qué significa cada uno de estos tres conceptos, porque son fundamentales en cualquier análisis de mercado para startups o nuevos negocios.

**TAM (Total Addressable Market — Mercado Total Disponible)** es el tamaño máximo del mercado si pudieras vender tu producto a absolutamente todos los clientes potenciales del mundo que podrían necesitarlo. Es el "techo" teórico. Por ejemplo, para un software de RRHH, el TAM sería todo el dinero que gastan todas las empresas del mundo en soluciones de gestión de personas.

**SAM (Serviceable Addressable Market — Mercado al que puedes llegar)** es la parte del TAM a la que realmente puedes dirigirte con tu modelo de negocio actual, dado tu producto, idioma, geografía y canal de ventas. Si tu software está en español y enfocado en empresas de menos de 500 empleados en España, el SAM es solo ese segmento.

**SOM (Serviceable Obtainable Market — Mercado que puedes capturar)** es la porción del SAM que razonablemente podrías conquistar en los próximos 3 a 5 años, teniendo en cuenta tu capacidad operativa, tu equipo comercial y la competencia existente. Es el objetivo realista de negocio a corto y medio plazo.

> 💡 **Para recordarlo fácil:** TAM es el cielo, SAM es el trozo de cielo que puedes alcanzar, y SOM es lo que puedes agarrar con la mano en los próximos años.

Ahora sí, supón que has creado una plataforma SaaS para equipos de recursos humanos que usa IA para automatizar la selección de personal: crea ofertas de trabajo, las publica en portales como Infojobs o LinkedIn, filtra candidatos y analiza el encaje con el puesto. Un prompt completo sería:

> "Estima el TAM, SAM y SOM para una startup SaaS de reclutamiento con IA en España. El producto automatiza la creación de ofertas, la publicación en portales (Infojobs, LinkedIn, Tecnoempleo), el filtrado de candidatos y el análisis de encaje cultural. Empieza por Madrid y Barcelona. Entrégame: una tabla con TAM/SAM/SOM con supuestos metodológicos, una tabla de competidores relevantes (Workday, SAP SuccessFactors, Factorial HR, Personio) y una recomendación para el modelo bottom-up basado en número de empresas objetivo y ticket promedio."

**Palabras clave útiles:** HR tech España, ATS, SaaS RRHH, TAM SAM SOM, bottom-up, Infojobs, Factorial HR.

> ⚠️ **Recuerda siempre:** Perplexity puede cometer errores en cifras de mercado. Verifica las fuentes que cita antes de usar los datos en una presentación o propuesta.

---

### Buenas prácticas para cerrar cualquier prompt

Independientemente del tema, hay elementos que siempre mejoran la calidad de la respuesta:

Especifica el **formato de salida** (tabla, reporte ejecutivo, lista de verificación). Indica las **secciones concretas** que necesitas (fuentes, métricas, próximos pasos). Añade el **uso final** del resultado (presentación a inversores, informe interno, propuesta comercial). Si el resultado tiene datos numéricos, pide que **incluya notas metodológicas** para poder verificar los supuestos.

---

## 2.2 — Investigación Profunda (Deep Research) en Perplexity AI

### ¿Qué es y cómo funciona?

La función de **Investigación Profunda** (Deep Research) es uno de los diferenciadores más potentes de Perplexity. A diferencia de una búsqueda normal que responde en segundos, esta función actúa como un **agente autónomo**: planifica, busca en múltiples fuentes, contrasta la información, itera y vuelve a buscar hasta construir un reporte extenso y bien estructurado.

Visualmente, mientras trabaja verás cómo el sistema va creando el documento en el panel derecho de la interfaz, indicando qué fuentes está consultando en tiempo real.

Tiempo aproximado de espera: entre **5 y 10 minutos** para la mayoría de reportes, pudiendo llegar a 20 minutos en casos muy complejos.

---

### ¿Cómo se activa?

En la interfaz web o en la app móvil verás varios iconos debajo del campo de texto. Selecciona el botón de **Investigación Profunda** (o "Deep Research"), escribe tu pedido con suficiente contexto y envíalo. El sistema empezará a trabajar de forma autónoma.

---

### ¿Qué contexto darle para mejores resultados?

Cuanto más contexto aportes, más útil será el resultado. Intenta siempre incluir:

**Quién eres y en qué trabajas.** Por ejemplo: "Soy consultor de transformación digital trabajando con pymes industriales en el País Vasco."

**El objetivo concreto.** Por ejemplo: "Quiero expandir mis servicios a Portugal e Italia."

**El alcance del análisis.** Por ejemplo: "Necesito una comparativa de ecosistemas de startups y ayudas públicas a la digitalización en ambos países."

**Los criterios de decisión.** Por ejemplo: "Ordénalos según la facilidad de entrada para una empresa española ya consolidada."

---

### Caso práctico — Reporte de expansión internacional para una empresa española

Imagina que trabajas en una startup española de formación online (edtech) con sede en Barcelona y quieres saber a qué mercado europeo expandirte primero. Tu prompt podría ser:

> "Soy el responsable de expansión de una startup edtech española con sede en Barcelona. Ofrecemos formación online en habilidades digitales para empresas. Quiero expandirme a uno de estos mercados: Portugal, Italia o Francia. Crea un reporte maestro comparando los tres países en: tamaño del mercado de formación corporativa online, marco regulatorio laboral para formación continua, competidores locales, ayudas públicas disponibles para empresas extranjeras y facilidad de adaptación del contenido al idioma local. Criterio principal de decisión: rapidez de entrada al mercado. Incluye un resumen ejecutivo de dos páginas y una tabla comparativa final con recomendación razonada."

---

### Cola de tareas y refinamiento

Una de las ventajas de Deep Research es que puedes **añadir instrucciones mientras trabaja** sin perder el progreso. Si mientras genera el reporte se te ocurre que necesitas un apartado adicional, escríbelo en el chat y el sistema lo añadirá a la cola de tareas.

Piensa en la herramienta como en un colaborador que trabaja en paralelo: tú supervisas, añades requisitos y revisas, mientras la IA investiga y redacta.

---

### Formatos de exportación disponibles

Una vez terminado el reporte puedes descargarlo como PDF o como documento Word (DOCX) para editarlo. También puedes exportarlo directamente a Google Drive si lo tienes conectado.

---

### ¿En qué se diferencia de ChatGPT o Gemini en investigación profunda?

Los tres ofrecen investigación profunda, pero hay diferencias prácticas relevantes para el día a día:

Perplexity suele completar el reporte en **5–10 minutos**, mientras que ChatGPT o Gemini pueden tardar entre 30 y 40 minutos en tareas similares. Los documentos de Perplexity tienden a ser más concisos, con más listas y síntesis directa. Para investigaciones con un nivel de profundidad académico muy elevado, ChatGPT o Gemini pueden ser más adecuados. Para acelerar el trabajo del día a día y tener las ideas clave de forma rápida, Perplexity es difícil de superar.

---

### Integración con fuentes privadas

Deep Research también puede trabajar con tus propios documentos. Puedes conectar **Google Drive, OneDrive o Gmail** para que el sistema incluya tus archivos privados como fuente adicional junto a la búsqueda web. Esto es especialmente útil cuando tienes estudios internos o informes de proveedores que no están publicados en internet.

---

## 2.3 — Análisis de Documentos y Archivos con Perplexity

### ¿Qué puedes hacer con archivos en Perplexity?

Perplexity no solo busca en la web: también puede **analizar archivos que tú le adjuntas** y combinar ese análisis con búsqueda en internet para crear entregables profesionales.

Formatos compatibles: PDF, Word, Excel, CSV, PowerPoint y más. Con la versión Pro el análisis de archivos es ilimitado.

El flujo conversacional mantiene una **ventana de contexto**: el sistema recuerda el archivo y todos los pasos anteriores de la conversación, por lo que no tienes que repetir instrucciones en cada mensaje.

---

### Caso práctico 1 — Crear un white paper con bibliografía en APA

Imagina que tienes un informe del Banco de España sobre el impacto de la IA en el mercado laboral español y quieres construir un white paper a partir de él.

El flujo paso a paso sería:

Primero, adjuntas el documento y escribes: *"¿Qué ves en este archivo?"* Esto confirma que el sistema lo ha leído correctamente y entiende su estructura.

Segundo, pides estudios relacionados: *"Busca estudios similares sobre IA y empleo en Europa, especialmente de fuentes como OCDE, Eurostat, CEOE o McKinsey. Entrega la lista en formato bibliográfico APA con un comentario breve sobre cada fuente."*

Tercero, solicitas el white paper: *"Con el informe adjunto y las fuentes encontradas, redacta un white paper de 2.000 palabras sobre el impacto de la IA en el mercado laboral español. Incluye introducción, análisis por sector, conclusiones y bibliografía en APA."*

Tu rol en este flujo es el de **revisor y validador**: abrir las fuentes citadas, verificar que sean reales y pertinentes, y ajustar el contenido final.

---

### ¿Qué hacer si el archivo descargado no tiene extensión?

A veces Perplexity genera un archivo y omite la extensión. Normalmente el formato es Markdown.

La solución es sencilla: añade manualmente la extensión `.md` al nombre del archivo para abrirlo en Notion u Obsidian. Si prefieres otro formato, pide al sistema que exporte en PDF o Word, o que regenere el archivo con la extensión correcta.

---

### Caso práctico 2 — Crear una presentación sobre IA en empresas españolas

Supón que tienes una presentación de formación corporativa sobre transformación digital y quieres crear una versión nueva enfocada en los riesgos del uso de IA no autorizada en empresas (conocida como **Shadow AI**).

El prompt sería:

> "Adjunto una presentación sobre transformación digital. Crea una nueva presentación centrada en Shadow AI (el uso de herramientas de IA no autorizadas por los empleados), manteniendo el mismo tono y estilo visual del original. Incluye: definición de Shadow AI, casos reales de riesgos en empresas españolas o europeas, marco regulatorio (AI Act de la UE), buenas prácticas para equipos de IT y recomendaciones para directivos. Exportar como PPTX."

El sistema detectará la estructura, la paleta de colores y las tipografías del original para mantener la consistencia visual. El resultado incluirá los apartados solicitados y estará listo para editar en PowerPoint o Google Slides.

> ⚠️ **Tip de experiencia:** los elementos visuales como imágenes o gráficos pueden necesitar ajuste manual después de exportar, especialmente si se salen de los márgenes de la diapositiva.

---

### Caso práctico 3 — Generar prospectos de ventas en Excel

Si tienes un Excel con la estructura de tu CRM (columnas de empresa, contacto, cargo, teléfono, correo, estado del pipeline), puedes pedirle a Perplexity que busque en internet nuevos prospectos y los entregue en el mismo formato.

**Ejemplo adaptado a España:**

> "Adjunto un Excel con la estructura de nuestro CRM de ventas. Somos una empresa de software de gestión para restaurantes. Busca restaurantes con más de dos locales en Madrid y Barcelona y rellena un nuevo Excel con la misma estructura. Incluye nombre del negocio, dirección, teléfono si está disponible y web. Comienza con 20 prospectos."

Después puedes iterar: *"Amplía a 50"*, *"Añade restaurantes en Valencia y Sevilla"*, *"Filtra solo los que tengan más de 50 reseñas en Google Maps"*.

> 💡 **Buena práctica antes de empezar:** escribe siempre *"¿Qué ves en el archivo?"* antes de dar instrucciones. Esto asegura que el sistema ha leído correctamente la estructura y evita errores de formato en el resultado.

---

## 2.4 — Combina Perplexity con Otras Herramientas de IA

### La lógica de combinar herramientas

Ninguna herramienta de IA es perfecta para todo. La clave de un flujo de trabajo eficiente está en entender las **fortalezas de cada herramienta** y asignarles las tareas en las que brillan:

**Perplexity** destaca en búsqueda con fuentes verificadas, síntesis de información actualizada e investigación profunda con datos reales.

**Gemini** destaca en personalización de asistentes (Gems), generación y edición de imágenes, y trabajo con archivos de Google Workspace.

**ChatGPT** destaca en razonamiento complejo, memoria de largo plazo entre conversaciones y generación de código.

**Claude** destaca en escritura de documentos largos, análisis de textos extensos y seguimiento preciso de instrucciones.

---

### Caso práctico — Crear un asistente de LinkedIn con Perplexity + Gemini

#### Paso 1: Generar la base de conocimiento en Perplexity

Empieza con este prompt en Perplexity:

> "Ayúdame a crear un manual de buenas prácticas de escritura en LinkedIn para publicar posts exitosos en el mercado español. Incluye: estructura de posts que funcionan, cómo escribir hooks que detienen el scroll, ejemplos prácticos de cada elemento, recomendaciones de extensión, frecuencia de publicación y cómo adaptar el tono para audiencias profesionales en España. Para cada recomendación, añade al menos un ejemplo concreto."

Una vez generado, descarga el manual en **PDF, Markdown o Word**.

#### Paso 2: Subir el manual como base de conocimiento en Gemini

En Gemini, crea un **Gem** (asistente personalizado). Ponle un nombre descriptivo, como *"El escritor de LinkedIn"*. Sube el manual descargado en la sección de conocimiento y añade estas instrucciones operativas:

> "Eres un experto en escribir y editar posts exitosos en LinkedIn para el mercado español. Tienes acceso a un manual con buenas prácticas y ejemplos. Basas tus sugerencias en las ideas y experiencias reales del usuario. Si el usuario no te da una idea clara de lo que quiere publicar, pídela antes de empezar."

#### Paso 3: Probarlo con una idea real

Ejemplo de prueba:

> "Escribe un post sobre que acabo de terminar un máster en inteligencia artificial mientras trabajaba a jornada completa. Quiero transmitir que fue difícil pero que valió la pena, y animar a otros profesionales a formarse en IA."

El asistente puede proponer una estructura tipo *"historia personal con lección"*, con un hook de confesión, el desarrollo de la experiencia, el aprendizaje obtenido y una pregunta final para generar conversación.

---

### Perplexity como validador de fuentes

Uno de los usos más inteligentes y poco conocidos es usar **Perplexity a la inversa**: escribes un borrador en ChatGPT o Claude, lo llevas a Perplexity y le pides que verifique si los datos, cifras y afirmaciones que contiene están respaldados por fuentes reales.

El flujo es:

Primero, redactas un artículo o informe en ChatGPT o Claude. Segundo, pegas el texto en Perplexity con este prompt: *"Revisa este texto y dime si los datos y afirmaciones están respaldados por fuentes verificables. Si encuentras información incorrecta o desactualizada, corrígela y cita las fuentes."* Tercero, usas la versión corregida y verificada como entregable final.

---

### Otras combinaciones útiles para tu flujo de trabajo

**Descriptores de empleo y perfiles profesionales:** investiga con Perplexity las mejores prácticas actuales para redactar ofertas de trabajo en Infojobs o LinkedIn, descarga el manual y crea un gem en Gemini que te ayude a redactarlos.

**Asistente de código especializado:** genera con Perplexity un documento actualizado sobre buenas prácticas en Python, SQL o el lenguaje que uses. Úsalo como base de conocimiento para un asistente de código en Claude o ChatGPT.

**Investigación + redacción en equipo:** comparte el enlace del reporte de Perplexity con tu equipo (la opción *Compartir* genera un enlace público) y usa Claude o ChatGPT para redactar el documento final a partir de esa investigación.

---

## ✅ Ejercicio para practicar

Elige uno de los siguientes retos y resuelve con Perplexity:

**Reto A (básico):** Pide a Perplexity un reporte sobre el estado actual del teletrabajo en España en 2025. Especifica el formato (tabla + resumen ejecutivo) y verifica al menos dos de las fuentes que cite.

**Reto B (intermedio):** Usa Deep Research para comparar las tres principales ciudades españolas (Madrid, Barcelona, Valencia) como destino para abrir una oficina de una startup tecnológica. Pide criterios como coste de oficinas, talento disponible, ecosistema startup y calidad de vida.

**Reto C (avanzado):** Adjunta un documento propio (puede ser un CV, un informe o incluso los apuntes de esta clase) y pide a Perplexity que lo complemente con información actualizada de internet, entregando el resultado en formato white paper con bibliografía en APA.

---

*Documento generado para uso educativo. Actualizado a marzo de 2026.*
