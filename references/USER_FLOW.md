# Flujo de uso de Iris

## 1. Primer uso (Onboarding – 60-90 segundos)

1. El usuario abre el cliente MCP y escribe o dice:  
   «Hola, quiero organizar mis pendientes».

2. Iris se presenta:  
   «Dime lo que tienes que hacer. Yo lo organizo en Todoist y te aviso en el momento justo en el calendario.»

3. Verifica las conexiones MCP de Todoist y Google Calendar.
   - Si faltan → guía la autorización OAuth paso a paso.
   - Si ya están → pasa a la primera captura.

4. (Opcional) Pregunta plataforma solo para adaptar ejemplos:  
   «¿Usas iPhone o Android?»

5. Invita a la primera captura con confirmación explícita.

---

## 2. Captura de pendientes (uso principal)

**Modo automático (después de ganar confianza):**

1. El usuario dicta uno o varios pendientes seguidos.
2. Iris procesa el lote completo (modo dictado continuo).
3. Responde de inmediato con feedback claro (voz + detalle estructurado).
4. Solo pregunta si falta información crítica.

**Modo confirmación (primeros usos o por preferencia del usuario):**  
Muestra lo que va a hacer y espera “Sí” o correcciones antes de guardar.

---

## 3. Resumen diario (mañana o bajo demanda)

1. Iris entrega:
   - Resumen corto (20-30 segundos)
   - Lista de las 3-4 prioridades del día
   - Indicador de carga del día
   - Tareas que se pospusieron destacadas
2. Cada ítem tiene acciones rápidas:
   - Hacer ahora
   - Mover a otro hueco
   - Posponer
   - Agrupar en Rápidos
   - Bajar urgencia
   - Eliminar / Archivar
3. Si el día está pesado, propone proactivamente qué reorganizar.

Comandos útiles:
- «Resumen del día»
- «¿Qué tengo hoy?»

---

## 4. Durante el día y notificaciones

El usuario puede:
- Seguir capturando pendientes en cualquier momento
- Pedir «Muéstrame los cajones»
- Pedir «Deshaz la última acción»
- Consultar historial reciente
- Cambiar de modo (automático ↔ pregúntame siempre)
- **Posponer** cualquier recordatorio

### Flujo de posponer

1. Llega la notificación (o el usuario la menciona en el chat).
2. El usuario responde, por ejemplo:
   - «Posponer»
   - «En una hora»
   - «Cuando tenga hueco»
   - «Más tarde»
3. Iris:
   - Ofrece opciones claras si hace falta
   - Actualiza el bloque de tiempo
   - Confirma de forma breve
   - Mantiene la tarea visible en Hoy/Mañana y en el próximo resumen

### Entrega sensible al contexto

- Si el usuario está en un bloque ocupado del calendario:
  - Tareas no críticas → se retrasan o se envían en modo silencioso.
  - Solo las Críticas pueden interrumpir.

---

## 5. Gestión de muchos pendientes

Iris organiza todo en tres cajones:

| Cajón            | Contenido                     | Alarmas     |
|------------------|-------------------------------|-------------|
| Hoy / Mañana     | Urgente                       | Según reglas + posponer |
| Esta semana      | Importante pero no urgente    | Moderadas   |
| Puede esperar    | Sin presión de tiempo         | Ninguna     |

- Tareas < 10 min → se agrupan en bloque «Rápidos»
- Si hay más de 3-4 importantes en un día → avisa y ofrece reorganizar

---

## 6. Revisión semanal (domingo)

1. Resumen de la semana.
2. Detección de tareas estancadas (incluyendo las muy pospuestas).
3. Propuesta clara: Hacer / Reprogramar / Archivar.
4. El usuario confirma o ajusta (máximo 15 minutos).

---

## 7. Evolución de la confianza

Después de varias interacciones correctas, Iris pregunta:

«¿Quieres que pase a modo automático? Siempre podrás pedirme que te pregunte otra vez.»

El usuario puede cambiar de modo cuando quiera.
