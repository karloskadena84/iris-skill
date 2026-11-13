# Iris — Skill de Gestión de Pendientes

![Iris Logo](assets/logo.jfif)

**Versión actual:** 1.1.0  
**Repositorio:** https://github.com/karloskadena84/iris-skill

**Iris** es un agente conversacional que te ayuda a capturar, organizar y recordar tus pendientes usando **Todoist** + **Google Calendar** a través de MCP.

Inspirado en la mensajera de los dioses de la mitología griega, Iris se encarga de llevar tus recordatorios en el momento preciso, sin ser invasiva.

---

## ¿Qué hace Iris?

- Captura pendientes por voz o texto en segundos
- Los organiza en Todoist con fecha, urgencia y duración
- Reserva bloques de tiempo y configura alarmas inteligentes en Google Calendar
- Te permite **posponer** recordatorios de forma fácil y contextual
- Entrega un resumen diario accionable
- Gestiona muchos pendientes con el sistema de “tres cajones”
- Empieza confirmando y evoluciona a modo automático

---

## Requisitos

1. Un cliente compatible con **Skills** y **MCP** (Claude, Cursor, u otros)
2. Servidores MCP de **Todoist** y **Google Calendar** conectados
3. Cuentas de Todoist y Google (autorizas con OAuth; Iris nunca pide contraseñas)

---

## Instalación

### Opción A — Subida por interfaz (recomendada)

1. Descarga el ZIP de la última release:  
   https://github.com/karloskadena84/iris-skill/releases
2. En tu cliente, ve a la pantalla **Skill ZIP Upload**
3. Arrastra el archivo `iris-skill-vX.X.X.zip` o selecciónalo
4. Confirma la carga

### Opción B — Instalación manual

1. Descarga y descomprime el ZIP
2. Copia la carpeta `iris/` dentro del directorio de skills de tu cliente  
   (normalmente `.grok/skills/` o el directorio equivalente)
3. Reinicia o recarga los skills si es necesario

---

## Cómo usar Iris

Una vez instalado, simplemente habla con el agente.

### Comandos principales

| Quieres…                    | Di algo como…                                      |
|----------------------------|----------------------------------------------------|
| Capturar pendientes        | “Anota este pendiente…”, “Recuérdame…”             |
| Ver el día                 | “¿Qué tengo hoy?”, “Resumen del día”               |
| Ver la semana              | “Muéstrame los cajones”, “¿Cómo está mi semana?”   |
| Posponer un recordatorio   | “Posponer”, “En 30 minutos”, “Cuando tenga hueco”  |
| Deshacer                   | “Deshaz la última acción”                          |
| Cambiar modo               | “Pasa a modo automático” / “Pregúntame siempre”    |

### Primer uso (Onboarding)

1. Iris se presenta y verifica si tienes conectados los MCP de Todoist y Google Calendar.
2. Si faltan, te guía paso a paso para autorizarlos (OAuth).
3. Te invita a dictar tu primer pendiente con confirmación.

### Uso diario

- Dicta uno o varios pendientes seguidos.
- Iris los procesa y te da feedback inmediato.
- Cada mañana (o cuando lo pidas) recibes el resumen del día con acciones rápidas.
- Si una notificación llega en mal momento, puedes posponerla fácilmente.
- Las tareas pospuestas siguen visibles y aparecen en el próximo resumen.

### Posponer (v1.1.0)

Cuando digas “posponer”, “más tarde”, “en una hora” o “cuando tenga hueco”, Iris te ayuda a reprogramar sin perder el pendiente:

- En 15 / 30 / 60 minutos
- Esta tarde
- Mañana a la misma hora
- Cuando tenga un hueco libre (busca espacio en tu calendario)
- Después de la reunión actual

---

## Cómo actualizar Iris

### Actualización recomendada (por release)

1. Ve a la página de releases:  
   https://github.com/karloskadena84/iris-skill/releases
2. Descarga el ZIP de la **última versión** (ej. `iris-skill-v1.1.0.zip`)
3. En tu cliente:
   - Si usas **Skill ZIP Upload**: sube el nuevo ZIP (normalmente reemplaza al anterior)
   - Si instalaste manualmente: borra o reemplaza la carpeta `iris/` anterior y copia la nueva
4. Recarga los skills si el cliente lo requiere

### Comprobar qué versión tienes

- Revisa el archivo `README.md` o `SKILL.md` dentro de la carpeta del skill.
- O mira la versión indicada en la release de GitHub que descargaste.

### Notas de actualización

- **v1.1.0** añade: posponer inteligente, entrega sensible al contexto del calendario y escalado suave de notificaciones.
- No necesitas borrar tus tareas de Todoist ni tu calendario. Solo se actualizan las instrucciones del agente.
- Si algo no se comporta como esperas después de actualizar, prueba a recargar el skill o reiniciar el cliente.

---

## Estructura del Skill

```
iris/
├── SKILL.md                  ← Instrucciones principales del agente
├── README.md                 ← Este archivo (uso y actualización)
├── TEST_REPORT_v1.1.0.md     ← Informe de pruebas de la versión
├── assets/
│   └── logo.jfif             ← Logo oficial
└── references/
    ├── DESIGN.md             ← Diseño completo
    ├── USER_FLOW.md          ← Flujo de uso detallado
    ├── URGENCY_RULES.md      ← Reglas de urgencia, alarmas y posponer
    └── EXAMPLES.md           ← Ejemplos de conversación
```

---

## Seguridad

- Iris **nunca** pide ni almacena contraseñas
- Solo utiliza OAuth a través del cliente
- No inventa acciones: solo confirma lo que las herramientas MCP reportan
- Pide confirmación extra para acciones destructivas masivas
- Incluye protecciones básicas contra prompt injection

---

## Limitaciones actuales

- Requiere que los MCP de Todoist y Google Calendar estén conectados para funcionar completamente.
- La detección de “usuario ocupado” depende de que el calendario exponga correctamente los eventos.
- El aprendizaje de hábitos y preferencias de posponer es progresivo.

---

*Iris no te recuerda lo que tienes que hacer.  
Te ayuda a que nunca se te olvide.*
