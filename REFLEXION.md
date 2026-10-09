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

---

## Laboratorio 4: Reflexión Aplicada

### 1. Fragmento CSS de la rotación del logo del CURZA

```css
header .logo {
    transition: transform 1s ease-in-out;
}

header .logo:hover {
    transform: rotateY(360deg);
}
```

`transition: transform 1s ease-in-out` hace que cualquier cambio en la propiedad `transform` se anime suavemente durante 1 segundo con una curva de aceleración `ease-in-out`. Al poner el cursor sobre la imagen, la pseudo-clase `:hover` aplica `transform: rotateY(360deg)`, que rota el logo una vuelta completa sobre el eje Y (en 3D); al retirar el cursor, la transición revierte la rotación de la misma forma.

### 2. ¿Por qué el `<h2>` sticky necesita `background-color`?

```css
section.biografia h2 {
    position: sticky;
    top: 0;
    background-color: var(--blanco);
    z-index: 10;
}
```

Un elemento con `position: sticky` "flota" sobre el contenido que va pasando debajo del área de desplazamiento (por eso también necesita `z-index`). Si no tuviera `background-color` (opaco), el texto y la imagen de la biografía que corren por debajo se verían **a través del título**, superponiéndose y haciendo ilegible la lectura. El color de fondo opaco tapa el contenido desplazado para que el encabezado se mantenga siempre legible.

### 3. Cambios visuales que aplica `@media (max-width: 768px)` en pantallas móviles

- El `header` pasa a `flex-direction: column`: el título y el logo se apilan uno debajo del otro (el logo se hace más chico, `height: 34px`).
- La navegación deja de estar en una fila horizontal y se **apila verticalmente** (`flex-direction: column`): cada enlace ocupa todo el ancho como un bloque, más fácil de tocar con el dedo.
- Se reduce el padding de `main` y de las secciones para aprovechar mejor el ancho de pantalla, se achica el tipo del `h1` y del botón "volver arriba", y la tabla del resumen usa una fuente menor.
- El `body` aumenta su `padding-top` (de 72px a 100px) porque el encabezado apilado ocupa más alto y no debe tapar el contenido inicial.