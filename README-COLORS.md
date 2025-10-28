# 🎨 Guía de Paleta de Colores - AmericaPlay

Esta guía detalla la paleta de colores extraída del logo oficial de AmericaPlay y cómo usarla en tu proyecto.

## 🖼️ Origen de la Paleta

La paleta de colores ha sido extraída directamente del logo de AmericaPlay (`public/images/logo.jpeg`), asegurando coherencia visual en todo el proyecto.

---

## 🎨 Colores Principales

### 1. **Primary - Cyan/Turquesa**
**Color del botón play y acentos tecnológicos**

```css
/* Color principal */
--color-primary-500: #06b6d4

/* Variantes disponibles */
primary-50, primary-100, primary-200, ... primary-950
```

**Uso:**
- Botones de acción principales
- Enlaces interactivos
- Iconos de navegación
- Elementos que requieren atención
- Highlights y acentos

**Ejemplo:**
```astro
<button class="bg-primary-500 hover:bg-primary-600 text-white">
  Click aquí
</button>
```

---

### 2. **Secondary - Amarillo/Dorado**
**Color del texto "AMERICA"**

```css
/* Color principal */
--color-secondary-400: #fbbf24

/* Variantes disponibles */
secondary-50, secondary-100, secondary-200, ... secondary-950
```

**Uso:**
- Títulos importantes
- Texto destacado
- Premios y logros
- Etiquetas especiales
- CTAs secundarios

**Ejemplo:**
```astro
<h1>
  <span class="text-secondary-400">America</span>
  <span class="text-white">Play</span>
</h1>
```

---

### 3. **Dark - Azul Oscuro Profundo**
**Fondo principal del logo**

```css
/* Color principal */
--color-dark-900: #0A1628

/* Variantes disponibles */
dark-50, dark-100, dark-200, ... dark-950
```

**Uso:**
- Fondos principales
- Headers y footers
- Secciones hero
- Overlays
- Modo oscuro

**Ejemplo:**
```astro
<div class="bg-dark-900 text-white">
  Contenido con fondo oscuro
</div>
```

---

### 4. **Blue - Azul Royal**
**Mapa mundial y elementos secundarios**

```css
/* Color principal */
--color-blue-800: #1e3a8a

/* Variantes disponibles */
blue-50, blue-100, blue-200, ... blue-950
```

**Uso:**
- Elementos secundarios
- Fondos alternativos
- Secciones informativas
- Detalles decorativos

**Ejemplo:**
```astro
<div class="bg-blue-800 text-white p-6">
  Sección informativa
</div>
```

---

### 5. **Accent - Cyan Brillante**
**Hexágonos y highlights**

```css
/* Color principal */
--color-accent-400: #22d3ee

/* Variantes disponibles */
accent-50, accent-100, accent-200, ... accent-950
```

**Uso:**
- Highlights brillantes
- Badges y notificaciones
- Elementos decorativos
- Estados activos
- Efectos de hover

**Ejemplo:**
```astro
<span class="bg-accent-400 text-dark-900 px-3 py-1 rounded-full">
  Nuevo
</span>
```

---

## 📊 Tabla de Referencia Rápida

| Color | Principal | Uso Primario | Ejemplo de Clase |
|-------|-----------|--------------|------------------|
| **Primary** | `#06b6d4` (Cyan) | Botones, enlaces, acentos | `bg-primary-500` |
| **Secondary** | `#fbbf24` (Dorado) | Títulos destacados | `text-secondary-400` |
| **Dark** | `#0A1628` (Azul Oscuro) | Fondos principales | `bg-dark-900` |
| **Blue** | `#1e3a8a` (Azul Royal) | Elementos secundarios | `bg-blue-800` |
| **Accent** | `#22d3ee` (Cyan Brillante) | Highlights, badges | `bg-accent-400` |

---

## 🎯 Escalas de Color

Cada color tiene 11 variantes (del 50 al 950):

- **50-100**: Muy claros (fondos, highlights sutiles)
- **200-300**: Claros (hover states, backgrounds secundarios)
- **400-500**: **Principal** (el tono más representativo)
- **600-700**: Oscuros (texto en fondos claros)
- **800-900**: Muy oscuros (fondos oscuros, texto en claro)
- **950**: Extremadamente oscuro

---

## 💡 Guía de Uso por Contexto

### Botones

```astro
<!-- Botón primario (acción principal) -->
<button class="bg-primary-500 hover:bg-primary-600 text-white px-6 py-3 rounded-lg transition">
  Acción Principal
</button>

<!-- Botón secundario (acción secundaria) -->
<button class="bg-secondary-400 hover:bg-secondary-500 text-dark-900 px-6 py-3 rounded-lg transition font-semibold">
  Acción Secundaria
</button>

<!-- Botón oscuro (alternativo) -->
<button class="bg-dark-900 hover:bg-dark-800 text-white px-6 py-3 rounded-lg transition">
  Acción Alternativa
</button>

<!-- Botón outline -->
<button class="border-2 border-primary-500 text-primary-600 hover:bg-primary-50 px-6 py-3 rounded-lg transition">
  Outline
</button>
```

