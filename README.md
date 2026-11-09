# Iris — Skill de Gestión de Pendientes

![Iris Logo](assets/logo.jfif)

**Iris** es un agente conversacional que te ayuda a capturar, organizar y recordar tus pendientes usando **Todoist** + **Google Calendar** a través de MCP.

Inspirado en la mensajera de los dioses de la mitología griega, Iris se encarga de llevar tus recordatorios en el momento preciso.

---

## ¿Qué hace Iris?

- Captura pendientes por voz o texto en segundos
- Los organiza en Todoist con fecha, urgencia y duración
- Reserva bloques de tiempo y configura alarmas inteligentes en Google Calendar
- Te entrega un resumen diario accionable
- Gestiona muchos pendientes con el sistema de “tres cajones”
- Aprende de tus hábitos con el tiempo
- Empieza confirmando y evoluciona a modo automático

---

## Requisitos

1. Un cliente compatible con **Skills** y **MCP** (Claude, Cursor, etc.)
2. Servidores MCP de **Todoist** y **Google Calendar** conectados
3. Cuentas de Todoist y Google (el usuario autoriza con OAuth, Iris nunca pide contraseñas)

---

## Cómo instalar este Skill

### Opción A — Subida por interfaz (recomendada)

1. Descarga el archivo `iris-skill.zip`
2. En la pantalla **Skill ZIP Upload**, arrastra el ZIP o selecciónalo
3. Confirma la carga

### Opción B — Instalación manual

1. Descomprime el ZIP
2. Copia la carpeta `iris/` dentro del directorio de skills de tu cliente  
   (normalmente algo como `.grok/skills/` o el directorio de skills del producto)
3. Reinicia o recarga los skills si es necesario

---

## Cómo usarlo

Una vez instalado, simplemente habla con el agente:

**Ejemplos de activación:**
- “Anota este pendiente...”
- “Qué tengo hoy”
- “Resumen del día”
- “Organizar mis tareas”
- “Muéstrame los cajones”
- “Deshaz la última acción”

### Primer uso (Onboarding)

1. Iris se presenta y verifica si tienes conectados los MCP de Todoist y Google Calendar
2. Si faltan, te guía paso a paso para autorizarlos (OAuth)
3. Te invita a dictar tu primer pendiente con confirmación

### Uso diario

- Dicta uno o varios pendientes seguidos
- Iris los procesa y te da feedback inmediato
- Cada mañana (o cuando lo pidas) recibes el resumen del día con acciones rápidas
- Puedes cambiar entre modo “pregúntame siempre” y modo automático

---

## Estructura del Skill

```
iris/
├── SKILL.md                  ← Instrucciones principales del agente
├── README.md                 ← Este archivo
├── assets/
│   └── logo.jfif             ← Logo oficial de Iris
└── references/
    ├── DESIGN.md             ← Diseño completo
    ├── USER_FLOW.md          ← Flujo de uso detallado
    ├── URGENCY_RULES.md      ← Reglas de urgencia y alarmas
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

## Soporte y mejoras

Este skill está en fase de prototipo. Las próximas mejoras recomendadas son:

- Conectar y probar los MCP reales de Todoist y Google Calendar
- Ajustar el umbral de paso a modo automático
- Mejorar la detección de duplicados
- Añadir aprendizaje de duración real vs estimada

---

## Limitaciones actuales

- Requiere que los MCP de Todoist y Google Calendar estén conectados para funcionar completamente.
- El aprendizaje de hábitos y ajuste de duraciones es progresivo (mejora con el uso).
- La detección de duplicados y la desambiguación de tareas muy vagas todavía son básicas.

---

*Iris no te recuerda lo que tienes que hacer.  
Te ayuda a que nunca se te olvide.*
