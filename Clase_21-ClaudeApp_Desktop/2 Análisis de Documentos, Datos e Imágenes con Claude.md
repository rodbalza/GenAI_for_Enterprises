# 2. Análisis de Documentos, Datos e Imágenes con Claude AI

---

## 2.1. Planes disponibles (marzo 2026)

| Característica | Free (Gratuito) | Pro ($20 USD/mes) |
| --- | --- | --- |
| **Modelo predeterminado** | Claude **Sonnet 4.6** (por defecto) y Haiku 4.5 | Sonnet 4.6 + **Opus 4.6** (el más avanzado) |
| **Ventana de contexto** | 1M de tokens en beta (Sonnet 4.6) | 1M de tokens (Sonnet 4.6 y Opus 4.6) con compactación |
| **Selector de modelo** | No disponible | Puedes elegir entre Sonnet, Haiku y Opus |
| **Límite de mensajes** | Bajo: aprox. 30–100 mensajes/día según complejidad. Reseteo cada ~5 horas | Al menos **5 veces más uso** que el plan gratuito. Reseteo cada 5 horas |
| **Acceso en horas pico** | Sin prioridad: puede haber esperas o bloqueos temporales | **Acceso prioritario** durante alta demanda |
| **Pensamiento extendido** | **No disponible** | Disponible: Claude razona paso a paso antes de responder |
| **Subir documentos e imágenes** | Sí (PDF, Word, TXT, CSV, imágenes) | Sí, con capacidades ampliadas de análisis |
| **Artifacts** | Sí (vista previa de código, HTML, SVG) | Sí |
| **Projects (Proyectos)** | Sí (desde febrero 2026) | Sí, con Knowledge Bases |
| **Búsqueda web** | Básica | Completa |
| **Cowork (agente autónomo)** | No disponible | Disponible: Claude trabaja en segundo plano en tareas complejas |
| **Claude Code (agente de terminal)** | No disponible | Disponible: lee tu código, edita archivos, ejecuta comandos |
| **Integración Google Workspace** | No disponible | Disponible: acceso directo a Docs, Gmail y Drive |
| **Privacidad de datos** | Las conversaciones pueden usarse para entrenar el modelo | Puedes desactivar la recopilación de datos |
| **Creación de archivos** | Sí (incluida desde Sonnet 4.6) | Sí (completa: Word, Excel, PowerPoint, PDF) |
| **Memoria entre conversaciones** | No disponible | Disponible |

## 2.2 ¿Cuándo conviene el plan gratuito?

El plan gratuito es más potente que nunca. Desde febrero de 2026, con la llegada de Sonnet 4.6 como modelo por defecto, los usuarios gratuitos tienen acceso a creación de archivos, conectores, skills y compactación de contexto (que permite conversaciones efectivamente ilimitadas). Es suficiente si usas Claude de forma ocasional: resolver dudas puntuales, resumir textos cortos, redactar correos, aprender conceptos o hacer pruebas con la herramienta antes de invertir en el plan de pago.

## 2.3 ¿Cuándo conviene el plan Pro?

El plan Pro se justifica cuando usas Claude a diario como herramienta de trabajo: análisis de documentos extensos, generación de presentaciones, trabajo con datos en Excel, creación de dashboards, tareas de programación o cuando necesitas el modelo Opus 4.6 con su razonamiento avanzado y ventana de contexto de hasta 1 millón de tokens.

> **Nota importante:** También existen los planes Max ($100–$200/mes) para usuarios intensivos, y planes Team ($25–$30/usuario/mes) y Enterprise para organizaciones. Esta clase se enfoca en Free vs Pro, que son los más relevantes para estudiantes.
> 

---

## 2.4 Análisis de documentos e imágenes con Claude

### 2.4.1 ¿Cómo adjuntar archivos?

Existen dos formas de subir archivos a Claude:

1. Haz clic en el **signo +** dentro del cuadro de texto y selecciona "Agregar archivos o fotos".
2. **Arrastra y suelta** directamente el archivo sobre la ventana de chat.

