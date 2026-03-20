# 🗺️ Roadmap de Mejoras — Studio Guiones

Este archivo documenta las mejoras propuestas para el proyecto, ordenadas por impacto y dificultad.

---

## 🔴 Alta prioridad

### 1. Streaming de la respuesta (typewriter effect)
**Por qué:** El usuario ve la generación en tiempo real, percibe la app más rápida.  
**Cómo:** Usar `stream: true` en la API de Anthropic y `ReadableStream` en el fetch.

```js
// Ejemplo básico de streaming
const response = await fetch("https://api.anthropic.com/v1/messages", {
  ...
  body: JSON.stringify({ ..., stream: true }),
});
const reader = response.body.getReader();
// leer chunks e ir añadiendo al DOM
```

---

### 2. Guardar la API Key de forma segura en localStorage
**Por qué:** El usuario no tiene que pegar la key en cada sesión.  
**Cómo:** Opción "Recordar API Key" con checkbox, guardar cifrada o en `sessionStorage`.

---

### 3. Edición del guion generado
**Por qué:** El usuario quiere ajustar el texto antes de copiar/guardar.  
**Cómo:** Convertir `<div class="script-output">` en `<textarea>` editable al hacer clic en un botón "Editar".

---

### 4. Exportar a PDF
**Por qué:** Más útil que el .txt para presentar o imprimir.  
**Cómo:** Usar la librería [`jsPDF`](https://github.com/parallax/jsPDF) (CDN, sin backend).

---

## 🟡 Media prioridad

### 5. Historial de generaciones (no solo los guardados)
**Por qué:** El usuario puede revisar guiones que no guardó explícitamente.  
**Cómo:** Guardar los últimos 10 en `localStorage` automáticamente con `sessionHistory`.

---

### 6. Contador de palabras y tiempo estimado
**Por qué:** Ayuda a calibrar si el guion cabe en 60 segundos (~130 palabras ≈ 60 s).  
**Cómo:** `script.split(/\s+/).length` y cálculo en tiempo real al generar o editar.

---

### 7. Variaciones de gancho
**Por qué:** A veces el usuario quiere 3 opciones de apertura para A/B testing.  
**Cómo:** Botón "Generar 3 ganchos alternativos" que llama a la API con un prompt específico.

---

### 8. Selector de plataforma (TikTok / Reels / YouTube Shorts)
**Por qué:** Cada plataforma tiene sutilezas distintas (duración, hashtags, llamada a la acción).  
**Cómo:** Añadir `select#plataforma` y ajustar el `buildPrompt()` según la selección.

---

### 9. Drag & drop para reordenar guiones guardados
**Por qué:** Organización más natural.  
**Cómo:** API nativa `dragstart` / `dragover` / `drop` en los `.saved-item`.

---

### 10. Modo claro / oscuro
**Por qué:** Accesibilidad y preferencia personal.  
**Cómo:** CSS custom properties (`--bg`, `--text`, etc.) + toggle que añade clase `.light` al `<body>`.

---

## 🟢 Baja prioridad / Ideas futuras

### 11. Backend mínimo (Node.js/Cloudflare Worker)
**Por qué:** Evitar exponer la API Key en el cliente para producción.  
**Cómo:** Proxy en Cloudflare Workers o Vercel Edge Functions.

### 12. Integración con TikTok API
**Por qué:** Publicar directamente desde la app.  
**Cómo:** Requiere aprobación de TikTok Developer Account y OAuth.

### 13. Análisis de rendimiento
**Por qué:** Ver qué temas y tonos generan más engagement.  
**Cómo:** Campo "Resultados" al editar un guion guardado + gráfico simple con Chart.js.

### 14. Multi-idioma (inglés / español)
**Por qué:** Ampliar el alcance.  
**Cómo:** Archivo `i18n.js` con objeto de traducciones y función `t("key")`.

### 15. PWA (Progressive Web App)
**Por qué:** Instalar en el móvil como app nativa.  
**Cómo:** `manifest.json` + `service-worker.js` para cache offline.

---

## 🐛 Bugs conocidos

| # | Descripción | Severidad |
|---|---|---|
| 1 | `renderSaved()` genera HTML con `.join('<div class="saved-list">')` incorrecto — usar `.join("")` | Media |
| 2 | `showSection()` en nav-btn usa `event.target` en vez del parámetro `btn` — puede fallar si el clic es en el texto del botón | Baja |
| 3 | No hay validación de longitud mínima para el tema personalizado | Baja |

---

*Última actualización: marzo 2026*
