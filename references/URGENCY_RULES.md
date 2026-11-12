# Reglas de urgencia, alarmas y posponer — Iris

## Niveles de urgencia

| Nivel     | Criterio                              | Alarmas en Google Calendar                     | Comportamiento |
|-----------|---------------------------------------|------------------------------------------------|----------------|
| **Crítica** | Vence en menos de 24 horas           | 3 horas antes + 1 hora antes + al iniciar     | Puede interrumpir aunque el usuario esté ocupado |
| **Alta**    | Vence en 1 a 3 días                  | Día anterior + 1 hora antes                   | Preferir momentos libres |
| **Normal**  | Vence en 4 a 14 días                 | Solo al iniciar el bloque                     | Una sola notificación suave |
| **Baja**    | Sin fecha dura o más de 14 días      | Solo aparece el bloque (sin sonar)            | Sin ruido |

## Entrega sensible al contexto

Antes de enviar una alarma con sonido:

1. Revisar el calendario del usuario.
2. Si está en reunión o bloque ocupado:
   - **Crítica** → puede interrumpir.
   - Resto de niveles → retrasar 15-30 min después del bloque, enviar notificación silenciosa, o dejar solo el bloque visible.
3. Respetar “No molestar” cuando sea detectable.

## Escalado suave

| Momento                              | Tipo de aviso                          | Invasión |
|--------------------------------------|----------------------------------------|----------|
| Varias horas antes                   | Solo bloque en calendario (sin sonido) | Muy baja |
| 1-2 horas antes (usuario libre)      | Notificación suave                     | Baja     |
| Cerca del deadline                   | Notificación más clara                 | Media    |
| Después de un posponer               | Nuevo bloque + recordatorio suave      | Baja     |

## Posponer (snooze inteligente)

Opciones estándar que Iris debe ofrecer o entender:

- En 15 / 30 / 60 minutos
- Esta tarde
- Mañana a la misma hora
- Cuando tenga un hueco libre (buscar próximo bloque disponible)
- Después de la reunión / bloque actual

Comportamiento al posponer:

- Actualizar o crear el bloque de tiempo en el calendario.
- Mantener la tarea visible en el cajón **Hoy / Mañana**.
- Confirmar de forma breve.
- Incluir la tarea de forma destacada en el próximo resumen diario.
- No bajar automáticamente la urgencia salvo que el usuario lo pida.

## “Lo vi, pero después”

Si el usuario solo dice “lo vi”, “más tarde” o similar:

- No eliminar ni archivar la tarea.
- No bajar la prioridad automáticamente.
- Mantenerla visible en el cajón de Hoy/Mañana.
- Destacarla en el siguiente resumen diario.
- Opcionalmente preguntar más tarde de forma suave si no ha avanzado.

## Reglas adicionales

- El usuario puede silenciar temporalmente un tipo de alarma (“Hoy no me avises de las normales”).
- Las tareas de menos de 10 minutos se agrupan en un único bloque llamado **«Rápidos»** con una sola alarma.
- Se aplica un margen de seguridad inicial del ~25 % sobre la duración estimada.
- Con el tiempo, Iris ajusta este margen comparando duración estimada vs duración real.
- Iris puede aprender las preferencias de aplazamiento del usuario (qué opción usa más) y proponerla por defecto.

## Asignación automática de urgencia

Iris asigna el nivel según:
1. Fecha límite declarada o inferida
2. Proximidad temporal
3. Impacto percibido (si el usuario lo indica)
4. Patrones aprendidos del usuario

El usuario siempre puede corregir el nivel de urgencia después de la creación.