**Formatos soportados:** PDF, Word (.docx), texto plano (.txt), CSV, imágenes (PNG, JPG, GIF, WebP).

### 2.4.2 Buenas prácticas de prompting para análisis de documentos

La clave para obtener buenos resultados con Claude no es solo adjuntar el archivo, sino dar instrucciones claras. Estas son las prácticas fundamentales:

1. **Explica el objetivo:** ¿Qué necesitas decidir o crear a partir del documento?
2. **Define el público:** ¿A quién va dirigido el resultado? (un jefe, un equipo técnico, estudiantes)
3. **Indica el formato de salida:** Tabla, lista con prioridades, pasos de acción, resumen ejecutivo.
4. **Pide "siguientes pasos":** Esto activa la iteración y evita que Claude se detenga en un solo entregable.

**Ejemplo de prompt efectivo:**

```
Adjunto un PDF de 30 páginas sobre estrategia de negocio.
Necesito que:
1. Identifiques las 5 ideas principales del documento
2. Las organices en una tabla con columnas: Idea, Descripción, Impacto estimado
3. Propongas 3 acciones concretas basadas en el contenido
El resultado es para una reunión con directivos, así que usa lenguaje ejecutivo.
```

**Ejemplo de prompt débil:**

```
Resume este documento.
```

La diferencia es enorme: el primer prompt da contexto, formato y audiencia. El segundo deja todo a la interpretación de Claude.

### 2.4.3 Análisis de imágenes (modelos multimodales)

Claude es un modelo multimodal con visión: puede "leer" y "ver" al mismo tiempo. Esto significa que puedes subir fotos de gráficos, esquemas, diagramas, memes o capturas de pantalla y pedir que los interprete.

**¿Qué puede hacer Claude con una imagen?**

- Interpretar esquemas con múltiples ejes y conceptos (por ejemplo, una matriz de perfiles de consultoría).
- Extraer datos de gráficos complejos y convertirlos en tabla.
- Reconocer texto manuscrito y transcribirlo.
- Analizar capturas de pantalla de dashboards o reportes visuales.

**Ejemplo práctico:** Subes una foto de un gráfico de barras con datos de ventas mensuales. Le pides: "Extrae los datos de este gráfico y organízalos en una tabla con columnas Mes y Ventas." Claude genera la tabla lista para copiar.

**Contraste Free vs Pro:**

- En el plan **Free**, puedes subir imágenes y obtener análisis básico.
- En el plan **Pro** con **Opus 4.6**, el análisis es más profundo: mejor interpretación de gráficos complejos, mayor precisión en datos numéricos y capacidad de trabajar con múltiples imágenes en una sola conversación sin agotar el límite rápidamente.

### 2.4.4 Pensamiento extendido

El pensamiento extendido es una función **exclusiva de los planes de pago** (Pro, Max). Cuando se activa, Claude se toma más tiempo para razonar internamente antes de responder. Funciona como un "borrador mental" donde descompone problemas complejos, detecta sus propios errores y produce respuestas más precisas.

**¿Cómo activarlo?**

1. Selecciona un modelo Claude 4 en el selector de modelo.
2. Haz clic en "Herramientas y búsqueda" (Search and tools).
3. Activa el toggle de "Pensamiento extendido" (Extended thinking).

**¿Cuándo usarlo?**

- Análisis de documentos extensos (50+ páginas).
- Cálculos en múltiples pasos con datos financieros.
- Creación de estrategias completas a partir de un marco teórico (como el Business Model Canvas).
- Tareas de programación complejas.
- Cualquier situación donde necesites que Claude "piense más" antes de responder.

**Beneficio concreto:** Cuando combinas un documento extenso + pensamiento extendido + un buen prompt, Claude primero identifica el tipo de documento, luego extrae y consolida el contenido relevante, comprende el marco de trabajo y finalmente redacta una salida sólida y estructurada.

### 2.4.5 Caso práctico: Business Model Canvas

Este ejemplo ilustra el poder de combinar análisis de documentos + pensamiento extendido + prompting.

