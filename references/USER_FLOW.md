# Flujo de uso de Iris

**Versión:** 1.4.1 (bad-timing por reglas)  
**Repo:** https://github.com/karloskadena84/iris-skill

---

## Flujo gráfico del día (mañana + minutos antes)

```text
                    ┌─────────────────────────────┐
                    │  INICIO DEL DÍA (mañana)    │
                    │  Franja de atención local   │
                    │  (ej. 8:00–9:30)            │
                    └──────────────┬──────────────┘
                                   │
                                   ▼
                    ┌─────────────────────────────┐
                    │  RESUMEN MATUTINO           │
                    │  • Reuniones del día        │
                    │  • 3–4 prioridades          │
                    │  • En riesgo                │
                    │  • Pospuestas               │
                    │  • Tiempo libre             │
                    └──────────────┬──────────────┘
                                   │
                                   ▼
                    ┌─────────────────────────────┐
                    │  ¿Usuario responde?         │
                    │  Hacer / Posponer / OK      │
                    └──────────────┬──────────────┘
                                   │
              ┌────────────────────┴────────────────────┐
              │                                         │
              ▼                                         ▼
     Pendientes CON hora                      Pendientes SIN hora
              │                                         │
              ▼                                         ▼
     Para CADA uno:                           Solo cajón Hoy
              │                               (sin “minutos antes”)
              ▼
     ┌────────────────────┐
     │ AVISO TEMPRANO     │
     │ Reunión: ~30 min   │
     │ Prep: 30–45 min    │
     │ Trabajo: ~15 min   │
     └─────────┬──────────┘
               │
               ▼
     ┌────────────────────┐
     │ ¿Mal momento?      │
     │ (bad-timing)       │
     └─────────┬──────────┘
          │         │
         Sí        No
          │         │
          ▼         ▼
     Reprogramar   Enviar
     en ventana    (Voy / Posponer)
          │
          └─────────┐
                    ▼
     ┌────────────────────┐
     │ AVISO CERCANO      │
     │ 10–15 min antes    │
     │ (NO se retrasa)    │
     └─────────┬──────────┘
               │
               ▼
     ┌────────────────────┐
     │ ¿Respondió?        │
     └─────────┬──────────┘
          │         │
         Sí        No
          │         │
          ▼         ▼
     Listo /      RECUPERACIÓN
     Pospuesto    «No supe de ti…»
                  Ahora / Mover / Más tarde
```

---

## Flujo: aviso inoportuno (detalle)

```text
[Hora planificada del aviso]
            │
            ▼
     ¿Mal momento?
     • Quiet hours 22:00–7:00
     • En reunión (Calendar)
     • Pospuso/ignoró hace ~20 min
     • Ráfaga de nudges
     • Fuera de franja de atención
            │
     ┌──────┴──────┐
     No           Sí
     │             │
     ▼             ▼
  Enviar     ¿Puede esperar?
               │         │
              Sí        No (cercano / crítica / chat activo)
               │         │
               ▼         ▼
          Reprogramar  Enviar igual
          en ventana
```

---

## 1. Onboarding

1. Verificar MCP Todoist + Google Calendar.
2. Primera captura con confirmación.
3. Mencionar: avisos con margen + resumen de mañana.

## 2. Captura

Dictado continuo, feedback inmediato, anticipación por tipo si hay hora fija.

## 3. Resumen matutino / diario

- Preferir franja de atención del usuario (send-time).
- Contenido: reuniones + prioridades + en riesgo + pospuestas + tiempo libre.
- Acciones: Hacer / Mover / Posponer / Prepárame.

## 4. Ciclo por pendiente con hora

1. **Aviso temprano** (según tipo; puede micro-ajustarse / bad-timing).
2. Usuario: Voy / Posponer / Lo vi.
3. **Aviso cercano** 10–15 min antes — **no se retrasa**.
4. Si no hay respuesta → **una recuperación**.
5. Sigue visible en Hoy/Mañana y en el próximo resumen.

## 5. Posponer

Respeta reuniones. Confirma horario. Mantiene en Hoy y en el resumen.

## 6. Preparación de reuniones

“Prepárame para la próxima reunión” / “¿Qué tengo a las 10?”.

## 7. Durante el día

Capturar · cajones · deshacer · posponer · voy / voy tarde · modo automático.

## 8. Cajones

Hoy/Mañana · Esta semana · Puede esperar.  
Tope 3–4 importantes. Rápidos agrupados.

---

## Nota de ejecución

Iris es skill + MCP: el resumen matutino y los avisos “minutos antes” se materializan cuando:

1. Hay bloques/alarmas en Google Calendar, y/o  
2. El cliente/automation dispara a Iris a esa hora, y/o  
3. El usuario abre el chat (resumen bajo demanda).

Las reglas del skill definen *qué* y *cuándo*; el canal (Calendar / scheduler) ejecuta el disparo.
