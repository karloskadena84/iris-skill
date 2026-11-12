# Iris v1.1.0 — Informe de pruebas

**Fecha:** 2026-11-12  
**Versión:** 1.1.0  
**Cambio principal:** Notificaciones inteligentes, posponer contextual y escalado suave

---

## 1. Validación estructural

| Prueba | Resultado |
|--------|-----------|
| `validate-skill.sh` | ✅ OK |
| Frontmatter (name + description) | ✅ Válido |
| Description sin caracteres prohibidos | ✅ |
| Archivos de referencia presentes | ✅ |
| Logo en assets/ | ✅ |

---

## 2. Pruebas de consistencia de la nueva lógica

| Escenario | SKILL.md | URGENCY_RULES | USER_FLOW | EXAMPLES | Estado |
|-----------|----------|---------------|-----------|----------|--------|
| Posponer con opciones claras | ✅ | ✅ | ✅ | ✅ | OK |
| “Cuando tenga un hueco libre” | ✅ | ✅ | ✅ | ✅ | OK |
| Entrega sensible al contexto (no interrumpir si ocupado) | ✅ | ✅ | ✅ | — | OK |
| Solo Crítica puede interrumpir | ✅ | ✅ | ✅ | — | OK |
| Escalado suave (bloque → suave → más claro) | ✅ | ✅ | — | — | OK |
| “Lo vi / más tarde” mantiene la tarea visible | ✅ | ✅ | ✅ | — | OK |
| Tareas pospuestas aparecen en resumen diario | ✅ | ✅ | ✅ | ✅ | OK |
| Comandos de posponer listados | ✅ | — | ✅ | ✅ | OK |

---

## 3. Casos de prueba manuales (lógicos)

### Caso A — Notificación en mal momento
1. Usuario está en reunión.
2. Llega recordatorio de tarea Normal/Alta.
3. **Esperado:** no interrumpe con sonido (o se retrasa).  
4. **Resultado de diseño:** ✅ Cubierto.

### Caso B — Posponer explícito
1. Usuario: “Posponer el informe”
2. Iris ofrece opciones.
3. Usuario elige “Cuando tenga un hueco libre”.
4. **Esperado:** busca hueco, crea bloque, confirma, mantiene visible.  
5. **Resultado de diseño:** ✅ Cubierto + ejemplo.

### Caso C — Posponer rápido
1. Usuario: “En 30 minutos”
2. **Esperado:** reprograma y confirma en una línea.  
3. **Resultado de diseño:** ✅ Cubierto + ejemplo.

### Caso D — “Lo vi”
1. Usuario: “Lo vi” / “Más tarde”
2. **Esperado:** no se borra, sigue en cajón Hoy y en el próximo resumen.  
3. **Resultado de diseño:** ✅ Cubierto.

### Caso E — Tarea Crítica
1. Tarea vence en < 24 h y usuario está ocupado.
2. **Esperado:** sí puede interrumpir.  
3. **Resultado de diseño:** ✅ Explicitado.

---

## 4. Pruebas de regresión (funcionalidad previa)

| Funcionalidad | Estado |
|---------------|--------|
| Captura continua + feedback | ✅ Sin cambios negativos |
| Resumen diario accionable | ✅ Mejorado (incluye pospuestas) |
| Tres cajones | ✅ Intactos |
| Confirmación progresiva | ✅ Intacta |
| Seguridad (no inventar acciones, OAuth, etc.) | ✅ Intacta |
| Onboarding | ✅ Intacto |

---

## 5. Limitaciones actuales (sin cambios)

- Requiere MCP de Todoist y Google Calendar conectados para funcionar de verdad.
- La detección real de “usuario ocupado” depende de que el MCP de Calendar exponga los eventos correctamente.
- El aprendizaje de preferencias de posponer es progresivo (aún no hay persistencia de preferencias fuera del contexto de conversación).

---

## 6. Conclusión

**v1.1.0** está lista.

- Estructura del skill válida.
- Nueva lógica de notificaciones y posponer consistente en todos los documentos clave.
- Casos de uso del problema original (“me llega la notificación cuando estoy ocupado y luego se me olvida”) cubiertos por diseño.

**Recomendación:** publicar release `v1.1.0` en GitHub con el ZIP adjunto.