**Escenario:** Subes un PDF extenso del libro *Business Model Generation* de Osterwalder y Pigneur, y pides crear la estrategia para una plataforma de e-commerce para restaurantes.

**¿Qué entregables puede crear Claude?**

- Un documento completo de estrategia con resumen ejecutivo, problema, solución, visión y misión.
- Un Business Model Canvas en formato tabla con los 9 bloques: segmentos de clientes, propuesta de valor, canales, relaciones con clientes, fuentes de ingresos, recursos clave, actividades clave, socios clave y estructura de costos.
- Un plan de go-to-market con KPIs de seguimiento.
- Todo exportable en formato Word con tablas y estilos.

**Contraste Free vs Pro en este caso:**

- **Free:** Puedes subir el PDF y pedir un resumen o una tabla del Canvas, pero es probable que agotes tu límite de mensajes antes de iterar y refinar el resultado.
- **Pro:** Puedes usar Opus 4.6 con pensamiento extendido, iterar múltiples veces, pedir correcciones y generar el documento Word completo sin preocuparte por los límites.

---

## 2.5. Análisis de datos con Claude

### 2.5.1 ¿Qué puede hacer Claude con un archivo Excel o CSV?

Cuando adjuntas una planilla de datos, Claude puede ejecutar código Python internamente para analizar tus datos. No te entrega fórmulas de Excel, sino tablas, gráficos y dashboards listos.

### 2.5.2 Preparación del análisis: el paso que nadie debe saltarse

Antes de pedir gráficos o modelos, siempre valida que Claude entiende correctamente tu archivo.

**Prompt recomendado como primer paso:**

```
Adjunto un archivo Excel con datos de un CRM. Antes de cualquier análisis,
dime qué ves: cuántas hojas tiene, qué columnas hay en cada una,
y qué crees que representa cada campo.
```

**¿Por qué?** Porque Claude puede asumir erróneamente que "facturación mensual promedio" es lo mismo que "rango de pago", o confundir métricas como *win rate* o *ciclo de ventas*.

### 2.5.3 Buenas prácticas para análisis de datos

1. **Activa el pensamiento extendido** (Pro) para cálculos en múltiples pasos.
2. **Usa Opus 4.6** (Pro) para análisis exigentes con muchos datos.
3. **Entrega contexto claro:** industria, tipo de negocio, objetivo del análisis.
4. **Pide primero "qué ve"** en el archivo antes de cualquier cálculo.
5. **Valida definiciones:** alinea el significado de columnas y métricas con Claude.

### 2.5.4 ¿Qué métricas y entregables genera Claude automáticamente?

A partir de un CRM con hojas de empresas, contactos y oportunidades, Claude puede generar:

- **Totales y tasas:** número de oportunidades, win rate, valor total y ponderado del pipeline.
- **Ciclos de venta:** tiempos por etapa y estado.
- **Funnel de ventas:** leads → contactados → propuestas → cierres.
- **Rendimiento por vendedor:** total vs cierres, win rate por persona.
- **Análisis por producto:** ventas y tasa de conversión por oferta.
- **Motivos de pérdida:** proyecto postergado, competencia, sin presupuesto.
- **Dashboard HTML interactivo:** visualización completa en un solo visor.
- **Hallazgos y recomendaciones:** puntos accionables para mejorar conversión.

### 2.5.5 Python vs Excel: ¿qué aporta y qué limita?

| Aspecto | Python (Claude) | Excel |
| --- | --- | --- |
| Fórmulas editables | No entrega fórmulas | Sí |
| Datasets grandes | Soporta volúmenes altos | Se vuelve lento |
| Análisis avanzados (ML) | Sí: k-means, regresión, etc. | Limitado |
| Dashboards interactivos | Genera HTML reutilizable | Requiere complementos |
| Velocidad de iteración | Alta: pide y recibe | Requiere configuración manual |

### 2.5.6 Segmentación con k-means

Claude puede ejecutar análisis de machine learning directamente. Con k-means, por ejemplo, puede segmentar clientes automáticamente.

