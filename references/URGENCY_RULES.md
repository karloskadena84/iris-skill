# Reglas de urgencia, avisos y recuperación — Iris

**Versión:** 1.3.0

## Objetivo

El usuario debe enterarse **a tiempo**. Preferible un aviso un poco antes a perder la actividad.

## Niveles de urgencia + avisos

| Nivel | Criterio | Avisos | Puede interrumpir si ocupado |
|-------|----------|--------|------------------------------|
| **Crítica** | < 24 h | 3 h antes + 1 h antes + 10–15 min antes + recuperación | Sí |
| **Alta** | 1–3 días | Día anterior + 1 h antes + 10–15 min antes | Preferir no; si es hora fija, sí el cercano |
| **Normal** | 4–14 días o con hora fija | 15–30 min antes + 10–15 min antes (o al inicio si es solo trabajo) | No (salvo hora fija muy próxima) |
| **Baja** | Sin hora dura o > 14 días | Solo bloque visible | No |

## Anticipación por tipo

| Tipo | Aviso temprano | Aviso cercano |
|------|----------------|---------------|
| Reunión / cita | 30 min | 10–15 min |
| Preparación / entrega / llamada | 30–45 min | 10–15 min |
| Bloque de trabajo | 15 min | Al inicio (opcional) |
| Rápidos (< 10 min) | — | Al inicio del bloque Rápidos |

Inferir por título (reunión, call, entrega, médico, salir…). Si hay hora fija y no está claro → tratar como preparación.

## Doble aviso

1. **Temprano** — con margen según tipo.
2. **Cercano** — 10–15 min antes (o al inicio).

Si el usuario responde al temprano (pospone, “voy”, “lo vi”), se puede cancelar o suavizar el cercano.

## Recuperación (si no se entera / no responde)

- Tras el aviso cercano, si no hay interacción en ~10–20 min o pasó la hora de inicio:
  - **Una** recuperación: «No supe de ti con [tarea]. ¿Ahora, movemos o más tarde?»
- Máximo una recuperación por tarea (Crítica: hasta dos).
- Mantener la tarea en Hoy/Mañana y en el resumen.

## Señal “en riesgo” (resumen diario)

Marcar tareas de las próximas horas sin avance ni confirmación:

> Ojo: “Enviar informe” es a las 11:00 y aún no la has tocado.

Acciones rápidas: Hacer / Posponer / Prepárame.

## Posponer

Opciones: 15 / 30 / 60 min · Esta tarde · Mañana misma hora · Hueco libre (sin choques con reuniones) · Después del bloque actual.

- Actualizar bloque en calendario.
- Seguir visible en Hoy/Mañana.
- Destacar en el próximo resumen.
- No bajar urgencia sola.

## Entrega si el usuario está ocupado

- **Crítica:** puede sonar.
- **Resto:** retraso corto del sonido permitido, pero no borrar el aviso cercano ni la recuperación.
- Respetar No molestar si es detectable (excepto Crítica).

## “Lo vi / más tarde”

No eliminar ni bajar prioridad. Visible en cajón y resumen. Puede disparar recuperación después.

## Asignación de urgencia

1. Fecha límite / hora  
2. Proximidad  
3. Impacto que indique el usuario  
4. Patrones (más adelante)

El usuario puede corregir el nivel siempre.
