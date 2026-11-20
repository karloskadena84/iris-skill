# Reglas de urgencia, avisos y recuperación — Iris

**Versión:** 1.4.0

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

## Send-time optimization

### Principio
Optimizar el momento de entrega según cuándo el usuario suele atender, **sin** retrasar avisos que pongan en riesgo una hora fija.

### Aplicar send-time a
- Resumen diario proactivo
- Avisos tempranos de tareas flexibles (sin cita rígida)
- Recuperaciones y “en riesgo”, si aún hay margen antes de la actividad
- Nudges del cajón Hoy no críticos

### No retrasar (hora del evento manda)
- Reuniones / citas
- Aviso cercano (10–15 min antes)
- Crítica cuando el plazo está encima

### Micro-ajuste permitido
En el aviso **temprano** de una actividad con hora, se puede elegir el minuto dentro de una ventana (ej. entre 25 y 40 min antes) si hay franja de alta atención del usuario. El aviso **cercano** no se aleja del evento.

### Quiet hours
Por defecto 22:00–7:00 hora local. Solo Crítica o citas inminentes atraviesan quiet hours.

### Sin historial
Usar anticipación fija por tipo (tablas de arriba) hasta tener señales de respuesta del usuario.

## Asignación de urgencia

1. Fecha límite / hora  
2. Proximidad  
3. Impacto que indique el usuario  
4. Patrones (más adelante)

El usuario puede corregir el nivel siempre.
