# 📸 Guía de Gestión de Imágenes - AmericaPlay

Esta guía explica cómo y dónde colocar las imágenes en tu proyecto Astro para obtener el mejor rendimiento.

## 📁 Estructura de Carpetas

```
AmericaPlay/
├── public/
│   └── images/           # ← Imágenes estáticas (sin optimización)
│       └── logo.jpeg
│
└── src/
    └── assets/
        └── images/       # ← Imágenes optimizadas (con procesamiento)
            ├── backgrounds/   # Fondos y banners
            ├── products/      # Imágenes de productos
            ├── team/          # Fotos del equipo
            └── gallery/       # Galerías de imágenes
```

---

## 🎯 ¿Dónde Colocar Cada Tipo de Imagen?

### 📌 `public/images/` - Para imágenes estáticas

**Usar cuando:**
- Logos del sitio
- Favicons
- Imágenes que NO necesitan optimización
- Assets que se referencian desde HTML/CSS directo
- Imágenes de terceros (ads, widgets)

**Características:**
- ✅ Se copian tal cual al build (sin procesamiento)
- ✅ Rutas absolutas simples: `/images/logo.png`
- ✅ Carga rápida sin procesamiento
- ❌ No se optimizan automáticamente
- ❌ No generan versiones responsive

**Ejemplo:**
```astro
<!-- Opción 1: HTML directo -->
<img src="/images/logo.jpeg" alt="Logo" />

<!-- Opción 2: Con componente OptimizedImage -->
<OptimizedImage
  src="/images/logo.jpeg"
  alt="Logo"
  width={200}
  height={200}
/>
```

---

### 🚀 `src/assets/images/` - Para imágenes optimizadas

**Usar cuando:**
- Fotos de productos
- Imágenes de contenido
- Galerías de fotos
- Banners y heroes
- Cualquier imagen que necesite optimización

**Características:**
- ✅ Optimización automática
- ✅ Generación de múltiples tamaños (responsive)
- ✅ Conversión a formatos modernos (WebP, AVIF)
- ✅ Lazy loading automático
- ✅ Mejor rendimiento y SEO

**Ejemplo:**
```astro
---
// 1. Importar la imagen
import productImage from '../assets/images/products/producto-1.jpg';
import OptimizedImage from '../components/OptimizedImage.astro';
---

<!-- 2. Usar con el componente OptimizedImage -->
<OptimizedImage
  src={productImage}
  alt="Producto 1"
  width={800}
  height={600}
  format="webp"
  quality={80}
/>
```

---

## 🧩 Componentes Disponibles

### 1️⃣ `OptimizedImage` - Componente universal para imágenes

**Uso básico:**
```astro
---
import OptimizedImage from '../components/OptimizedImage.astro';
import miImagen from '../assets/images/products/producto.jpg';
---

<OptimizedImage
  src={miImagen}
  alt="Descripción de la imagen"
  width={800}
  height={600}
/>
```

**Props disponibles:**
- `src` (required): Imagen importada o ruta string
- `alt` (required): Texto alternativo
- `width`: Ancho en píxeles
- `height`: Alto en píxeles
- `class`: Clases CSS de Tailwind
- `loading`: 'lazy' (default) o 'eager'
- `format`: 'webp' (default), 'avif', 'jpeg', 'png'
- `quality`: 1-100 (default: 80)

**Ejemplos de uso:**

```astro
<!-- Imagen desde assets/ (optimizada) -->
---
import producto from '../assets/images/products/producto-1.jpg';
---

<OptimizedImage
  src={producto}
  alt="Producto 1"
  width={400}
  height={300}
  class="rounded-lg shadow-xl"
  format="webp"
  quality={85}
/>

<!-- Imagen desde public/ (estática) -->
<OptimizedImage
  src="/images/logo.jpeg"
  alt="Logo"
  width={150}
  height={150}
  class="rounded-full"
/>
```

---

### 2️⃣ `HeroImage` - Componente para banners y secciones hero

**Uso básico:**
```astro
---
import HeroImage from '../components/HeroImage.astro';
import heroBackground from '../assets/images/backgrounds/hero-bg.jpg';
---

<HeroImage
  src={heroBackground}
  alt="Hero background"
  title="¡Bienvenido a AmericaPlay!"
  subtitle="Tu plataforma de streaming favorita"
  height="large"
/>
```

**Props disponibles:**
- `src` (required): Imagen importada o ruta string
- `alt` (required): Texto alternativo
- `title`: Título principal (opcional)
- `subtitle`: Subtítulo (opcional)
- `overlay`: true/false (overlay oscuro)
- `overlayOpacity`: 0-100 (opacidad del overlay)
- `height`: 'small', 'medium', 'large', 'full'
- `position`: 'top', 'center', 'bottom'
- `class`: Clases CSS adicionales

**Ejemplos de uso:**

```astro
<!-- Hero con título y subtítulo -->
<HeroImage
  src={backgroundImage}
  alt="Background"
  title="Tu título aquí"
  subtitle="Tu subtítulo aquí"
  height="full"
  overlay={true}
  overlayOpacity={60}
/>

<!-- Hero con contenido personalizado (usando slot) -->
<HeroImage
  src={backgroundImage}
  alt="Background"
  height="medium"
>
  <div class="text-white text-center">
    <h1 class="text-6xl font-bold mb-4">Contenido Custom</h1>
    <button class="bg-blue-500 px-6 py-3 rounded-lg">
      ¡Empieza Ahora!
    </button>
  </div>
</HeroImage>
```

---

## 💡 Mejores Prácticas

### ✅ **HACER:**

1. **Usar imágenes optimizadas para contenido:**
   ```astro
   import imagen from '../assets/images/productos/producto.jpg';
   <OptimizedImage src={imagen} alt="..." />
   ```