**Pasos que ejecuta el modelo:**

1. Selección y normalización de variables numéricas.
2. Elección del número óptimo de clusters (método del codo o silueta).
3. Entrenamiento del modelo k-means y cálculo de centroides.
4. Evaluación con puntaje de silueta.
5. Documentación: perfiles, distribución y métricas por segmento.

**Entregables reutilizables:**

- Excel enriquecido con columnas nuevas: segmento, distancia al centroide, prioridad, valor por día.
- Tablas descriptivas por segmento con perfiles y recomendaciones.
- Dashboard de segmentación con visualización de clusters y estrategias recomendadas.

**Contraste Free vs Pro:**

- **Free:** Claude puede ejecutar Python y generar análisis, pero los límites de mensajes se agotan rápido cuando iteras con datasets complejos.
- **Pro:** Con Opus 4.6 y pensamiento extendido, puedes hacer análisis profundos, iterar sin restricciones severas, y generar múltiples entregables (Excel, dashboard HTML, recomendaciones) en una sola sesión.

---

## 2.6. Creación de presentaciones PowerPoint con Claude

### 2.6.1 ¿Cómo crear un PPT con Claude?

Claude puede generar archivos .pptx completos directamente. El proceso es simple: describe lo que necesitas, entrega la información (aunque esté desordenada) y Claude se encarga de estructurar, crear narrativa y diseñar las diapositivas.

### 2.6.2 ¿Qué incluir en el prompt?

Un buen prompt para presentaciones incluye:

- **Objetivo de la reunión** (entre paréntesis para dar contexto).
- **Temas o propuestas** que deseas cubrir.
- **Fases del proyecto** o cronograma si aplica.
- **Resultados esperados** que deseas comunicar.
- **Preferencias de diseño:** colores, tipografías, estilo (minimalista, corporativo, etc.).

**Ejemplo:**

```
Crea una presentación ejecutiva sobre optimización organizacional.
(Es para una reunión con el comité directivo)

Información a incluir (desordenada):
- Equipos de máximo 5 personas
- Estructura corporativa más plana
- Máximo 5 personas por reunión interna
- Documentación de procesos usando Claude Projects
- Plazo: 2 meses
- Resultados esperados: menos carga laboral, mejor eficiencia, mayor éxito con clientes
- Automatización de procesos manuales

Estilo: minimalista corporativo, acento en azul profundo y coral.
Tipografía: títulos grandes, cuerpo compacto.
```

### 2.6.3 ¿Qué hace Claude con la información?

1. Ordena y prioriza los mensajes clave.
2. Construye una narrativa coherente (por ejemplo: "Trabajar mejor, no más").
3. Define la estructura de slides con títulos, puntos y espacios para íconos.
4. Genera el archivo .pptx descargable.
5. Si tiene pensamiento extendido activo, revisa superposiciones de texto y corrige antes de entregar.

### 2.6.4 Uso de templates corporativos

Puedes subir tu template corporativo (.pptx) con logos y colores, e indicar: "Usa el template adjunto para esta presentación." Claude intentará respetar la estética del template.

También puedes enviar una imagen de referencia: gracias a su capacidad de visión, Claude identifica tonos de color y tipografías para replicarlos.

### 2.6.5 Exportar y editar

El archivo generado se puede:

- Abrir en **Google Slides** (subiendo a Drive).
- Descargar como **.pptx** y abrir en **PowerPoint**.
- Editar elementos individuales: mover, redimensionar, cambiar colores, insertar íconos.
- Pedir más slides o nuevas secciones manteniendo el mismo estilo en la conversación.

**Contraste Free vs Pro:**

- **Free:** Puedes pedir que Claude genere contenido para slides en formato texto, pero la creación de archivos .pptx completos puede verse limitada.
- **Pro:** Generación completa de archivos .pptx con diseño profesional, iteración para corregir detalles, uso de pensamiento extendido para verificar calidad visual, y mayor capacidad para combinar documentos fuente + template + instrucciones de diseño en una sola sesión.

---