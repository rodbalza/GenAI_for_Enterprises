# Tutorial guiado n8n: Formulario n8n + Google Sheets + Edit Fields + Google Calendar + Gmail

## 1. Nuevo caso práctico

Una empresa de **consultoría de marketing digital** quiere captar solicitudes de nuevos clientes mediante un **formulario creado directamente en n8n**.

Cuando una persona rellena el formulario, el flujo debe hacer lo siguiente:

1. Captar los datos desde un **n8n Form**.
2. Guardar automáticamente la solicitud en **Google Sheets**.
3. Preparar los datos con **Edit Fields**.
4. Crear una reunión inicial en **Google Calendar**.
5. Enviar un email de confirmación con **Gmail**.
6. Actualizar la fila de Google Sheets indicando que la solicitud fue procesada.

---

## 2. Nuevo flujo general

```text
n8n Form Trigger
        ↓
Google Sheets
        ↓
Edit Fields
        ↓
Google Calendar
        ↓
Gmail
        ↓
Google Sheets
```

Ya no usaremos Google Drive.

---

## 3. Preparación de Google Sheets

Crea una hoja llamada:

```text
Solicitudes Clientes Marketing
```

Crea estas columnas:

| Columna | Descripción |
|---|---|
| id_solicitud | Código único de la solicitud |
| fecha_solicitud | Fecha en la que se recibe la solicitud |
| nombre_cliente | Nombre de la persona interesada |
| email_cliente | Correo del cliente |
| empresa | Empresa del cliente |
| servicio_interes | Servicio solicitado |
| presupuesto_estimado | Presupuesto aproximado |
| fecha_reunion | Fecha propuesta para la reunión |
| hora_reunion | Hora propuesta para la reunión |
| estado | Estado de la solicitud |
| evento_calendar | ID o enlace del evento |
| email_enviado | Sí / No |

---

## 4. Paso 1: Crear el workflow

En n8n:

1. Crea un nuevo workflow.
2. Ponle este nombre:

```text
Captación de clientes con formulario n8n
```

---

## 5. Paso 2: Añadir el nodo n8n Form Trigger

Este nodo será el formulario que rellenará el cliente.

1. Añade un nodo nuevo.
2. Busca:

```text
Form Trigger
```

3. Configura el formulario con un título, por ejemplo:

```text
Solicitud de consultoría de marketing digital
```

4. Añade una descripción:

```text
Completa este formulario para solicitar una reunión inicial con nuestro equipo.
```

---

## Campos del formulario

Configura estos campos en el **Form Trigger**:

| Campo del formulario | Tipo de campo | Obligatorio |
|---|---|---|
| nombre_cliente | Text | Sí |
| email_cliente | Email | Sí |
| empresa | Text | Sí |
| servicio_interes | Dropdown o Text | Sí |
| presupuesto_estimado | Number | Sí |
| fecha_reunion | Date | Sí |
| hora_reunion | Text | Sí |

Para `servicio_interes`, puedes usar un desplegable con opciones como:

```text
SEO local
Campañas en redes sociales
Email marketing
Auditoría de marketing digital
Automatización comercial
Analítica web
```

Para `hora_reunion`, puedes pedir que el usuario escriba la hora en formato:

```text
10:00
11:30
16:00
```

---

## 6. Paso 3: Probar el formulario

1. Ejecuta el nodo **Form Trigger**.
2. Abre el enlace del formulario.
3. Rellena un ejemplo:

| Campo | Valor de prueba |
|---|---|
| nombre_cliente | Laura Gómez |
| email_cliente | laura@email.com |
| empresa | Belleza Natural SL |
| servicio_interes | Campañas en redes sociales |
| presupuesto_estimado | 2500 |
| fecha_reunion | 2026-05-20 |
| hora_reunion | 10:30 |

Cuando envíes el formulario, n8n recibirá esos datos como entrada del flujo.

---

## 7. Paso 4: Añadir Google Sheets para registrar la solicitud

Ahora guardaremos los datos del formulario en Google Sheets.

1. Añade un nodo nuevo después del **Form Trigger**.
2. Busca:

```text
Google Sheets
```

3. Conecta:

```text
Form Trigger → Google Sheets
```

4. Configura el nodo así:

| Campo | Valor |
|---|---|
| Resource | Sheet Within Document |
| Operation | Append Row |
| Document | Solicitudes Clientes Marketing |
| Sheet | Hoja principal |

---

## Mapeo de columnas

Mapea los campos de Google Sheets con los datos del formulario:

| Columna de Google Sheets | Valor en n8n |
|---|---|
| id_solicitud | `{{ "SOL-" + $now.toMillis() }}` |
| fecha_solicitud | `{{ $now.toFormat("yyyy-MM-dd") }}` |
| nombre_cliente | `{{ $json.nombre_cliente }}` |
| email_cliente | `{{ $json.email_cliente }}` |
| empresa | `{{ $json.empresa }}` |
| servicio_interes | `{{ $json.servicio_interes }}` |
| presupuesto_estimado | `{{ $json.presupuesto_estimado }}` |
| fecha_reunion | `{{ $json.fecha_reunion }}` |
| hora_reunion | `{{ $json.hora_reunion }}` |
| estado | `Pendiente` |
| evento_calendar | dejar vacío |
| email_enviado | `No` |

