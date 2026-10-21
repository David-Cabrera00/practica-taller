# Pixel-Perfect Cheatsheet (Tailwind CSS)

## 1. Posicionamiento de Badges / Iconos Flotantes
- Contenedor padre: `relative`
- Elemento flotante hijo: `absolute top-4 right-4` o `absolute top-3 left-3`

## 2. Redondeados Densos (Estilo Moderno)
- Botones / Pills: `rounded-full`
- Tarjetas medianas: `rounded-2xl`
- Tarjetas y Contenedores grandes: `rounded-3xl` o `rounded-[2.5rem]`

## 3. Grillas Típicas
- 4 columnas (desktop) / 2 columnas (móvil): `grid grid-cols-2 md:grid-cols-4 gap-4`
- 3 columnas (desktop) / 1 columna (móvil): `grid grid-cols-1 md:grid-cols-3 gap-6`
- Grilla asimétrica (Texto + Fotos): `grid grid-cols-1 md:grid-cols-12 gap-8` -> (`md:col-span-7` e `md:col-span-5`)

## 4. Tipografía y Jerarquía
- Títulos principales: `text-4xl md:text-6xl font-black uppercase tracking-tight leading-none`
- Títulos de cards: `text-xs md:text-sm font-bold line-clamp-1`
- Textos secundarios / descripciones: `text-xs text-stone-500 leading-relaxed`

## 5. Reemplazo Rápido de Paleta (Ctrl + H)
- De Azul a Naranja: Buscar `blue-600` -> Reemplazar por `orange-600`
- De Azul a Rosa/Vino: Buscar `blue-600` -> Reemplazar por `rose-700`
- De Azul a Esmeralda: Buscar `blue-600` -> Reemplazar por `emerald-600`

# 🚀 Guía Definitiva y Chuleta: Examen Pixel Perfect

Guía de referencia rápida y estructura explicada desde cero para maquetar interfaces web profesionales usando **HTML5**, **Tailwind CSS (CDN)**, **Sublime Text** y **Git**.

---

## 📂 1. Estructura Ideal del Proyecto
Organiza tus carpetas de la siguiente manera para mantener el orden y acceder rápidamente a los componentes:

```text
mi-proyecto-examen/
│
├── index.html              <-- Lienzo en blanco principal de trabajo
├── README.md               <-- Esta guía de referencia rápida
│
├── img/                    <-- Carpeta para guardar tus imágenes locales
│   ├── logo.png
│   └── producto-1.jpg
│
└── componentes/            <-- Librería de bloques reutilizables
    ├── 01-navbars.html
    ├── 02-heroes.html
    ├── 03-cards.html
    ├── 04-features.html
    ├── 05-collages.html
    ├── 06-banners.html
    └── 07-footers.html