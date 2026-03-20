# Photography Portfolio | Visual Stories (v2 - Vue.js & Bootstrap)

Un portafolio de fotografía moderno y responsivo, refactorizado de una estructura estática a una aplicación modular basada en **Vue.js 3** y **Bootstrap 5.3**.

## Características Principales:
- **Refactorización a Vue.js 3**: Migración de lógica estática a componentes reactivos con Composition API.
- **Diseño Sleek & Minimalist**: Estética oscura con glassmorphism en navegación y contrastes controlados.
- **Masonry Layout**: Visualización dinámica de imágenes adaptativa según el tamaño de pantalla.
- **Optimización de Activos**: Servido con **Vite** para tiempos de carga ultrarrápidos y desarrollo eficiente.
- **Base SCSS**: Estilos modulares utilizando la arquitectura SMACSS para facilitar el mantenimiento.

## Tecnologías Utilizadas:
- [Vue.js 3](https://vuejs.org/)
- [Vite](https://vitejs.dev/)
- [Bootstrap 5.3](https://getbootstrap.com/)
- [Sass (SCSS)](https://sass-lang.com/)

## Estructura del Proyecto:
- `src/App.vue`: Componente principal y maquetación.
- `src/data/images.js`: Archivo de datos centralizado para la colección de fotos.
- `src/assets/scss/`: Estilos globales y variables de diseño.
- `public/assets/media/`: Galería de imágenes.
- `legacy/`: Respaldo de la versión estática original y del tema Minecraft.

## Instalación y Ejecución:
Para ejecutar el proyecto localmente:

```bash
# Instalación de dependencias
npm install

# Lanzamiento del servidor de desarrollo
npm run dev
```

## Aprendizaje del Sprint:
1. **Refactorización Modular**: De mover elementos manuales en el DOM con `script.js` a una estructura declarativa con `v-for` en Vue.
2. **Integración Bootstrap en Vue**: Configuración del bundle de JS y estilos de Bootstrap dentro del ecosistema de Vite.
3. **Optimización con public folder**: Manejo de rutas absolutas para activos estáticos en Vite.

---
© 2024 Visual Stories. Producido con enfoque en impacto visual.
