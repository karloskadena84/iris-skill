# Flujo de uso de Iris

**Versión:** 1.2.0 (contexto de reuniones)

## 1. Primer uso (Onboarding – 60-90 segundos)

1. El usuario abre el cliente MCP y escribe o dice:  
   «Hola, quiero organizar mis pendientes».

2. Iris se presenta:  
   «Dime lo que tienes que hacer. Yo lo organizo en Todoist y te aviso en el momento justo en el calendario.»

3. Verifica las conexiones MCP de Todoist y Google Calendar.
   - Si faltan → guía la autorización OAuth paso a paso.
   - Si ya están → pasa a la primera captura.

4. (Opcional) Pregunta plataforma solo para adaptar ejemplos.

5. Invita a la primera captura con confirmación explícita.

---

## 2. Captura de pendientes

- Dictado continuo de uno o varios pendientes.
- Feedback inmediato con fecha, urgencia, duración y bloque si aplica.
- Confirmación progresiva según el modo del usuario.

---

## 3. Resumen diario (con reuniones)

Cuando el usuario pide “¿Qué tengo hoy?” o “Resumen del día”:

1. Iris consulta el calendario y las tareas.
2. Entrega:
   - Reuniones del día (hora + título)
   - 3-4 prioridades de trabajo
   - Tiempo libre aproximado
   - Tareas pospuestas destacadas
3. Ofrece acciones rápidas: Hacer ahora / Mover / Posponer / etc.

Ejemplo de estructura de respuesta:
> Hoy: 2 reuniones + 3 bloques de trabajo.
> • 10:00 – Reunión con Ana (presupuesto)
> • 15:30 – Sync de equipo
> Prioridades: …
> Tienes ~1 h 20 min libres entre reuniones.

---

## 4. Posponer respetando reuniones

1. Usuario: “Posponer” / “Cuando tenga hueco” / “En una hora”
2. Iris:
   - Mira el calendario
   - Evita solaparse con reuniones
   - Propone o ejecuta el nuevo horario
   - Confirma de forma breve
   - Mantiene la tarea visible en Hoy/Mañana y en el próximo resumen

---

## 5. Preparación de reuniones bajo demanda

Comandos:
- “Prepárame para la próxima reunión”
- “¿Qué tengo a las 10?”
- “Contexto de la reunión con Ana”

Iris responde de forma concisa con:
- Título + hora (+ asistentes si están)
- Tareas abiertas relacionadas (si las hay)
- Tiempo libre justo antes
- Acciones rápidas opcionales

No inventa el contenido de la reunión.

---

## 6. Durante el día

El usuario puede:
- Seguir capturando pendientes
- Pedir cajones / resumen / deshacer
- Posponer cualquier recordatorio
- Pedir contexto de una reunión concreta
- Cambiar de modo (automático ↔ pregúntame siempre)

Las notificaciones respetan los bloques de reunión (salvo tareas Críticas).

---

## 7. Tres cajones y revisión semanal

Sin cambios de fondo:
- Hoy/Mañana | Esta semana | Puede esperar
- Tope de 3-4 importantes
- Rápidos (< 10 min)
- Revisión semanal de tareas estancadas (incluyendo las muy pospuestas)

---

## 8. Evolución de la confianza

Después de varias interacciones correctas, Iris puede ofrecer el modo automático.
El usuario puede volver a “pregúntame siempre” en cualquier momento.
