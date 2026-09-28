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

---

## Laboratorio 3: Reflexión Aplicada

### 1. Código HTML del campo Código Postal con `pattern` y `title`

```html
<input type="text" id="cp" name="cp" pattern="^[A-Z]\d{4}[A-Z]{3}$" title="Formato: una letra mayúscula, cuatro dígitos y tres letras mayúsculas (ej: R8500AAF)">
```

### 2. ¿Para qué sirve la etiqueta `<label>` y cómo se asocia a un campo con `for`?

La etiqueta `<label>` proporciona un texto descriptivo asociado a un campo del formulario. Al asociarla con `for` (cuyo valor debe coincidir con el `id` del campo), se logra:

- **Accesibilidad:** Los lectores de pantalla anuncian el rótulo cuando el usuario se posiciona en el campo.
- **Usabilidad:** Al hacer clic en el texto del rótulo, el foco se mueve automáticamente al campo correspondiente (y activa la casilla en radio/checkbox), ampliando la zona clicable.
- **Mejores mensajes de validación:** el navegador puede enunciar correctamente qué campo tiene el error.

Ejemplo de mi formulario:

```html
<label for="edad">Edad:</label>
<input type="number" id="edad" name="edad" min="16" max="120">
```

Aquí `for="edad"` apunta al `id="edad"` del `<input>`, quedando ambos fuertemente vinculados.

### 3. Comportamiento de los radio buttons con distintos `name` vs. el mismo `name`

- **Mismo `name`:** Los botones de radio forman parte de un mismo grupo; el navegador permite seleccionar **una sola opción a la vez**. Al elegir una, automáticamente se deselecciona la anterior. Solo así la selección excluyente funciona.
- **Distintos `name`:** Cada radio pertenece a un grupo independiente, por lo que se pueden seleccionar **varias opciones a la vez** (una por cada grupo). Esto rompe el comportamiento excluyente esperado y permite elegir más de una "opción única".

En mi formulario uso el mismo `name="metodo"` en los tres radios de "Método de Contacto Preferido" para garantizar que solo se pueda seleccionar una opción por defecto.