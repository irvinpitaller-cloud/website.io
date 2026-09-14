# website.io
repo website alfa y omega aluminio
ayoalum.io/
│
├── index.html                      # Página principal (solo HTML)
├── README.md                       # Documentación del repo
├── LICENSE                         # Licencia del proyecto
├── .gitignore                      # Archivos ignorados por Git
├── .nojekyll                       # Necesario para GitHub Pages
├── robots.txt                      # SEO - indexación
├── sitemap.xml                     # SEO - mapa del sitio
├── manifest.webmanifest            # PWA / metadata móvil
│
├── assets/
│   ├── css/
│   │   ├── styles.css              # Estilos principales
│   │   └── responsive.css          # Media queries (opcional)
│   │
│   ├── js/
│   │   ├── config.js               # ⚙️ CONFIGURACIÓN (editar aquí)
│   │   ├── main.js                 # Lógica principal
│   │   ├── catalogo.js             # Módulo del catálogo
│   │   ├── lightbox.js             # Módulo del lightbox
│   │   ├── menu.js                 # Menú móvil
│   │   ├── animaciones.js          # Scroll animations
│   │   └── seo.js                  # Schema.org JSON-LD
│   │
│   ├── img/
│   │   ├── logo/
│   │   │   ├── logo.svg
│   │   │   ├── logo-blanco.svg
│   │   │   └── favicon.ico
│   │   │
│   │   ├── hero/
│   │   │   └── hero-bg.jpg
│   │   │
│   │   ├── catalogo/
│   │   │   ├── corredizo-1.jpg
│   │   │   ├── abatible-1.jpg
│   │   │   ├── fijo-1.jpg
│   │   │   ├── plegable-1.jpg
│   │   │   ├── domo-1.jpg
│   │   │   ├── cristal-templado-1.jpg
│   │   │   ├── especiales-1.jpg
│   │   │   └── acoples-1.jpg
│   │   │
│   │   ├── proyectos/
│   │   │   ├── proyecto-1.jpg
│   │   │   ├── proyecto-2.jpg
│   │   │   ├── proyecto-3.jpg
│   │   │   ├── proyecto-4.jpg
│   │   │   ├── proyecto-5.jpg
│   │   │   └── proyecto-6.jpg
│   │   │
│   │   └── og/
│   │       └── og-image.jpg        # Imagen para redes sociales
│   │
│   └── fonts/                      # (opcional si usas fuentes locales)
│
├── docs/
│   ├── COMO-EDITAR.md              # Guía para editar contenido
│   ├── DEPLOY.md                   # Guía de despliegue
│   └── ESTRUCTURA.md               # Explicación de la estructura
│
└── .github/
    └── workflows/
        └── deploy.yml              # Auto-deploy a GitHub Pages (opcional)