---

## Resultado esperado

Después de ejecutar este nodo, la hoja de cálculo debería tener una nueva fila parecida a esta:

| id_solicitud | fecha_solicitud | nombre_cliente | email_cliente | empresa | servicio_interes | presupuesto_estimado | fecha_reunion | hora_reunion | estado | evento_calendar | email_enviado |
|---|---|---|---|---|---|---|---|---|---|---|---|
| SOL-1770000000000 | 2026-05-12 | Laura Gómez | laura@email.com | Belleza Natural SL | Campañas en redes sociales | 2500 | 2026-05-20 | 10:30 | Pendiente |  | No |

---

## 8. Paso 5: Añadir Edit Fields

Ahora prepararemos los datos que van a usar Calendar, Gmail y la actualización final de Sheets.

1. Añade un nodo nuevo.
2. Busca:

```text
Edit Fields
```

3. Conecta:

```text
Google Sheets → Edit Fields
```

---

## Campos que debes crear en Edit Fields

Añade estos campos:

| Campo nuevo | Tipo | Valor |
|---|---|---|
| id_solicitud | String | `{{ $('Google Sheets').item.json.id_solicitud }}` |
| nombre_cliente | String | `{{ $('Google Sheets').item.json.nombre_cliente }}` |
| email_cliente | String | `{{ $('Google Sheets').item.json.email_cliente }}` |
| empresa | String | `{{ $('Google Sheets').item.json.empresa }}` |
| servicio_interes | String | `{{ $('Google Sheets').item.json.servicio_interes }}` |
| presupuesto_estimado | String | `{{ $('Google Sheets').item.json.presupuesto_estimado }}` |
| fecha_reunion | String | `{{ $('Google Sheets').item.json.fecha_reunion }}` |
| hora_reunion | String | `{{ $('Google Sheets').item.json.hora_reunion }}` |
| asunto_email | String | `Confirmación de reunión - {{ $('Google Sheets').item.json.empresa }}` |
| estado_final | String | `Procesado` |
| email_enviado | String | `Sí` |
| inicio_reunion | String | `{{ $('Google Sheets').item.json.fecha_reunion + "T" + $('Google Sheets').item.json.hora_reunion + ":00" }}` |

---

## Salida esperada de Edit Fields

```json
{
  "id_solicitud": "SOL-1770000000000",
  "nombre_cliente": "Laura Gómez",
  "email_cliente": "laura@email.com",
  "empresa": "Belleza Natural SL",
  "servicio_interes": "Campañas en redes sociales",
  "presupuesto_estimado": "2500",
  "fecha_reunion": "2026-05-20",
  "hora_reunion": "10:30",
  "asunto_email": "Confirmación de reunión - Belleza Natural SL",
  "estado_final": "Procesado",
  "email_enviado": "Sí",
  "inicio_reunion": "2026-05-20T10:30:00"
}
```

---

## 9. Paso 6: Añadir Google Calendar

Ahora se creará una reunión en Google Calendar.

1. Añade un nodo nuevo.
2. Busca:

```text
Google Calendar
```

3. Conecta:

```text
Edit Fields → Google Calendar
```

4. Configura el nodo así:

| Campo | Valor |
|---|---|
| Resource | Event |
| Operation | Create |
| Calendar | Tu calendario principal |
| Start Time | `{{ $json.inicio_reunion }}` |
| End Time | `{{ DateTime.fromISO($json.inicio_reunion).plus({ hours: 1 }).toISO() }}` |
| Summary | `Reunión inicial - {{ $json.empresa }}` |
| Attendees | `{{ $json.email_cliente }}` |
| Location | Reunión online |

---

## Descripción del evento

En el campo de descripción puedes colocar:

```text
Reunión inicial con cliente interesado en servicios de marketing digital.

Cliente: {{ $('Edit Fields').item.json.nombre_cliente }}
Empresa: {{ $('Edit Fields').item.json.empresa }}
Email: {{ $('Edit Fields').item.json.email_cliente }}
Servicio solicitado: {{ $('Edit Fields').item.json.servicio_interes }}
Presupuesto estimado: {{ $('Edit Fields').item.json.presupuesto_estimado }} €

Solicitud registrada desde formulario n8n.
```

---

## 10. Paso 7: Añadir Gmail

Ahora enviaremos un correo automático al cliente.

1. Añade un nodo nuevo.
2. Busca:

```text
Gmail
```

3. Conecta:

```text
Google Calendar → Gmail
```

4. Configura el nodo así:

| Campo | Valor |
|---|---|
| Resource | Message |
| Operation | Send |
| To | `{{ $('Edit Fields').item.json.email_cliente }}` |
| Subject | `{{ $('Edit Fields').item.json.asunto_email }}` |

