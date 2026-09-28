# Laboratorio 3: Captura de Datos y Validación Semántica con Formularios HTML5

## Información del Alumno

- **Nombre y Apellido:** Isaías Reyes Arzamendia
- **Legajo/Matrícula:** 8542
- **Últimos 4 dígitos del DNI:** 6775
- **Fecha de Entrega:** 2026-09-07
- **Enlace al Repositorio de GitHub:** https://github.com/isaiasreyesbjj16-ux/peylw-2026-practicos-reyes-6775-42
- **Enlace a la Página en GitHub Pages:** https://isaiasreyesbjj16-ux.github.io/peylw-2026-practicos-reyes-6775-42/

## Objetivos

- Conocer y estructurar los elementos esenciales de entrada de datos en HTML5.
- Aplicar atributos de validación nativos del navegador sin JavaScript (`required`, `min`, `max`, `pattern`, `maxlength`).
- Utilizar estructuras de selección excluyentes (radio buttons) y de opción múltiple (checkboxes).
- Implementar listas de sugerencia dinámicas mediante el elemento `<datalist>`.

## Estructura del Repositorio

```
peylw-2026-practicos-reyes-6775-42/
├── index.html        (página de bienvenida)
├── acercade.html     (página de biografía e imagen)
├── contacto.html     (formulario de contacto con validación)
├── styles.css        (hoja de estilos básica vinculada)
├── img/
│   └── img.png       (imagen de perfil)
├── README.md         (carátula del TP3)
└── REFLEXION.md      (análisis)
```

## Formulario de Contacto (contacto.html)

- Nombre: obligatorio, máximo 20 caracteres.
- Apellido: máximo 20 caracteres.
- Correo Electrónico: obligatorio, formato email.
- Teléfono: con placeholder de ejemplo.
- Edad: min 16, max 120.
- Dirección: texto libre.
- Provincia: entrada con `<datalist>` de las provincias patagónicas.
- Código Postal: validado con `pattern="^[A-Z]\d{4}[A-Z]{3}$"`.
- Método de Contacto: radios excluyentes (Correo electrónico por defecto).
- Suscripciones: checkboxes múltiples (Alertas por defecto).
- Botón "Cargar" con id `btn-cargar-reyes-6775-42`.
- Tabla de resumen vacía con celdas `id="resumen-*"` para rellenar con JavaScript en prácticos futuros.

## Tecnologías utilizadas

- HTML5 semántico
- CSS
- Validación nativa de formularios HTML5
- Git y GitHub (despliegue con GitHub Pages)