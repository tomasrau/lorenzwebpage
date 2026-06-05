# Lorenz — Web Institucional Premium

Sitio web institucional de alta gama para **Lorenz** (Consultoría en Tecnología, Finanzas, Business Intelligence y Automatización). Construido con enfoque en diseño premium (estética fintech/SaaS, layouts limpios y microinteracciones fluidas), accesibilidad (A11y), responsive y optimización de rendimiento (SEO).

## 🛠️ Stack Tecnológico

- **Framework:** [Astro v5](https://astro.build/)
- **Estilos:** [Tailwind CSS v4](https://tailwindcss.com/)
- **Lenguaje:** [TypeScript](https://www.typescriptlang.org/)
- **Despliegue:** [GitHub Pages](https://pages.github.com/) (sitio estático completo)

---

## ⚙️ Configuración del Entorno Local

Este proyecto utiliza **Anaconda** para la gestión del entorno de ejecución de Node.js.

### 1. Activar el ambiente de Conda

Antes de instalar dependencias o ejecutar scripts de desarrollo, asegúrate de activar el entorno virtual provisto:

```bash
conda activate tommyrauwebpage
```

### 2. Instalar dependencias

Una vez activado el entorno, instala los paquetes necesarios mediante npm:

```bash
npm install
```

---

## 🚀 Comandos de Desarrollo

Todos los comandos deben ser ejecutados en la raíz del proyecto con el entorno Conda activo:

| Comando | Acción |
| :--- | :--- |
| `npm run dev` | Inicia el servidor de desarrollo local en `http://localhost:4321` |
| `npm run build` | Compila el sitio y genera los archivos estáticos listos para producción en `./dist/` |
| `npm run preview` | Permite previsualizar localmente la compilación de producción |
| `npm run astro -- --help` | Obtiene ayuda sobre el CLI de Astro |

---

## 📁 Estructura del Proyecto

```text
/
├── public/                 # Favicons y recursos públicos
├── src/
│   ├── components/         # Componentes modulares de la interfaz
│   │   ├── Navbar.astro      # Menú sticky con scroll-driven height shrink & glassmorphism
│   │   ├── Hero.astro        # Mensajes principales y CTAs
│   │   ├── Problem.astro     # Sección consultiva sobre problemáticas de mercado
│   │   ├── ValueProp.astro   # Propuesta de valor y diferenciales clave
│   │   ├── Services.astro    # Tarjetas detalladas de servicios e integraciones
│   │   ├── UseCases.astro    # Pestañas interactivas de casos por tipo de cliente
│   │   ├── Methodology.astro # Cronograma vertical del proceso de consultoría (1 al 5)
│   │   ├── Dashboard.astro   # Mockup interactivo HTML/CSS/JS de Business Intelligence
│   │   ├── Trust.astro       # Pilares de confianza (seguridad, consistencia) e integraciones
│   │   ├── Insights.astro    # Centro de investigación y artículos técnicos (Research)
│   │   ├── Contact.astro     # Formulario de contacto y CTAs finales
│   │   └── Footer.astro      # Pie de página institucional y enlaces rápidos
│   ├── layouts/
│   │   └── Layout.astro      # Estructura HTML5 base con SEO (OG, canonical, descriptivo)
│   ├── styles/
│   │   └── global.css        # Directivas Tailwind v4, fuentes y estilos de base
│   └── pages/
│       └── index.astro       # Página principal que ensambla las secciones
├── astro.config.mjs        # Configuración de Astro (incluye site/base para GH Pages)
├── package.json            # Dependencias y scripts de Node.js
└── tsconfig.json           # Configuración del compilador TypeScript
```

---

## 🌐 Publicación en GitHub Pages

El sitio está preconfigurado para ser desplegado en GitHub Pages.

### Configuración en `astro.config.mjs`

El archivo de configuración tiene definidos los parámetros `site` y `base` necesarios para resolver correctamente las rutas relativas en el subdirectorio del repositorio:

```javascript
export default defineConfig({
  site: 'https://tomasrau.github.io',
  base: '/lorenzwebpage',
  // ...
});
```

### Instrucciones de Deploy

1. Sube los archivos del proyecto a tu repositorio de GitHub:
   ```bash
   git add .
   git commit -m "feat: implement initial premium institutional landing page"
   git push origin main
   ```
2. Configura una **GitHub Action** para compilar y desplegar automáticamente en cada push, o realiza un deploy manual compilando (`npm run build`) y subiendo la carpeta `./dist/` a la rama `gh-pages` utilizando paquetes como `gh-pages`:
   
   - **Opción recomendada (GitHub Actions):** Crea un archivo `.github/workflows/deploy.yml` con la plantilla estándar de Astro para GitHub Pages. GitHub se encargará de compilar el sitio y publicarlo automáticamente.
   - **Opción manual:**
     ```bash
     npm install -D gh-pages
     npx gh-pages -d dist
     ```
