# 🎬 Studio Guiones

> Generador de guiones educativos para TikTok y Reels, impulsado por la API de Anthropic Claude.

![Studio Guiones](https://img.shields.io/badge/Claude-Sonnet-7c3aed?style=flat-square)
![HTML](https://img.shields.io/badge/HTML-5-orange?style=flat-square)
![CSS](https://img.shields.io/badge/CSS-3-blue?style=flat-square)
![JS](https://img.shields.io/badge/JavaScript-ES2020-yellow?style=flat-square)
![License](https://img.shields.io/badge/license-MIT-green?style=flat-square)

---

## ✨ Características

| Módulo | Descripción |
|---|---|
| ✍️ **Generador** | Crea guiones de 60 seg con IA eligiendo tema, tono y audiencia |
| 📲 **Flujo NotebookLM** | Guía paso a paso para publicar en TikTok/Reels |
| 💰 **Monetización** | Estrategia por fases: 0→1K, 1K→10K, 10K+ |
| 📅 **Calendario** | Calendario mensual de publicación sugerido |
| 📁 **Guardados** | Guarda y descarga guiones en localStorage |

---

## 🚀 Cómo usarlo

### Opción A — Abrir directo en el navegador

```bash
git clone https://github.com/TU_USUARIO/studio-guiones.git
cd studio-guiones
# Abre index.html en tu navegador
open index.html       # macOS
start index.html      # Windows
xdg-open index.html   # Linux
```

Ingresa tu API Key de Anthropic en el campo correspondiente dentro de la app.

### Opción B — Servidor local (recomendado)

```bash
# Con Python
python -m http.server 3000

# Con Node.js / npx
npx serve .

# Con VS Code
# Instala la extensión "Live Server" y haz clic en "Go Live"
```

Luego abre `http://localhost:3000` en tu navegador.

### Opción C — Desplegar en GitHub Pages

1. Sube el repositorio a GitHub
2. Ve a **Settings → Pages**
3. Selecciona rama `main` y carpeta `/` (root)
4. Tu app estará disponible en `https://TU_USUARIO.github.io/studio-guiones/`

---

## 🔑 API Key

Obtén tu API Key gratuita (o de pago) en [console.anthropic.com](https://console.anthropic.com).

> ⚠️ **Nunca** subas tu API Key al repositorio. Usa el campo en la interfaz de la app o variables de entorno si lo conviertes a backend.

---

## 📁 Estructura del proyecto

```
studio-guiones/
├── index.html          # HTML principal (estructura + navegación)
├── css/
│   └── styles.css      # Todos los estilos
├── js/
│   ├── data.js         # Datos estáticos: temas, pasos, fases
│   └── app.js          # Lógica principal + llamadas a la API
├── docs/
│   └── MEJORAS.md      # Roadmap de mejoras propuestas
├── .gitignore
└── README.md
```

---

## 🛠️ Stack

- **Frontend:** HTML5 + CSS3 puro + JavaScript ES2020 (sin frameworks)
- **IA:** [Anthropic Claude](https://anthropic.com) — modelo `claude-sonnet-4-20250514`
- **Almacenamiento:** `localStorage` del navegador
- **Sin dependencias externas** — funciona offline excepto las llamadas a la API

---

## 🤝 Contribuir

1. Haz fork del repositorio
2. Crea una rama: `git checkout -b feature/mi-mejora`
3. Haz commit: `git commit -m "feat: descripción de la mejora"`
4. Push: `git push origin feature/mi-mejora`
5. Abre un Pull Request

Consulta [`docs/MEJORAS.md`](docs/MEJORAS.md) para ver el roadmap de funcionalidades.

---

## 📄 Licencia

MIT © 2026 — úsalo, modifícalo y compártelo libremente.
