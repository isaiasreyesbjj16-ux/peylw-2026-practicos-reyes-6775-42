# REFLEXION.md

## Laboratorio 2: Reflexión Aplicada

### 1. Nombre de la imagen y valor del atributo `alt`

La imagen que guardé en mi carpeta `img/` se llama **`img.png`** y se carga desde `acercade.html` con la siguiente etiqueta:

```html
<img src="img/img.png" alt="Foto de perfil de Isaías Reyes Arzamendia">
```

El valor del atributo `alt` que asigné es: **"Foto de perfil de Isaías Reyes Arzamendia"**.

### 2. ¿Por qué es fundamental usar etiquetas semánticas como `<main>` o `<nav>` en lugar de `<div>`?

Porque las etiquetas semánticas le dan **significado** al contenido y no solo presentación:

- **Accesibilidad:** Los lectores de pantalla y las tecnologías de asistencia identifican claramente qué es la navegación, el contenido principal o el pie de página, permitiendo saltos directos entre zonas (por ejemplo, saltar la navegación).
- **SEO:** Los buscadores comprenden mejor la jerarquía y la relevancia del contenido, priorizando lo que está dentro de `<main>` y mejorando el posicionamiento.
- **Mantenimiento y legibilidad del código:** Un documento estructurado con `<header>`, `<nav>`, `<main>`, `<article>`, `<section>` y `<footer>` es más fácil de leer, mantener y modificar que una "sopa" de `<div>` anidados.

Un `<div>` es totalmente genérico y no comunica nada sobre el contenido que envuelve. Usarlo para todo implicaría perder accesibilidad, SEO y claridad estructural.

### 3. ¿Cómo verifiqué las rutas de los enlaces de navegación?

- **En el entorno local:** Abrí `index.html` directamente en el navegador y comprobé que los estilos de `styles.css` se aplicaban (fondo `#f4f4f9` y fuente sans-serif). Luego hice clic en el enlace "Acerca de" para verificar que abría `acercade.html`, y desde allí volví con el enlace "Inicio". Como los enlaces son **rutas relativas** (`index.html` y `acercade.html`), funcionan siempre que ambos archivos estén en la misma carpeta raíz.
- **Tras desplegar en GitHub Pages:** Publiqué los cambios en la rama `main` con un commit y habilité GitHub Pages sobre la rama principal. Una vez desplegado el sitio en la URL pública, repetí el mismo recorrido entre "Inicio" y "Acerca de" en el navegador y verifiqué que ambas páginas y la imagen `img/mi_foto.png` se cargaban correctamente. Las rutas relativas se resuelven igual en GitHub Pages porque la estructura de carpetas del repositorio se mantiene intacta.