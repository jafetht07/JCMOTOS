# JCMOTOS

> Catálogo estático de motocicletas en una sola página con secciones por marca y cotización por WhatsApp.

## 🇪🇸 Español

### ¿Qué es?

JCMOTOS es una página única con un catálogo de motocicletas de Costa Rica organizado por marca. El visitante selecciona una marca en un desplegable y se muestra la sección con las fichas de cada modelo (imagen, cilindraje, precio y año). Cada ficha incluye un botón que abre WhatsApp con un mensaje prellenado para cotizar.

El contenido está escrito directamente en el HTML, sin base de datos, backend ni peticiones de red.

### Características

- **Selección por marca**: un `<select>` con 14 marcas y la función `showModels()`, que oculta todas las secciones y muestra la del `id` seleccionado.
- **95 fichas de motos** en 14 secciones: Honda, Formula, Yamaha, Suzuki, Freedom, Katana, Serpento, Haojue, Bajaj, Benelli, Vento, TVS, Cuadraciclos y BICIMOTOS.
- **Cotización por WhatsApp**: `sendMessage(modelo)` abre `wa.me` con un mensaje que menciona el modelo consultado.
- Bloque de estilos dentro del `<head>` y una hoja de estilos externa enlazada.
- Maquetación sencilla: secciones ocultas con `display: none`, fondo de imagen fija y tarjetas con animaciones de entrada y hover.

### Stack técnico

- HTML5 y CSS3, sin frameworks.
- JavaScript vanilla, sin dependencias ni compilación.
- Sin Firebase, sin `localStorage`, sin `sessionStorage`, sin `fetch` y sin JSON: los datos son HTML estático.

### Estructura del proyecto

```
JCMOTOS/
├── indexx.html   # Página completa: estilos en línea, 14 secciones y las 95 fichas
├── styles.css    # En realidad es un documento HTML completo ("Mundo Motor"), no una hoja CSS
├── script.js     # Variante de sendMessage() que no está enlazada desde el HTML
└── README.md     # 9 bytes
```

Las imágenes se referencian por nombre relativo (por ejemplo `Honda XR190L.jpeg`) y están incluidas en el repositorio: son cerca de 95 archivos `.jpeg` en la raíz. Deben permanecer en la misma carpeta que el HTML.

### Cómo ejecutarlo

No necesita instalación: abre `indexx.html` en el navegador. Para publicarlo en GitHub Pages hay que renombrarlo a `index.html`, que es el archivo que Pages sirve como portada.

### Datos y configuración

- Los datos de las motos están escritos a mano en `indexx.html`.
- El número de WhatsApp de las cotizaciones está en la función `sendMessage` de `indexx.html`.
- No hay credenciales, panel de administración ni almacenamiento.

### Relación con los otros repositorios

`JCMOTOS`, `MotosJC` y `MOTOMANIA-JC` son variantes del mismo catálogo de motos, no proyectos distintos.

- **`MOTOMANIA-JC` es la versión más completa.** Reemplaza el HTML estático por datos en Firebase (Firestore y Storage) y añade panel de administración con CRUD de motos y marcas, generador de volantes PDF, estadísticas, login y un catálogo público renderizado en JavaScript con 109 motos de 15 marcas.
- **`JCMOTOS` y `MotosJC` comparten el mismo `indexx.html` y el mismo `script.js`**, idénticos byte a byte. Solo cambia `styles.css`.
- **`JCMOTOS` parece ser la versión previa de `MotosJC`.** Su `styles.css` es la variante más simple: no tiene `meta description`, no incluye el ajuste para móviles que desactiva la imagen de fondo por debajo de 768 px y no ajusta el tamaño de `h1` ni de los botones. El color del encabezado está escrito como valor literal (`rgb(247, 236, 236)`) en lugar de `white`.
- Este repositorio **no** incluye las funciones del panel de administración ni del PDF; es la etapa estática del catálogo.

### Notas y limitaciones

- **`styles.css` no es CSS**: contiene un documento HTML completo de la plantilla "Mundo Motor", con `<!DOCTYPE html>`, `<head>` y su propio `<style>`. El navegador no lo aplica como hoja de estilos, así que la apariencia real proviene del `<style>` interno de `indexx.html`.
- **`script.js` no se usa**: `indexx.html` no lo enlaza y define su propio `sendMessage`. El archivo contiene una versión que pregunta por financiamiento o contado y solicita la cédula por `prompt` cuando se elige financiamiento; esa lógica no está activa.
- **ID duplicado**: hay una segunda `<section id="Benelli">` con texto de relleno al final del documento; como los `id` deben ser únicos, esa sección queda inalcanzable.
- **Ficha duplicada**: la BICIMOTO KATANA MINI aparece dos veces con los mismos datos.
- **Sin validación ni mantenimiento**: precios y cilindrajes son texto escrito a mano; cualquier cambio implica editar el HTML.
- **Rutas de imagen relativas**: si las fotos no están junto al HTML, las fichas quedan sin imagen y sin mensaje de error.
- **`indexx.html` no funciona como portada** en GitHub Pages ni en hosts que esperan `index.html`.

