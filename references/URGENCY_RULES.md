# Reglas de urgencia, avisos y recuperación — Iris

**Versión:** 1.4.1

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

## Doble aviso

1. **Temprano** — con margen según tipo.
2. **Cercano** — 10–15 min antes (o al inicio).

Si el usuario responde al temprano, se puede suavizar el cercano.

## Recuperación

Una recuperación si no hay respuesta tras el cercano (~10–20 min) o pasó la hora. Crítica: hasta dos. Mantener en Hoy/Mañana y resumen.

## Señal “en riesgo”

En el resumen: tareas próximas sin avance. Acciones: Hacer / Posponer / Prepárame.

## Posponer

15/30/60 min · Esta tarde · Mañana · Hueco libre (sin choques) · Después del bloque actual.

## Send-time optimization

Optimizar entrega según franjas de atención del usuario **sin** retrasar citas ni aviso cercano. Quiet hours 22:00–7:00. Sin historial: anticipación fija por tipo.

## Bad-timing por reglas (sin modelo externo)

### Señales de mal momento
1. Quiet hours (22:00–7:00 local), salvo Crítica o cita ≤30 min.
2. Usuario en reunión/bloque ocupado (Calendar), salvo Crítica.
3. Acaba de posponer/ignorar la misma tarea (~20 min).
4. Ráfaga: nudge no crítico muy reciente.
5. Fuera de franja de atención conocida y el aviso puede esperar.

### Política
- **Siempre enviar:** Crítica, aviso cercano (10–15 min), usuario en chat activo, pedido explícito.
- **Puede retrasar:** resumen, temprano flexible, recuperación si aún hay margen antes de la actividad.
- **Micro-ajuste solo:** aviso temprano de cita dentro de la ventana de anticipación.
- No usar señales inventadas (batería, pantalla) si el canal no las aporta.