---

## Cuerpo del email

Puedes usar este texto:

```text
Hola {{ $('Edit Fields').item.json.nombre_cliente }},

Gracias por contactar con nuestro equipo de marketing digital.

Hemos recibido tu solicitud correctamente.

Datos registrados:

Empresa:
{{ $('Edit Fields').item.json.empresa }}

Servicio solicitado:
{{ $('Edit Fields').item.json.servicio_interes }}

Presupuesto estimado:
{{ $('Edit Fields').item.json.presupuesto_estimado }} €

Hemos creado una reunión inicial para revisar tu caso.

Fecha:
{{ $('Edit Fields').item.json.fecha_reunion }}

Hora:
{{ $('Edit Fields').item.json.hora_reunion }}

Nos pondremos en contacto contigo en la fecha indicada.

Un saludo,

Equipo de Consultoría de Marketing Digital
```

---

## 11. Paso 8: Actualizar Google Sheets al final

Después de crear el evento y enviar el correo, actualizaremos la fila original.

1. Añade otro nodo:

```text
Google Sheets
```

2. Conecta:

```text
Gmail → Google Sheets
```

3. Configura el nodo así:

| Campo | Valor |
|---|---|
| Resource | Sheet Within Document |
| Operation | Append or Update Row |
| Document | Solicitudes Clientes Marketing |
| Sheet | Hoja principal |
| Matching Column | id_solicitud |
| Value to Match | `{{ $('Edit Fields').item.json.id_solicitud }}` |

---

## Columnas a actualizar

Mapea estas columnas:

| Columna | Valor |
|---|---|
| estado | `{{ $('Edit Fields').item.json.estado_final }}` |
| evento_calendar | `{{ $('Google Calendar').item.json.id }}` |
| email_enviado | `{{ $('Edit Fields').item.json.email_enviado }}` |

El resto de columnas pueden quedarse sin tocar.

---

## 12. Resultado final esperado en Google Sheets

Al terminar el flujo, la fila debería quedar así:

| id_solicitud | nombre_cliente | empresa | servicio_interes | estado | evento_calendar | email_enviado |
|---|---|---|---|---|---|---|
| SOL-1770000000000 | Laura Gómez | Belleza Natural SL | Campañas en redes sociales | Procesado | ID del evento | Sí |

---

## 13. Flujo final completo

```text
1. Form Trigger
   Recoge los datos del cliente desde un formulario de n8n.

2. Google Sheets
   Inserta una nueva fila con la solicitud recibida.

3. Edit Fields
   Prepara los datos para Calendar, Gmail y la actualización final.

4. Google Calendar
   Crea una reunión inicial con el cliente.

5. Gmail
   Envía un correo de confirmación al cliente.

6. Google Sheets
   Actualiza la fila original con estado, evento creado y email enviado.
```

---

## 14. Ejercicio propuesto para estudiantes

### Enunciado

Crea una automatización en n8n para una empresa de marketing digital que permita captar solicitudes de nuevos clientes mediante un formulario.

El flujo debe cumplir estos requisitos:

1. Crear un formulario con n8n Form.
2. Captar los siguientes datos:
   - Nombre del cliente.
   - Email.
   - Empresa.
   - Servicio solicitado.
   - Presupuesto estimado.
   - Fecha de reunión.
   - Hora de reunión.
3. Guardar automáticamente la solicitud en Google Sheets.
4. Preparar los datos con Edit Fields.
5. Crear una reunión en Google Calendar.
6. Enviar un email automático de confirmación con Gmail.
7. Actualizar Google Sheets indicando:
   - Estado: Procesado.
   - Evento de Calendar creado.
   - Email enviado: Sí.

---

## 15. Posibles errores comunes

| Error | Causa probable | Solución |
|---|---|---|
| El formulario no ejecuta el flujo | El workflow no está activo o no se está probando correctamente | Ejecutar el workflow o activar el flujo |
| Google Sheets no recibe datos | Los nombres de campos no coinciden | Revisar los nombres del formulario y el mapeo |
| Calendar falla con la hora | Formato incorrecto de fecha/hora | Usar formato `YYYY-MM-DDTHH:mm:ss` |
| Gmail no envía el correo | Credenciales incorrectas | Revisar permisos de Gmail |
| No se actualiza la fila | No coincide `id_solicitud` | Verificar que el mismo ID se usa al insertar y actualizar |

---

## 16. Versión resumida para explicar en clase

```text
El usuario rellena un formulario en n8n.
n8n guarda la solicitud en Google Sheets.
Edit Fields organiza los datos.
Google Calendar crea una reunión.
Gmail envía la confirmación.
Google Sheets se actualiza con el estado final.
```

Este flujo es más limpio que el anterior porque el proceso empieza directamente con un formulario de n8n, sin necesidad de que alguien escriba manualmente una nueva fila en Google Sheets.
