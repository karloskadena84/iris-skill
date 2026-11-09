# Contexto: Agente de pendientes (Todoist + Google Calendar + MCP)

Fecha: 2026-11-08  
Versión: 2.0 (UX mejorada)

## 1. Problema

- Anota los pendientes en sticky notes por todos lados y aun así se le olvidan.
- Maneja muchos pendientes a la vez.
- El papel no tiene disparador: espera a que lo mires, y ya se olvidó.

## 2. Proceso base acordado

1. **Captura en un solo lugar**, en menos de 5 segundos.
2. **Todo con fecha y hora**: un pendiente sin hora es un deseo.
3. **Revisión diaria** de 5 minutos.
4. **Revisión semanal** de 15 minutos (domingo).

Reglas de apoyo:

- Regla de los 2 minutos: si toma menos, se hace ya.
- Máximo 3 prioridades al día.
- Sticky notes solo como apoyo visual, nunca como fuente de verdad.

## 3. Apps evaluadas (búsqueda web, 2026)

| App | Para qué destaca |
|---|---|
| Todoist | Mejor captura rápida, lenguaje natural, voz (Ramble), multiplataforma |
| TickTick | Múltiples recordatorios por tarea, calendario, hábitos |
| Apple Recordatorios / Google Tasks | Gratis e integradas al celular |
| Any.do | Pensada para quienes olvidan usar las apps |
| Things 3 | Muy pulida, solo Apple, pago único |

Decisión: **Todoist + Google Calendar**, para que el calendario evite llenar el celular de alarmas.

## 4. Idea del agente

Un agente conectado por **MCP** que:

1. Recibe pendientes por **nota de voz o texto**.
2. Los crea en **Todoist** con fecha, urgencia y duración estimada.
3. **Evalúa a diario** la lista: urgencia, plazo, duración y huecos libres del calendario.
4. Reserva bloques de tiempo y configura alarmas en **Google Calendar**.
5. Aprende de los hábitos del usuario y ajusta sus recomendaciones con el tiempo.

El agente vive en un **cliente con soporte MCP** (Claude, Cursor, o cualquier interfaz compatible). El usuario interactúa por chat (texto o voz). Todoist y Google Calendar se conectan exclusivamente mediante servidores MCP. El agente nunca crea cuentas ni maneja contraseñas; solo guía el proceso de autorización OAuth.

## 5. Flujo de captura mejorado (Mejora 1)

### Principios
- Captura continua: el usuario puede dictar varios pendientes seguidos sin interrupciones innecesarias.
- El agente solo pregunta cuando falta información crítica (fecha límite o duración cuando es imprescindible).
- Si puede inferir una fecha razonable a partir del contexto o del calendario, lo hace y confirma después.

### Feedback inmediato
Después de cada captura (o lote) el agente responde con:

- **Voz corta** (si el cliente lo permite):  
  «Listo. Reunión con Ana mañana a las 10, prioridad alta, bloque de 45 minutos reservado.»

- **Tarjeta visual** (cuando el cliente lo soporte):
  - Título de la tarea
  - Fecha y hora
  - Nivel de urgencia
  - Duración estimada + margen de seguridad
  - Bloque de calendario reservado (si aplica)

### Modo de confirmación progresiva
- Primeras interacciones: siempre confirma antes de crear la tarea o el bloque.
- Después de N interacciones correctas (configurable, por defecto 8-10): pasa a modo automático.
- El usuario puede volver al modo «pregúntame siempre» en cualquier momento con un comando simple.

## 6. Resumen diario accionable (Mejora 2)

Cada mañana el agente entrega un resumen de **20-30 segundos de voz** + lista visual accionable.

Contenido del resumen:
- Las 3-4 prioridades del día.
- Indicador de carga: «Hoy tienes 3 bloques importantes + 25 min de rápidos. Te quedan 1 h 40 min libres.»
- Si el día está sobrecargado, propone proactivamente qué adelantar o posponer.

Acciones rápidas por cada ítem (botones o comandos de voz):
- Hacer ahora
- Mover a otro hueco
- Agrupar en «Rápidos»
- Bajar urgencia
- Eliminar / Archivar

El resumen se puede solicitar también en cualquier momento con «¿Qué tengo hoy?» o «Resumen del día».

## 7. Gestión inteligente del volumen (Mejora 3)

### Tres cajones
- **Hoy / Mañana** → alarmas fuertes
- **Esta semana** → alarmas moderadas
- **Puede esperar** → sin alarmas (solo bloque visible)

### Reglas de volumen
- Tope diario de 3-4 pendientes importantes. Si se supera, el agente avisa de forma suave y ofrece reorganizar.
- Tareas de menos de 10 minutos se agrupan automáticamente en un único bloque «Rápidos» con una sola alarma.
- En la revisión semanal se detectan tareas que llevan varios días sin movimiento y se propone: Hacer / Reprogramar / Archivar.