### Cards y Contenedores

```astro
<!-- Card con borde izquierdo -->
<div class="bg-primary-50 border-l-4 border-primary-500 p-4 rounded">
  <h3 class="font-semibold text-primary-900">Título</h3>
  <p class="text-primary-700">Contenido de la card</p>
</div>

<!-- Card con fondo oscuro -->
<div class="bg-dark-900 p-6 rounded-lg">
  <h3 class="text-secondary-400 font-bold text-xl mb-2">Título Destacado</h3>
  <p class="text-primary-200">Contenido sobre fondo oscuro</p>
</div>

<!-- Card con borde y sombra -->
<div class="bg-white border border-primary-200 shadow-lg shadow-primary-500/20 p-6 rounded-lg">
  <p class="text-dark-900">Contenido con sombra colorida</p>
</div>
```

### Fondos y Gradientes

```astro
<!-- Fondo sólido oscuro -->
<div class="bg-dark-900 min-h-screen">
  <!-- Contenido -->
</div>

<!-- Gradiente principal (estilo logo) -->
<div class="bg-gradient-to-br from-dark-900 via-blue-900 to-dark-800">
  <!-- Contenido hero -->
</div>

<!-- Gradiente de acento -->
<div class="bg-gradient-to-r from-primary-500 to-accent-400">
  <!-- Banner llamativo -->
</div>

<!-- Gradiente dorado -->
<div class="bg-gradient-to-r from-secondary-400 to-secondary-600">
  <!-- Sección premium -->
</div>
```

### Texto

```astro
<!-- Títulos -->
<h1 class="text-secondary-400 font-bold text-4xl">Título Destacado</h1>
<h2 class="text-primary-600 font-semibold text-2xl">Subtítulo</h2>

<!-- Texto sobre fondo oscuro -->
<p class="text-primary-100">Texto claro sobre fondo oscuro</p>

<!-- Texto sobre fondo claro -->
<p class="text-dark-900">Texto oscuro sobre fondo claro</p>

<!-- Enlaces -->
<a href="#" class="text-primary-500 hover:text-primary-600 underline">
  Enlace
</a>
```

### Badges y Etiquetas

```astro
<!-- Badge primary -->
<span class="bg-primary-500 text-white px-3 py-1 rounded-full text-sm font-semibold">
  Nuevo
</span>

<!-- Badge secondary -->
<span class="bg-secondary-400 text-dark-900 px-3 py-1 rounded-full text-sm font-semibold">
  Premium
</span>

<!-- Badge accent -->
<span class="bg-accent-400 text-dark-900 px-3 py-1 rounded-full text-sm font-semibold">
  En Vivo
</span>

<!-- Badge outline -->
<span class="border-2 border-primary-500 text-primary-600 px-3 py-1 rounded-full text-sm font-semibold">
  Popular
</span>
```

---

## 🌗 Modo Oscuro

La paleta está optimizada para modo oscuro. Usa estos colores para temas oscuros:

```astro
<!-- Fondo oscuro -->
<div class="bg-dark-900 text-white">

  <!-- Títulos en modo oscuro -->
  <h1 class="text-secondary-400">Título Dorado</h1>
  <h2 class="text-primary-300">Subtítulo Cyan Claro</h2>

  <!-- Texto en modo oscuro -->
  <p class="text-primary-100">Texto legible sobre oscuro</p>

  <!-- Cards en modo oscuro -->
  <div class="bg-blue-900 border border-primary-700 p-4 rounded">
    <p class="text-white">Contenido de card oscura</p>
  </div>
</div>
```

---

## ✅ Mejores Prácticas

### DO ✓

1. **Usa Primary para acciones principales:**
   ```astro
   <button class="bg-primary-500 hover:bg-primary-600">Comprar Ahora</button>
   ```

2. **Usa Secondary para destacar títulos:**
   ```astro
   <h1 class="text-secondary-400 font-bold">AMERICA</h1>
   ```

3. **Combina Dark con colores brillantes:**
   ```astro
   <div class="bg-dark-900">
     <span class="text-primary-300">Texto legible</span>
   </div>
   ```

4. **Usa gradientes para heros:**
   ```astro
   <section class="bg-gradient-to-br from-dark-900 via-blue-900 to-dark-800">
     <!-- Hero content -->
   </section>
   ```

5. **Aplica opacidad para efectos sutiles:**
   ```astro
   <div class="shadow-2xl shadow-primary-500/20">
     <!-- Sombra colorida sutil -->
   </div>
   ```

### DON'T ✗

1. **❌ NO uses demasiados colores a la vez:**
   ```astro
   <!-- MAL: Demasiados colores -->
   <div class="bg-primary-500 border-secondary-400 text-accent-300">
     <!-- Sobrecargado -->
   </div>
   ```

