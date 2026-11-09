# Reglas de urgencia y alarmas — Iris

## Niveles de urgencia

| Nivel     | Criterio                              | Alarmas en Google Calendar                     | Comportamiento |
|-----------|---------------------------------------|------------------------------------------------|----------------|
| **Crítica** | Vence en menos de 24 horas           | 3 horas antes + 1 hora antes + al iniciar     | Máxima atención |
| **Alta**    | Vence en 1 a 3 días                  | Día anterior + 1 hora antes                   | Recordatorio fuerte |
| **Normal**  | Vence en 4 a 14 días                 | Solo al iniciar el bloque                     | Una sola notificación |
| **Baja**    | Sin fecha dura o más de 14 días      | Solo aparece el bloque (sin sonar)            | Sin ruido |

## Reglas adicionales

- El usuario puede silenciar temporalmente un tipo de alarma (“Hoy no me avises de las normales”).
- Las tareas de menos de 10 minutos se agrupan en un único bloque llamado **«Rápidos»** con una sola alarma.
- Se aplica un margen de seguridad inicial del ~25 % sobre la duración estimada.
- Con el tiempo, Iris ajusta este margen comparando duración estimada vs duración real.

## Asignación automática de urgencia

Iris asigna el nivel según:
1. Fecha límite declarada o inferida
2. Proximidad temporal
3. Impacto percibido (si el usuario lo indica)
4. Patrones aprendidos del usuario

El usuario siempre puede corregir el nivel de urgencia después de la creación.
