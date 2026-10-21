# Guía de examen: crear una página web desde cero
## HTML5 + Tailwind CSS por CDN + Sublime Text

Esta guía está pensada para usarla como **receta durante el examen**. Sigue el orden, copia la estructura base y adapta los bloques al diseño que te pidan. La prioridad es construir primero una página completa y funcional, y después ajustar los detalles visuales para acercarte al diseño de referencia (*pixel perfect*).

---

## Índice rápido

1. [Preparar el proyecto](#1-preparar-el-proyecto)
2. [Crear el HTML base](#2-crear-el-html-base)
3. [Planear la página antes de escribir código](#3-planear-la-página-antes-de-escribir-código)
4. [Construir la página por secciones](#4-construir-la-página-por-secciones)
5. [Chuleta de clases Tailwind](#5-chuleta-de-clases-tailwind)
6. [Bloques listos para adaptar](#6-bloques-listos-para-adaptar)
7. [Imágenes, iconos y detalles](#7-imágenes-iconos-y-detalles)
8. [Responsive: móvil y escritorio](#8-responsive-móvil-y-escritorio)
9. [Cómo acercarse al diseño de referencia](#9-cómo-acercarse-al-diseño-de-referencia)
10. [Errores frecuentes y soluciones](#10-errores-frecuentes-y-soluciones)
11. [Git: guardar avances](#11-git-guardar-avances)
12. [Checklist final del examen](#12-checklist-final-del-examen)
13. [Chuleta ultrarrápida](#13-chuleta-ultrarrápida)

---

## 1. Preparar el proyecto

### 1.1 Crear la carpeta

En Sublime Text, usa **File → Open Folder** para abrir la carpeta del proyecto. Puedes crearla primero desde el explorador de archivos.

Estructura recomendada:

```text
mi-proyecto-examen/
├── index.html
├── README.md
├── img/
│   ├── logo.png
│   ├── hero.jpg
│   └── producto-1.jpg
└── componentes/
    ├── 01-navbars.html
    ├── 02-heroes.html
    ├── 03-cards.html
    ├── 04-features.html
    ├── 05-collages.html
    ├── 06-banners.html
    └── 07-footers.html
```

- `index.html`: página principal que se abre en el navegador.
- `img/`: imágenes locales del proyecto.
- `componentes/`: ejemplos de bloques que puedes consultar y reutilizar manualmente.
- `README.md`: esta guía.

**Importante:** el navegador no inserta automáticamente el contenido de los archivos de `componentes/`. Si necesitas usar uno, copia su HTML dentro de `index.html` o utiliza una herramienta que permita incluir componentes.

### 1.2 Abrir y probar la página

1. Abre `index.html` en Sublime Text.
2. Guarda los cambios con `Ctrl + S`.
3. Abre el archivo en Chrome o en el navegador permitido por el examen.
4. Después de cada cambio, guarda y recarga con `Ctrl + R`.

Tailwind por CDN necesita conexión a internet. Si el examen no garantiza internet, confirma antes si se permite una instalación local o si debes trabajar con CSS tradicional.

---

## 2. Crear el HTML base

Copia esta plantilla en `index.html`. Es el punto de partida para casi cualquier página sencilla.

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Nombre de la página</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>

<body class="bg-white text-stone-900 antialiased">

  <!-- 1. Navegación -->
  <header>
    <!-- Navbar -->
  </header>

  <main>
    <!-- 2. Hero / portada -->
    <!-- 3. Contenido principal -->
    <!-- 4. Características, productos o servicios -->
    <!-- 5. Banner / llamada a la acción -->
  </main>

  <!-- 6. Pie de página -->
  <footer>
    <!-- Footer -->
  </footer>

</body>
</html>
```

### ¿Qué hace cada parte?

- `lang="es"`: indica que el documento está en español.
- `charset="UTF-8"`: permite mostrar tildes y caracteres especiales.
- `viewport`: adapta la página a pantallas pequeñas.
- `tailwindcss.com`: carga Tailwind mediante CDN.
- `<header>`: suele contener el menú.
- `<main>`: contiene el contenido principal.
- `<section>`: separa bloques de contenido.
- `<footer>`: contiene información final, enlaces o redes.

**Regla:** escribe clases de Tailwind directamente en el atributo `class`, por ejemplo:

```html
<h1 class="text-4xl font-black tracking-tight">
  Título principal
</h1>
```

---

## 3. Planear la página antes de escribir código

Antes de programar, mira la referencia y divide el diseño en bloques. No empieces ajustando sombras o colores pequeños.

### 3.1 Identifica las secciones

Una página de presentación suele tener este orden:

1. **Navbar:** logo, enlaces y botón.
2. **Hero:** título grande, descripción, botón e imagen.
3. **Beneficios o características:** tarjetas con icono, título y texto.
4. **Productos, galería o contenido:** cuadrícula de elementos.
5. **Banner CTA:** mensaje final y botón.
6. **Footer:** logo, enlaces y datos secundarios.

No todas las páginas necesitan todas las secciones. **Respeta lo que aparece en la referencia del examen** y elimina los bloques que no correspondan.

### 3.2 Observa estos detalles

- **Estructura:** ¿cuántas secciones hay y en qué orden?
- **Ancho:** ¿el contenido ocupa toda la pantalla o está centrado?
- **Columnas:** ¿hay una o dos columnas?
- **Espaciado:** ¿hay mucho aire o todo está compacto?
- **Tipografía:** ¿los títulos son grandes, gruesos, mayúsculos?
- **Color:** identifica el color principal, el fondo y los colores secundarios.
- **Forma:** observa si las tarjetas son cuadradas, redondeadas o tipo píldora.
- **Imágenes:** fíjate en su proporción, tamaño y recorte.

### 3.3 Orden de trabajo recomendado

1. Estructura HTML completa.
2. Distribución y tamaños.
3. Tipografía y colores.
4. Imágenes.
5. Bordes, sombras y detalles.
6. Revisión en móvil y escritorio.

---

## 4. Construir la página por secciones

Copia el bloque que necesites dentro de `index.html` y cambia los textos, enlaces, imágenes y colores.

### 4.1 Navbar / menú superior

```html
<header class="border-b border-stone-200 bg-white">
  <nav class="mx-auto flex max-w-7xl items-center justify-between px-6 py-4">
    <a href="#" class="text-xl font-black tracking-tight">
      MARCA
    </a>

    <div class="hidden items-center gap-6 md:flex">
      <a href="#inicio" class="text-sm font-medium hover:text-orange-600">Inicio</a>
      <a href="#servicios" class="text-sm font-medium hover:text-orange-600">Servicios</a>
      <a href="#nosotros" class="text-sm font-medium hover:text-orange-600">Nosotros</a>
    </div>

    <a href="#contacto"
       class="rounded-full bg-stone-900 px-5 py-3 text-sm font-bold text-white hover:bg-orange-600">
      Contáctanos
    </a>
  </nav>
</header>
```

**Claves:**
- `flex items-center justify-between`: elementos en una fila, alineados y separados.
- `max-w-7xl mx-auto`: limita el ancho y centra el contenido.
- `hidden md:flex`: oculta los enlaces en móvil y los muestra desde el breakpoint `md`.
- `hover:text-orange-600`: cambia el color al pasar el cursor.

Si el diseño necesita un menú visible en móvil, no uses `hidden` sin crear una alternativa móvil. Para una maqueta estática, puedes mostrar una versión simplificada del menú.

### 4.2 Hero / portada con texto e imagen

```html
<section id="inicio" class="bg-stone-100">
  <div class="mx-auto grid max-w-7xl grid-cols-1 items-center gap-10 px-6 py-16 md:grid-cols-2 md:py-24">

    <div>
      <p class="mb-4 text-sm font-bold uppercase tracking-[0.2em] text-orange-600">
        Frase introductoria
      </p>

      <h1 class="text-4xl font-black leading-none tracking-tight md:text-6xl">
        UN TÍTULO GRANDE QUE LLAME LA ATENCIÓN
      </h1>

      <p class="mt-6 max-w-xl text-base leading-relaxed text-stone-600 md:text-lg">
        Escribe una descripción breve que explique la propuesta de valor de la página.
      </p>

      <div class="mt-8 flex flex-wrap gap-3">
        <a href="#servicios"
           class="rounded-full bg-orange-600 px-6 py-3 font-bold text-white hover:bg-orange-700">
          Explorar
        </a>
        <a href="#nosotros"
           class="rounded-full border border-stone-300 px-6 py-3 font-bold hover:bg-white">
          Conocer más
        </a>
      </div>
    </div>

    <div class="relative">
      <img
        src="img/hero.jpg"
        alt="Descripción de la imagen"
        class="h-72 w-full rounded-3xl object-cover md:h-[480px]"
      >
      <span class="absolute right-4 top-4 rounded-full bg-white px-4 py-2 text-xs font-bold shadow">
        NUEVO
      </span>
    </div>

  </div>
</section>
```

**Si no tienes una imagen local**, reemplaza `img/hero.jpg` por una URL de imagen permitida. Si la imagen no carga, revisa la ruta, el nombre y la extensión del archivo.

### 4.3 Sección de tarjetas

```html
<section id="servicios" class="px-6 py-16 md:py-24">
  <div class="mx-auto max-w-7xl">
    <div class="mb-10 max-w-2xl">
      <p class="mb-3 text-sm font-bold uppercase tracking-widest text-orange-600">
        Lo que ofrecemos
      </p>
      <h2 class="text-3xl font-black tracking-tight md:text-5xl">
        Todo lo que necesitas
      </h2>
      <p class="mt-4 leading-relaxed text-stone-600">
        Una descripción corta para presentar los elementos de esta sección.
      </p>
    </div>

    <div class="grid grid-cols-1 gap-5 sm:grid-cols-2 lg:grid-cols-3">
      <article class="rounded-2xl border border-stone-200 p-6 transition hover:-translate-y-1 hover:shadow-lg">
        <div class="mb-5 flex h-12 w-12 items-center justify-center rounded-2xl bg-orange-100 text-xl">
          ✦
        </div>
        <h3 class="text-lg font-bold">Título de tarjeta</h3>
        <p class="mt-2 text-sm leading-relaxed text-stone-600">
          Explica el beneficio o la característica en una o dos frases.
        </p>
        <a href="#" class="mt-5 inline-block text-sm font-bold text-orange-600 hover:underline">
          Saber más →
        </a>
      </article>

      <article class="rounded-2xl border border-stone-200 p-6 transition hover:-translate-y-1 hover:shadow-lg">
        <div class="mb-5 flex h-12 w-12 items-center justify-center rounded-2xl bg-orange-100 text-xl">
          ◈
        </div>
        <h3 class="text-lg font-bold">Otro beneficio</h3>
        <p class="mt-2 text-sm leading-relaxed text-stone-600">
          Mantén una longitud de texto similar para que las tarjetas se vean uniformes.
        </p>
        <a href="#" class="mt-5 inline-block text-sm font-bold text-orange-600 hover:underline">
          Saber más →
        </a>
      </article>

      <article class="rounded-2xl border border-stone-200 p-6 transition hover:-translate-y-1 hover:shadow-lg">
        <div class="mb-5 flex h-12 w-12 items-center justify-center rounded-2xl bg-orange-100 text-xl">
          ◎
        </div>
        <h3 class="text-lg font-bold">Tercer beneficio</h3>
        <p class="mt-2 text-sm leading-relaxed text-stone-600">
          Duplica una tarjeta y cambia su contenido si necesitas más elementos.
        </p>
        <a href="#" class="mt-5 inline-block text-sm font-bold text-orange-600 hover:underline">
          Saber más →
        </a>
      </article>
    </div>
  </div>
</section>
```

Para crear más tarjetas, copia un bloque `<article>...</article>` y pégalo dentro del contenedor `grid`.

### 4.4 Cuadrícula de productos o galería

```html
<section class="bg-stone-50 px-6 py-16">
  <div class="mx-auto max-w-7xl">
    <div class="mb-8 flex flex-wrap items-end justify-between gap-4">
      <div>
        <p class="text-sm font-bold uppercase tracking-widest text-orange-600">Colección</p>
        <h2 class="mt-2 text-3xl font-black md:text-4xl">Productos destacados</h2>
      </div>
      <a href="#" class="font-bold hover:text-orange-600">Ver todos →</a>
    </div>

    <div class="grid grid-cols-2 gap-4 md:grid-cols-4">
      <article>
        <img src="img/producto-1.jpg" alt="Producto 1"
             class="aspect-[4/5] w-full rounded-2xl object-cover">
        <h3 class="mt-3 text-sm font-bold md:text-base">Producto uno</h3>
        <p class="mt-1 text-sm text-stone-500">$99.000</p>
      </article>

      <article>
        <img src="img/producto-2.jpg" alt="Producto 2"
             class="aspect-[4/5] w-full rounded-2xl object-cover">
        <h3 class="mt-3 text-sm font-bold md:text-base">Producto dos</h3>
        <p class="mt-1 text-sm text-stone-500">$89.000</p>
      </article>

      <article>
        <img src="img/producto-3.jpg" alt="Producto 3"
             class="aspect-[4/5] w-full rounded-2xl object-cover">
        <h3 class="mt-3 text-sm font-bold md:text-base">Producto tres</h3>
        <p class="mt-1 text-sm text-stone-500">$120.000</p>
      </article>

      <article>
        <img src="img/producto-4.jpg" alt="Producto 4"
             class="aspect-[4/5] w-full rounded-2xl object-cover">
        <h3 class="mt-3 text-sm font-bold md:text-base">Producto cuatro</h3>
        <p class="mt-1 text-sm text-stone-500">$75.000</p>
      </article>
    </div>
  </div>
</section>
```

Cambia las rutas y textos por los datos reales del ejercicio. Si solo hay tres elementos, elimina el cuarto en lugar de inventar contenido que no esté en la referencia.

### 4.5 Sección de dos columnas: texto + imagen

```html
<section id="nosotros" class="px-6 py-16 md:py-24">
  <div class="mx-auto grid max-w-7xl grid-cols-1 items-center gap-10 md:grid-cols-12">
    <div class="md:col-span-7">
      <h2 class="text-3xl font-black md:text-5xl">Una historia que contar</h2>
      <p class="mt-5 leading-relaxed text-stone-600">
        Coloca aquí el texto principal de la sección.
      </p>
      <ul class="mt-6 space-y-3 text-sm">
        <li>✓ Primera ventaja o característica</li>
        <li>✓ Segunda ventaja o característica</li>
        <li>✓ Tercera ventaja o característica</li>
      </ul>
    </div>
    <div class="md:col-span-5">
      <img src="img/hero.jpg" alt="Imagen relacionada"
           class="h-80 w-full rounded-3xl object-cover md:h-[420px]">
    </div>
  </div>
</section>
```

`md:grid-cols-12` crea una cuadrícula de doce columnas. `md:col-span-7` usa siete columnas y `md:col-span-5` usa cinco.

### 4.6 Banner / llamada a la acción (CTA)

```html
<section id="contacto" class="px-6 py-12 md:py-16">
  <div class="mx-auto flex max-w-7xl flex-col items-start justify-between gap-6 rounded-3xl bg-stone-900 p-8 text-white md:flex-row md:items-center md:p-12">
    <div class="max-w-2xl">
      <p class="text-sm font-bold uppercase tracking-widest text-orange-400">¿Listo para empezar?</p>
      <h2 class="mt-3 text-3xl font-black md:text-4xl">Haz que suceda hoy.</h2>
      <p class="mt-3 text-stone-300">Una frase breve que motive a realizar la acción.</p>
    </div>
    <a href="mailto:contacto@ejemplo.com"
       class="shrink-0 rounded-full bg-orange-600 px-6 py-3 font-bold text-white hover:bg-orange-700">
      Contactar
    </a>
  </div>
</section>
```

### 4.7 Footer / pie de página

```html
<footer class="bg-stone-950 px-6 py-10 text-white">
  <div class="mx-auto flex max-w-7xl flex-col justify-between gap-8 md:flex-row">
    <div>
      <a href="#" class="text-xl font-black">MARCA</a>
      <p class="mt-3 max-w-sm text-sm leading-relaxed text-stone-400">
        Una descripción breve de la marca o del proyecto.
      </p>
    </div>

    <div class="flex flex-wrap gap-x-8 gap-y-3 text-sm text-stone-300">
      <a href="#inicio" class="hover:text-white">Inicio</a>
      <a href="#servicios" class="hover:text-white">Servicios</a>
      <a href="#nosotros" class="hover:text-white">Nosotros</a>
      <a href="#contacto" class="hover:text-white">Contacto</a>
    </div>
  </div>

  <div class="mx-auto mt-8 max-w-7xl border-t border-white/10 pt-5 text-xs text-stone-500">
    © 2026 Marca. Todos los derechos reservados.
  </div>
</footer>
```

Actualiza el año y los datos si el ejercicio lo requiere. Los enlaces `#inicio`, `#servicios`, etc. funcionan si existe un elemento con ese `id`.

---

## 5. Chuleta de clases Tailwind

### 5.1 Contenedores y ancho

| Necesidad | Clase |
|---|---|
| Centrar un contenedor | `mx-auto` |
| Ancho máximo habitual | `max-w-7xl` |
| Ancho medio | `max-w-4xl` |
| Ocupar todo el ancho | `w-full` |
| Altura mínima de pantalla | `min-h-screen` |
| Espaciado horizontal | `px-6` |
| Espaciado vertical | `py-16` |

### 5.2 Flexbox y alineación

| Necesidad | Clase |
|---|---|
| Elementos en fila | `flex` |
| Elementos en columna | `flex flex-col` |
| Separar extremos | `justify-between` |
| Centrar horizontalmente | `justify-center` |
| Centrar verticalmente | `items-center` |
| Permitir salto de línea | `flex-wrap` |
| Espacio entre elementos | `gap-4` o `gap-6` |

### 5.3 Grillas típicas

```html
<!-- 2 columnas en móvil, 4 desde md -->
<div class="grid grid-cols-2 gap-4 md:grid-cols-4">...</div>

<!-- 1 columna en móvil, 2 desde md -->
<div class="grid grid-cols-1 gap-8 md:grid-cols-2">...</div>

<!-- 1 columna en móvil, 3 desde lg -->
<div class="grid grid-cols-1 gap-6 sm:grid-cols-2 lg:grid-cols-3">...</div>

<!-- Composición asimétrica de 12 columnas -->
<div class="grid grid-cols-1 gap-8 md:grid-cols-12">
  <div class="md:col-span-7">Texto</div>
  <div class="md:col-span-5">Imagen</div>
</div>
```

### 5.4 Tipografía y jerarquía

| Elemento | Clase de referencia |
|---|---|
| Título grande | `text-4xl font-black tracking-tight md:text-6xl` |
| Título de sección | `text-3xl font-black md:text-5xl` |
| Título de tarjeta | `text-base font-bold` |
| Texto normal | `text-base leading-relaxed` |
| Texto secundario | `text-sm text-stone-500 leading-relaxed` |
| Etiqueta superior | `text-xs font-bold uppercase tracking-widest` |
| Texto centrado | `text-center` |
| Mayúsculas | `uppercase` |
| Peso fuerte | `font-bold` o `font-black` |

**Consejo:** no uses títulos gigantes en todas las secciones. El tamaño debe reflejar la jerarquía visual del diseño.

### 5.5 Colores de ejemplo

| Estilo | Fondo o texto |
|---|---|
| Blanco | `bg-white`, `text-white` |
| Negro suave | `bg-stone-950`, `text-stone-900` |
| Gris claro | `bg-stone-100`, `text-stone-500` |
| Azul | `bg-blue-600`, `text-blue-600` |
| Naranja | `bg-orange-600`, `text-orange-600` |
| Rosa/vino | `bg-rose-700`, `text-rose-700` |
| Esmeralda | `bg-emerald-600`, `text-emerald-600` |

**Cambio rápido de paleta en Sublime Text:** `Ctrl + H` abre Buscar/Reemplazar. Por ejemplo, cambia `blue-600` por `orange-600`. Revisa también variantes como `blue-700`, `blue-100` y `text-blue-600`; cambiar solo un tono puede dejar colores inconsistentes.

### 5.6 Bordes, redondeados y sombras

| Necesidad | Clase |
|---|---|
| Borde fino | `border border-stone-200` |
| Esquinas suaves | `rounded-xl` |
| Tarjeta redondeada | `rounded-2xl` |
| Contenedor muy redondeado | `rounded-3xl` |
| Botón tipo píldora | `rounded-full` |
| Sombra ligera | `shadow-sm` |
| Sombra marcada | `shadow-lg` |
| Sin sombra | `shadow-none` |

### 5.7 Imágenes

```html
<!-- Imagen completa dentro de un marco, recortada -->
<img src="img/foto.jpg" alt="Descripción"
     class="h-80 w-full rounded-2xl object-cover">

<!-- Mantener proporción vertical -->
<img src="img/producto.jpg" alt="Producto"
     class="aspect-[4/5] w-full rounded-2xl object-cover">

<!-- Imagen cuadrada -->
<img src="img/foto.jpg" alt="Descripción"
     class="aspect-square w-full rounded-2xl object-cover">
```

- `object-cover`: llena el marco recortando lo que sobra.
- `object-contain`: muestra la imagen completa, dejando espacio si hace falta.
- `w-full`: ocupa el ancho disponible.
- `h-80`: fija una altura aproximada.
- `aspect-[4/5]`: define una proporción vertical.

### 5.8 Posicionamiento de badges e iconos flotantes

El padre debe tener `relative`; el elemento flotante, `absolute`.

```html
<div class="relative">
  <img src="img/hero.jpg" alt="Imagen" class="h-80 w-full rounded-3xl object-cover">
  <span class="absolute right-4 top-4 rounded-full bg-white px-4 py-2 text-xs font-bold shadow">
    DESTACADO
  </span>
</div>
```

Posiciones rápidas: `absolute top-4 right-4`, `absolute top-3 left-3` o `absolute bottom-4 left-4`.

### 5.9 Efectos al pasar el cursor

```html
<a class="bg-orange-600 text-white hover:bg-orange-700">Botón</a>

<article class="transition hover:-translate-y-1 hover:shadow-lg">Tarjeta</article>

<a class="text-stone-700 hover:text-orange-600">Enlace</a>
```

`transition` suaviza el cambio; `hover:` aplica el estilo al pasar el cursor. No agregues efectos si la referencia es plana o minimalista.

---

## 6. Bloques listos para adaptar

### 6.1 Botón principal

```html
<a href="#"
   class="inline-flex items-center justify-center rounded-full bg-orange-600 px-6 py-3 text-sm font-bold text-white transition hover:bg-orange-700">
  Texto del botón
</a>
```

### 6.2 Etiqueta pequeña

```html
<span class="inline-flex rounded-full bg-orange-100 px-3 py-1 text-xs font-bold uppercase tracking-wide text-orange-700">
  Destacado
</span>
```

### 6.3 Tarjeta con imagen

```html
<article class="overflow-hidden rounded-2xl border border-stone-200 bg-white">
  <img src="img/producto-1.jpg" alt="Descripción"
       class="aspect-[4/3] w-full object-cover">
  <div class="p-5">
    <p class="text-xs font-bold uppercase tracking-widest text-orange-600">Categoría</p>
    <h3 class="mt-2 text-lg font-bold">Nombre de la tarjeta</h3>
    <p class="mt-2 text-sm leading-relaxed text-stone-600">Descripción breve del contenido.</p>
  </div>
</article>
```

### 6.4 Texto centrado

```html
<div class="mx-auto max-w-3xl px-6 py-16 text-center md:py-24">
  <p class="text-sm font-bold uppercase tracking-widest text-orange-600">Etiqueta</p>
  <h2 class="mt-3 text-3xl font-black tracking-tight md:text-5xl">Título de la sección</h2>
  <p class="mx-auto mt-5 max-w-2xl leading-relaxed text-stone-600">Texto de introducción.</p>
</div>
```

### 6.5 Fondo con imagen

```html
<section class="bg-cover bg-center px-6 py-24 text-white"
         style="background-image: url('img/hero.jpg');">
  <div class="mx-auto max-w-7xl">
    <h1 class="max-w-2xl text-4xl font-black md:text-6xl">Título sobre la imagen</h1>
    <p class="mt-5 max-w-xl text-white/80">Descripción breve.</p>
  </div>
</section>
```

Si el texto no se lee, añade una capa oscura o usa una imagen menos cargada. La legibilidad tiene prioridad sobre el efecto visual.

---

## 7. Imágenes, iconos y detalles

### 7.1 Rutas de imágenes

Si la imagen está en `mi-proyecto-examen/img/hero.jpg`, desde `index.html` se referencia así:

```html
<img src="img/hero.jpg" alt="Descripción">
```

Errores típicos:
- Escribir `Img/` en vez de `img/` puede fallar en algunos entornos.
- El nombre debe coincidir exactamente, incluida la extensión `.jpg`, `.jpeg`, `.png` o `.webp`.
- No uses una ruta de tu computador como `C:\Users\...`; esa ruta no funcionará en otro equipo.

### 7.2 Iconos

Para un examen rápido puedes usar símbolos sencillos o emojis si encajan con el diseño. Si el ejercicio permite una librería de iconos, usa la opción autorizada. No dependas de una librería externa que no esté cargada.

### 7.3 Accesibilidad básica

- Añade `alt` descriptivo a las imágenes.
- Usa un solo `<h1>` principal cuando sea posible.
- Mantén los títulos en orden (`h1`, `h2`, `h3`).
- Los enlaces deben tener un texto que explique su destino.
- Comprueba que el texto contraste con el fondo.

---

## 8. Responsive: móvil y escritorio

Tailwind usa prefijos para aplicar estilos desde ciertos tamaños de pantalla. Las clases sin prefijo suelen ser el diseño base, normalmente móvil.

| Prefijo | Uso habitual |
|---|---|
| Sin prefijo | Móvil y tamaños pequeños |
| `sm:` | Pantallas pequeñas/medianas |
| `md:` | Tabletas y pantallas medianas |
| `lg:` | Escritorio |
| `xl:` | Pantallas grandes |

Ejemplo:

```html
<h1 class="text-4xl md:text-6xl">Título adaptable</h1>

<div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
  <!-- Tarjetas -->
</div>
```

Esto significa:
- En móvil: título de tamaño `4xl`, tarjetas en una columna.
- Desde `md`: el título pasa a `6xl`.
- Desde `sm`: las tarjetas pasan a dos columnas.
- Desde `lg`: las tarjetas pasan a tres columnas.

**Regla de oro:** construye primero para móvil y agrega `sm:`, `md:` o `lg:` para ampliar el diseño. Revisa la página en ancho móvil y escritorio; evita el desbordamiento horizontal.

---

## 9. Cómo acercarse al diseño de referencia

Para un resultado *pixel perfect*, compara tu página con la imagen de referencia sección por sección.

1. **Ancho del contenido:** usa `max-w-7xl mx-auto` si el contenido está centrado y no llega a los bordes.
2. **Espaciado:** ajusta `px-6`, `py-16`, `gap-6`, `mt-6` y `mb-8`.
3. **Tamaños:** ajusta `text-4xl`, `md:text-6xl`, `h-80`, `md:h-[480px]`.
4. **Proporciones:** ajusta `grid-cols-*` y `col-span-*`.
5. **Imágenes:** cambia `object-cover`/`object-contain` y la altura.
6. **Colores:** usa una paleta coherente basada en la referencia.
7. **Detalles:** termina con radios, bordes, sombras y efectos.

### Método de comparación

- Mira la referencia y tu página a un tamaño de ventana similar.
- Corrige primero diferencias grandes: sección faltante, columnas, imagen o ancho.
- Después corrige espaciados y tamaños.
- Deja los detalles pequeños para el final.

No intentes arreglar una mala distribución con márgenes al azar. Si los elementos no están bien colocados, revisa primero el contenedor (`flex`, `grid`, `max-w-*`, `mx-auto`).

---

## 10. Errores frecuentes y soluciones

| Problema | Qué revisar |
|---|---|
| Tailwind no aplica estilos | Comprueba que el `<script src="https://cdn.tailwindcss.com"></script>` esté en `<head>` y que haya conexión. |
| La imagen no aparece | Verifica `src`, carpeta, nombre y extensión. |
| Todo queda pegado a los bordes | Añade `px-6` al contenedor o sección. |
| El contenido es demasiado ancho | Usa `max-w-7xl mx-auto`. |
| Las tarjetas no se alinean | Revisa el contenedor `grid`, `gap-*` y el número de columnas. |
| El badge no se posiciona sobre la imagen | Añade `relative` al padre y `absolute` al badge. |
| La imagen se deforma | Usa `object-cover` u `object-contain` y define proporción/altura. |
| Aparece scroll horizontal | Revisa anchos fijos, textos largos y elementos que exceden la pantalla. |
| Un enlace no lleva a la sección | Comprueba que `href="#servicios"` coincida con `id="servicios"`. |
| El menú desaparece en móvil | Revisa `hidden md:flex` y crea una alternativa móvil si hace falta. |
| El diseño no se parece a la referencia | Comprueba primero estructura, anchos, columnas e imágenes antes de los detalles. |

---

## 11. Git: guardar avances

Usa Git solo si está disponible y permitido en el examen. Abre la terminal en la carpeta del proyecto.

```bash
git init
git add .
git commit -m "Estructura inicial de la página"
```

Después de hacer cambios importantes:

```bash
git add .
git commit -m "Construir secciones principales"
```

Si el repositorio ya existe, no vuelvas a ejecutar `git init` sin necesidad. Para revisar el estado:

```bash
git status
```

---

## 12. Checklist final del examen

Antes de entregar, revisa esta lista:

- [ ] El archivo principal se llama `index.html`.
- [ ] El HTML incluye `doctype`, `lang`, `charset` y `viewport`.
- [ ] Tailwind está cargado si se permite usar CDN.
- [ ] Están todas las secciones de la referencia, en el orden correcto.
- [ ] Los textos y botones corresponden al ejercicio.
- [ ] Las imágenes cargan y tienen rutas correctas.
- [ ] Los enlaces internos apuntan a los `id` correctos.
- [ ] Los colores, tipografía y espaciados son coherentes.
- [ ] El contenido está centrado y no se desborda.
- [ ] Revisé el diseño en móvil y escritorio.
- [ ] Guardé los cambios con `Ctrl + S`.
- [ ] Abrí `index.html` en el navegador y comprobé el resultado.
- [ ] Guardé un commit si Git forma parte del examen.

---

## 13. Chuleta ultrarrápida

### Orden para empezar cualquier página

1. Crear `index.html` y pegar la plantilla base.
2. Identificar las secciones en la referencia.
3. Crear el navbar.
4. Crear el hero.
5. Añadir las secciones de contenido necesarias.
6. Añadir el banner y el footer si aparecen.
7. Ajustar colores, tamaños e imágenes.
8. Probar en navegador y revisar responsive.

### Clases que más vas a usar

```text
Contenedor:  mx-auto max-w-7xl px-6
Sección:     py-16 md:py-24
Fila:        flex items-center justify-between gap-6
Columnas:    grid grid-cols-1 md:grid-cols-2 gap-8
Tarjetas:    grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6
Título:      text-4xl font-black tracking-tight md:text-6xl
Texto:       text-base leading-relaxed text-stone-600
Botón:       rounded-full bg-orange-600 px-6 py-3 font-bold text-white
Tarjeta:     rounded-2xl border border-stone-200 p-6
Imagen:      h-80 w-full rounded-2xl object-cover
Badge:       absolute right-4 top-4 rounded-full bg-white px-3 py-1
Padre badge: relative
```

### Plantilla mínima para recordar

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Mi página</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-white text-stone-900">
  <header><!-- Navbar --></header>
  <main>
    <section id="inicio"><!-- Hero --></section>
    <section id="contenido"><!-- Contenido --></section>
  </main>
  <footer><!-- Footer --></footer>
</body>
</html>
```

**Recuerda:** primero estructura, luego distribución, después estilo y finalmente detalles. Una página completa y bien organizada suele ser mejor punto de partida que una sola sección muy pulida.