2. **Siempre incluir texto alternativo (alt):**
   ```astro
   <OptimizedImage src={img} alt="Descripción clara y descriptiva" />
   ```

3. **Especificar dimensiones para evitar layout shift:**
   ```astro
   <OptimizedImage src={img} alt="..." width={800} height={600} />
   ```

4. **Usar lazy loading para imágenes below the fold:**
   ```astro
   <OptimizedImage src={img} alt="..." loading="lazy" />
   ```

5. **Organizar imágenes por categoría:**
   ```
   src/assets/images/
   ├── products/     # Fotos de productos
   ├── team/         # Fotos del equipo
   ├── backgrounds/  # Fondos y banners
   └── gallery/      # Galerías
   ```

### ❌ **NO HACER:**

1. **NO usar imágenes gigantes sin optimizar:**
   ```astro
   <!-- ❌ MAL: Imagen de 5MB sin optimizar -->
   <img src="/images/giant-photo.jpg" alt="..." />

   <!-- ✅ BIEN: Imagen optimizada -->
   <OptimizedImage src={optimizedImage} alt="..." quality={80} />
   ```

2. **NO olvidar el texto alternativo:**
   ```astro
   <!-- ❌ MAL -->
   <img src="..." />

   <!-- ✅ BIEN -->
   <OptimizedImage src="..." alt="Descripción clara" />
   ```

3. **NO mezclar imágenes optimizadas en public/:**
   ```
   ❌ public/images/products/product-1.jpg  # Mal ubicado
   ✅ src/assets/images/products/product-1.jpg  # Correcto
   ```

---

## 📊 Comparación: public/ vs assets/

| Aspecto | `public/images/` | `src/assets/images/` |
|---------|------------------|----------------------|
| **Optimización** | ❌ No | ✅ Sí |
| **Formatos modernos** | ❌ No | ✅ WebP, AVIF |
| **Responsive** | ❌ No | ✅ Múltiples tamaños |
| **Lazy loading** | Manual | ✅ Automático |
| **Build time** | ⚡ Rápido | 🐢 Más lento |
| **Tamaño final** | 📦 Grande | 📦 Optimizado |
| **Uso recomendado** | Logos, favicons | Contenido, productos |

---

## 🎨 Ejemplos Completos

### Ejemplo 1: Galería de productos
```astro
---
import OptimizedImage from '../components/OptimizedImage.astro';
import producto1 from '../assets/images/products/producto-1.jpg';
import producto2 from '../assets/images/products/producto-2.jpg';
import producto3 from '../assets/images/products/producto-3.jpg';
---

<div class="grid grid-cols-1 md:grid-cols-3 gap-6">
  <OptimizedImage
    src={producto1}
    alt="Producto 1"
    width={400}
    height={400}
    class="rounded-lg shadow-lg hover:shadow-2xl transition"
  />
  <OptimizedImage
    src={producto2}
    alt="Producto 2"
    width={400}
    height={400}
    class="rounded-lg shadow-lg hover:shadow-2xl transition"
  />
  <OptimizedImage
    src={producto3}
    alt="Producto 3"
    width={400}
    height={400}
    class="rounded-lg shadow-lg hover:shadow-2xl transition"
  />
</div>
```

### Ejemplo 2: Hero con imagen de fondo
```astro
---
import HeroImage from '../components/HeroImage.astro';
import heroBackground from '../assets/images/backgrounds/hero-home.jpg';
---

<HeroImage
  src={heroBackground}
  alt="Background principal"
  title="¡Bienvenido a AmericaPlay!"
  subtitle="Disfruta del mejor contenido en streaming"
  height="full"
  overlay={true}
  overlayOpacity={50}
  position="center"
>
  <button class="mt-8 bg-blue-500 hover:bg-blue-600 text-white px-8 py-4 rounded-full text-lg font-semibold transition">
    Empezar Ahora
  </button>
</HeroImage>
```

### Ejemplo 3: Logo en header
```astro
---
import OptimizedImage from '../components/OptimizedImage.astro';
---

<header class="bg-white shadow-md">
  <nav class="container mx-auto px-4 py-4 flex items-center justify-between">
    <a href="/">
      <OptimizedImage
        src="/images/logo.jpeg"
        alt="AmericaPlay Logo"
        width={120}
        height={40}
        class="h-10 w-auto"
        loading="eager"
      />
    </a>
    <!-- ... resto del nav -->
  </nav>
</header>
```

---

## 🔧 Configuración Avanzada

### Formatos de imagen soportados

Astro puede procesar los siguientes formatos:
- **WebP**: Mejor compresión, soporte amplio
- **AVIF**: Máxima compresión, soporte creciente
- **JPEG**: Universal, buena calidad
- **PNG**: Transparencias, sin pérdida

### Calidad recomendada por uso

- **Imágenes hero/banner**: quality={85-90}
- **Productos**: quality={80-85}
- **Thumbnails**: quality={70-75}
- **Fondos decorativos**: quality={60-70}

---

## 🚀 Rendimiento

Las imágenes optimizadas mejoran:
- ⚡ **Velocidad de carga**: Hasta 70% más rápido
- 📊 **Core Web Vitals**: Mejor LCP y CLS
- 🎯 **SEO**: Google favorece sitios rápidos
- 📱 **Mobile**: Menor consumo de datos

---

## 📚 Recursos Adicionales

- [Documentación oficial de Astro Images](https://docs.astro.build/en/guides/images/)
- [Guía de optimización de imágenes web](https://web.dev/fast/#optimize-your-images)
- [Tailwind CSS - Object Fit/Position](https://tailwindcss.com/docs/object-fit)

---

**¿Preguntas?** Revisa la documentación de Astro o experimenta con los componentes incluidos. ¡Happy coding! 🎉