2. **❌ NO combines colores con bajo contraste:**
   ```astro
   <!-- MAL: Poco contraste -->
   <p class="bg-primary-400 text-primary-500">Difícil de leer</p>

   <!-- BIEN: Alto contraste -->
   <p class="bg-primary-500 text-white">Fácil de leer</p>
   ```

3. **❌ NO uses colores muy saturados para texto largo:**
   ```astro
   <!-- MAL: Texto largo muy brillante -->
   <p class="text-secondary-400 text-base">
     Párrafo largo y largo... cansa la vista
   </p>

   <!-- BIEN: Colores más sutiles -->
   <p class="text-dark-800">
     Párrafo largo y cómodo de leer
   </p>
   ```

---

## 🎨 Componente de Referencia

Para ver todos los colores visualmente, crea una página de referencia:

```astro
---
// src/pages/colors.astro
import Layout from '../layouts/Layout.astro';
import ColorPalette from '../components/ColorPalette.astro';
---

<Layout title="Paleta de Colores">
  <ColorPalette />
</Layout>
```

Luego visita: `http://localhost:4321/colors`

---

## 🔧 Configuración Técnica

Los colores están definidos en `src/styles/colors.css` usando la sintaxis de Tailwind v4:

```css
@theme {
  --color-primary-500: oklch(64% 0.18 195);
  --color-secondary-400: oklch(77% 0.17 85);
  --color-dark-900: oklch(10% 0.04 250);
  /* ... más colores */
}
```

### Variables CSS Globales

También disponibles como variables CSS:

```css
:root {
  --americaplay-cyan: #06b6d4;
  --americaplay-gold: #fbbf24;
  --americaplay-dark: #0A1628;
  --americaplay-blue: #1e3a8a;
  --americaplay-accent: #22d3ee;
}
```

Uso:
```astro
<div style={`background: var(--americaplay-cyan)`}>
  Contenido
</div>
```

---

## 🎯 Casos de Uso Específicos

### Landing Page Hero

```astro
<section class="min-h-screen bg-gradient-to-br from-dark-900 via-blue-900 to-dark-800 flex items-center justify-center">
  <div class="text-center text-white px-4">
    <h1 class="text-6xl font-bold mb-4">
      <span class="text-secondary-400">America</span>
      <span>Play</span>
    </h1>
    <p class="text-primary-200 text-xl mb-8">
      Tu plataforma de streaming favorita
    </p>
    <button class="bg-primary-500 hover:bg-primary-600 text-white px-8 py-4 rounded-full text-lg font-semibold transition">
      Empezar Ahora
    </button>
  </div>
</section>
```

### Tarjeta de Producto

```astro
<div class="bg-white rounded-lg shadow-xl shadow-primary-500/10 overflow-hidden hover:shadow-2xl transition">
  <div class="h-48 bg-gradient-to-br from-dark-900 to-blue-800"></div>
  <div class="p-6">
    <h3 class="text-xl font-bold text-dark-900 mb-2">Nombre del Producto</h3>
    <p class="text-dark-600 mb-4">Descripción del producto...</p>
    <div class="flex items-center justify-between">
      <span class="text-2xl font-bold text-secondary-500">$99.99</span>
      <button class="bg-primary-500 hover:bg-primary-600 text-white px-6 py-2 rounded-lg transition">
        Comprar
      </button>
    </div>
  </div>
</div>
```

### Barra de Navegación

```astro
<nav class="bg-dark-900 shadow-lg shadow-dark-950/50">
  <div class="container mx-auto px-4 py-4 flex items-center justify-between">
    <div class="text-2xl font-bold">
      <span class="text-secondary-400">America</span>
      <span class="text-white">Play</span>
    </div>
    <div class="flex gap-6">
      <a href="#" class="text-primary-300 hover:text-primary-400 transition">Inicio</a>
      <a href="#" class="text-white hover:text-primary-300 transition">Explorar</a>
      <a href="#" class="text-white hover:text-primary-300 transition">Mi Lista</a>
    </div>
    <button class="bg-primary-500 hover:bg-primary-600 text-white px-6 py-2 rounded-lg transition">
      Suscribirse
    </button>
  </div>
</nav>
```

---

## 📚 Recursos Adicionales

- [Tailwind CSS - Customizing Colors](https://tailwindcss.com/docs/customizing-colors)
- [Tailwind CSS v4 - Theme Configuration](https://tailwindcss.com/docs/theme)
- [OKLCH Color Picker](https://oklch.com/)
- [Color Contrast Checker](https://webaim.org/resources/contrastchecker/)

---

## 🎨 Inspiración del Logo

Esta paleta fue extraída directamente de `public/images/logo.jpeg`, que presenta:
- Fondo azul oscuro profundo (#0A1628)
- Mapa mundial en azul royal
- Hexágonos con líneas cyan brillantes (#22d3ee)
- Botón play en cyan (#06b6d4)
- Texto "AMERICA" en dorado (#fbbf24)
- Texto "PLAY" en blanco

**¡Mantén la coherencia visual usando esta paleta en todo tu proyecto!** 🎨✨