---

## 🇬🇧 English

### What is it?

JCMOTOS is a single-page motorcycle catalog for Costa Rica organized by brand. The visitor selects a brand from a dropdown and the matching section appears with one card per model (photo, displacement, price and year). Each card has a button that opens WhatsApp with a prefilled quote request.

Content is written directly in the HTML, with no database, backend or network request.

### Features

- **Brand selection**: a `<select>` with 14 brands and the `showModels()` function, which hides every section and shows the one matching the selected `id`.
- **95 motorcycle cards** across 14 sections: Honda, Formula, Yamaha, Suzuki, Freedom, Katana, Serpento, Haojue, Bajaj, Benelli, Vento, TVS, Cuadraciclos and BICIMOTOS.
- **WhatsApp quotes**: `sendMessage(model)` opens `wa.me` with a message that names the selected model.
- A `<style>` block inside `<head>` plus a linked external stylesheet.
- Simple layout: sections hidden with `display: none`, a fixed background image and cards with entrance and hover animations.

### Tech stack

- HTML5 and CSS3, no frameworks.
- Vanilla JavaScript, no dependencies and no build step.
- No Firebase, no `localStorage`, no `sessionStorage`, no `fetch` and no JSON: the data is static HTML.

### Project structure

```
JCMOTOS/
├── indexx.html   # Full page: inline styles, 14 sections and all 95 cards
├── styles.css    # Actually a complete HTML document ("Mundo Motor"), not a CSS file
├── script.js     # A sendMessage() variant that is never linked from the HTML
└── README.md     # 9 bytes
```

Images are referenced by relative filename (for example `Honda XR190L.jpeg`) and are included in the repository: roughly 95 `.jpeg` files at the root. They must stay next to the HTML.

### How to run it

Nothing to install: open `indexx.html` in a browser. To publish it on GitHub Pages, rename it to `index.html`, which is the file Pages serves as the entry point.

### Data and configuration

- Motorcycle data is hand-written in `indexx.html`.
- The WhatsApp number used for quotes lives in the `sendMessage` function in `indexx.html`.
- There are no credentials, no admin panel and no storage.

### Relationship to the other repositories

`JCMOTOS`, `MotosJC` and `MOTOMANIA-JC` are variants of the same motorcycle catalog, not separate projects.

- **`MOTOMANIA-JC` is the most complete version.** It replaces the static HTML with Firebase data (Firestore and Storage) and adds an admin panel with motorcycle and brand CRUD, a PDF flyer generator, statistics, login, and a JavaScript-rendered public catalog with 109 motorcycles across 15 brands.
- **`JCMOTOS` and `MotosJC` share the same `indexx.html` and `script.js`**, byte-for-byte identical. Only `styles.css` differs.
- **`JCMOTOS` appears to be the earlier version of `MotosJC`.** Its `styles.css` is the simpler variant: no `meta description`, no mobile rule that disables the background image below 768 px, and no size adjustments for `h1` or buttons. The header color is written as a literal value (`rgb(247, 236, 236)`) instead of `white`.
- This repository does **not** include the admin panel or PDF features; it is the static stage of the catalog.

### Notes and limitations

- **`styles.css` is not CSS**: it contains a full HTML document for the "Mundo Motor" template, with `<!DOCTYPE html>`, `<head>` and its own `<style>`. The browser does not apply it as a stylesheet, so the real look comes from the inline `<style>` in `indexx.html`.
- **`script.js` is unused**: `indexx.html` never links it and defines its own `sendMessage`. The file holds a version that asks about financing versus cash and requests the national ID through `prompt` for financing; that logic is not active.
- **Duplicate ID**: a second `<section id="Benelli">` with placeholder text sits at the end of the document; since IDs must be unique, that section is unreachable.
- **Duplicate card**: the BICIMOTO KATANA MINI appears twice with identical data.
- **No validation or maintainability**: prices and displacements are hand-written text; any change means editing the HTML.
- **Relative image paths**: if the photos are not next to the HTML, cards render without an image and without any error message.
- **`indexx.html` does not work as a landing page** on GitHub Pages or hosts that expect `index.html`.

---

Autor: Jafeth (GitHub: [@jafetht07](https://github.com/jafetht07))
