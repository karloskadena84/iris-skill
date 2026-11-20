# Iris — Skill de Gestión de Pendientes

![Iris Logo](assets/logo.jfif)

**Versión actual:** 1.4.1 (bad-timing por reglas)  
**Repositorio:** https://github.com/karloskadena84/iris-skill

**Iris** es un agente conversacional que te ayuda a capturar, organizar y recordar tus pendientes usando **Todoist** + **Google Calendar** a través de MCP.

Inspirado en la mensajera de los dioses de la mitología griega, Iris se encarga de llevar tus recordatorios en el momento preciso, sin ser invasiva — y evitando avisos en mal momento.

---

## ¿Qué hace Iris?

- Captura pendientes por voz o texto en segundos
- Los organiza en Todoist con fecha, urgencia y duración
- Reserva bloques y alarmas inteligentes en Google Calendar
- **Posponer** fácil y contextual
- Resumen diario con reuniones y tareas **en riesgo**
- Doble aviso (temprano + cercano) y recuperación si no hay respuesta
- **Send-time optimization** y **bad-timing por reglas** (quiet hours, reunión, ráfaga)
- Tres cajones y modo automático progresivo

---

## Requisitos

1. Cliente compatible con Skills y MCP
2. MCP de Todoist y Google Calendar conectados
3. Cuentas autorizadas con OAuth (Iris nunca pide contraseñas)

---

## Instalación

### Opción A — Skill ZIP Upload
1. Descarga el ZIP de la última release: https://github.com/karloskadena84/iris-skill/releases
2. Súbelo en **Skill ZIP Upload**

### Opción B — Manual
1. Descomprime el ZIP
2. Copia la carpeta `iris/` al directorio de skills (p. ej. `.grok/skills/`)
3. Recarga los skills si hace falta

---

## Cómo usar

| Quieres… | Di algo como… |
|----------|----------------|
| Capturar | “Anota este pendiente…”, “Recuérdame…” |
| Ver el día | “¿Qué tengo hoy?”, “Resumen del día” |
| Cajones | “Muéstrame los cajones” |
| Posponer | “Posponer”, “En 30 minutos”, “Cuando tenga hueco” |
| Preparar reunión | “Prepárame para la próxima reunión” |
| Ante un aviso | “Voy”, “Voy tarde”, “Ya la hice” |

---

## Cómo actualizar

1. Releases: https://github.com/karloskadena84/iris-skill/releases
2. Descarga el ZIP de la última versión
3. Súbelo de nuevo o reemplaza la carpeta `iris/`
4. Recarga skills

### Notas de actualización

- **v1.4.1** — Bad-timing por reglas: evita avisos no críticos en mal momento (quiet hours, reunión, ráfaga) sin modelo externo.
- **v1.4.0** — Send-time optimization: aprende cuándo atiendes mejor; no retrasa citas ni avisos cercanos.
- **v1.3.0** — Avisos a tiempo: anticipación por tipo, doble aviso, recuperación, en riesgo.
- **v1.2.0** — Contexto de reuniones en resumen, posponer inteligente, “prepárame”.

No se borran tareas de Todoist ni el calendario al actualizar el skill.

---

## Estructura

```
iris/
├── SKILL.md
├── README.md
├── VERSION
├── CHANGELOG_v1.4.1.md
├── assets/logo.jfif
└── references/
    ├── DESIGN.md
    ├── USER_FLOW.md      ← incluye flujo de aviso inoportuno
    ├── URGENCY_RULES.md
    └── EXAMPLES.md
```

---

## Seguridad

- Nunca pide ni almacena contraseñas
- Solo OAuth vía el cliente
- No inventa acciones no confirmadas por MCP
- Confirmación extra en borrados masivos

---

*Iris no te recuerda lo que tienes que hacer.  
Te ayuda a que nunca se te olvide.*