### Vista de cajones
Siempre accesible mediante el comando «Muéstrame los cajones» o «¿Cómo está mi semana?».

## 8. Confianza y control del usuario (Mejora 4)

- Historial reciente consultable: «¿Qué hiciste esta mañana?» o «Últimas acciones».
- Comando universal de deshacer: «Deshaz la última acción».
- Transparencia: el agente explica sus decisiones cuando es relevante  
  («Subí la urgencia porque vence mañana y no tienes hueco libre hasta el jueves»).
- El usuario puede cambiar en cualquier momento entre:
  - Modo «Pregúntame siempre»
  - Modo automático

## 9. Onboarding y primeros usos (Mejora 5)

Flujo de primer uso (máximo 60-90 segundos):

1. El agente se presenta en una frase:  
   «Dime lo que tienes que hacer. Yo lo organizo en Todoist y te aviso en el momento justo en el calendario.»
2. Detecta si el usuario ya tiene Todoist y Google Calendar conectados vía MCP.
3. Si faltan conexiones, guía paso a paso la autorización OAuth (el usuario hace clic, el agente nunca pide contraseñas).
4. Primera captura con confirmación explícita para generar confianza.
5. Al finalizar el onboarding, pregunta preferencia de plataforma (iPhone / Android) solo para adaptar ejemplos de comandos de voz.

Objetivo: que el usuario vea valor real en los primeros 3-5 usos.

## 10. Alarmas y notificaciones más humanas (Mejora 6)

| Nivel     | Criterio                        | Alarmas                                      |
|-----------|----------------------------------|----------------------------------------------|
| Crítica   | Vence en menos de 24 h          | 3 h antes + 1 h antes + al iniciar           |
| Alta      | Vence en 1 a 3 días             | Día anterior + 1 h antes                     |
| Normal    | Vence en 4 a 14 días            | Solo al iniciar                              |
| Baja      | Sin fecha dura o > 14 días      | Solo bloque visible, sin sonar               |

El usuario puede silenciar temporalmente un tipo de alarma («Hoy no me avises de las normales») o cambiar el comportamiento de cualquier nivel.

## 11. Aprendizaje y personalización progresiva (Mejora 7)

El agente mejora con el uso:

- Compara duración estimada vs duración real y ajusta el margen de seguridad (inicialmente ~25 %).
- Detecta patrones del usuario («Normalmente haces las llamadas los martes por la mañana») y los usa para sugerir fechas y horas.
- Aprende qué tipo de tareas el usuario suele completar o posponer y adapta las recomendaciones de prioridad.
- Si un servicio falla (Todoist o Calendar), guarda la acción localmente y reintenta automáticamente.

## 12. Arquitectura y cliente (Mejora 8)

- El agente vive en un **cliente con soporte MCP** (Claude, Cursor u otro compatible).
- Toda la interacción se realiza por chat (texto o voz).
- Las integraciones con Todoist y Google Calendar se realizan exclusivamente a través de servidores MCP.
- No se utiliza WhatsApp ni aplicaciones de mensajería externas como canal principal.
- El cliente debe permitir:
  - Envío de mensajes de voz
  - Visualización de tarjetas / mensajes estructurados
  - Ejecución de herramientas MCP (Todoist + Google Calendar)

Ventajas de este enfoque:
- Un solo lugar de interacción.
- Control total de la conversación y del historial.
- Facilidad para añadir nuevas capacidades vía MCP en el futuro.
- Sin dependencia de plataformas de mensajería de terceros.

## 13. Estado actual

- Documento de diseño actualizado a versión 2.0 con las 8 mejoras de UX.
- Aún no hay servidores MCP de Todoist ni Google Calendar conectados en esta conversación.
- Siguiente paso crítico: elegir y conectar los MCP correspondientes.

## 14. Preguntas abiertas (actualizadas)

- ¿Qué cliente MCP concreto se usará como hogar principal del agente?
- ¿Qué servidores MCP oficiales o comunitarios de Todoist y Google Calendar se eligen?
- ¿Un solo usuario o soporte multi-usuario desde el inicio?
- ¿Cuántas interacciones correctas se consideran suficientes para pasar a modo automático por defecto?

## 15. Siguientes pasos

- [ ] Elegir el cliente MCP donde vivirá el agente
- [ ] Seleccionar y conectar los servidores MCP de Todoist y Google Calendar
- [ ] Prototipo 1: captura por texto + creación de tarea en Todoist + feedback inmediato
- [ ] Prototipo 2: resumen diario accionable (aunque sea solo texto)
- [ ] Añadir lectura de huecos libres y creación de bloques en Google Calendar
- [ ] Implementar reglas de urgencia y sistema de alarmas
- [ ] Añadir confirmación progresiva y comando de deshacer
- [ ] Onboarding guiado + detección de plataforma
- [ ] Agrupación de «Rápidos» y detección de sobrecarga
- [ ] Sistema de aprendizaje de duraciones y patrones
- [ ] Revisión semanal automatizada
