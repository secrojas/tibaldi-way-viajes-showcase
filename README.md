# ✈️ Tibaldi Way Viajes — Landing Web

> Showcase público del proyecto. El código completo se mantiene en un repositorio privado.

Landing page profesional desarrollada para **Tibaldi Way Viajes**, agencia de turismo internacional ubicada en Mar del Plata, Argentina. El sitio fue diseñado para transmitir confianza, elegancia y experiencia en viajes internacionales.

---

## 📋 Descripción del Proyecto

Desarrollo de una landing web one-page orientada a la captación de consultas para una agencia de turismo especializada en destinos internacionales. El objetivo central fue crear una presencia digital profesional que refleje la identidad de la agencia y facilite el contacto con potenciales clientes.

---

## 🌍 Contexto del Proyecto

**Cliente:** Tibaldi Way Viajes
**Tipo:** Agencia de turismo internacional
**Ubicación:** Mar del Plata, Argentina
**Alcance:** Diseño y desarrollo de landing web one-page

**Objetivos del sitio:**
- Presentar la agencia y sus servicios
- Mostrar destinos internacionales destacados
- Generar consultas y conversiones
- Permitir contacto vía formulario
- Habilitar contacto directo vía WhatsApp

---

## ✨ Características Principales

- 🗺️ Showcase de destinos internacionales
- 📬 Formulario de contacto integrado
- 💬 Botón de contacto directo por WhatsApp
- 📱 Diseño completamente responsive
- ⚡ Optimizado para performance y Core Web Vitals
- 🔍 SEO optimizado con metadatos dinámicos
- 🎨 Diseño minimalista y moderno

---

## 🛠️ Stack Tecnológico

| Tecnología | Uso |
|---|---|
| **Nuxt 3** | Framework principal (SSG/SSR) |
| **Vue 3** | UI reactiva con Composition API |
| **TailwindCSS** | Estilos utilitarios y diseño responsive |

---

## 🏗️ Arquitectura

El proyecto sigue la arquitectura basada en componentes de Nuxt 3, con generación estática del sitio (SSG) para máximo rendimiento y compatibilidad con hosting estático.

```
Cliente (Browser)
      │
      ▼
  Nuxt 3 (SSG)
      │
      ├── Pages (rutas)
      ├── Components (UI reutilizable)
      ├── Assets (estilos, imágenes)
      └── Public (archivos estáticos)
```

La landing es generada como sitio estático mediante `nuxt generate`, lo que permite despliegue en cualquier CDN o servicio de hosting estático con tiempos de carga óptimos.

---

## 📁 Estructura del Proyecto

```
tibaldi-way-viajes/
├── pages/
│   └── index.vue          # Página principal (landing one-page)
├── components/
│   ├── HeroSection.vue    # Sección hero con CTA principal
│   ├── DestinationsGrid.vue
│   ├── ContactForm.vue
│   └── WhatsAppButton.vue
├── assets/
│   ├── css/
│   │   └── main.css       # Estilos globales + directivas Tailwind
│   └── images/            # Imágenes optimizadas
├── public/
│   └── favicon.ico        # Archivos estáticos públicos
└── nuxt.config.ts         # Configuración de Nuxt (SEO, módulos, SSG)
```

**Propósito de cada directorio:**

- **`pages/`** — Define las rutas de la aplicación. Cada archivo `.vue` es una ruta automática.
- **`components/`** — Componentes reutilizables registrados automáticamente por Nuxt.
- **`assets/`** — Recursos procesados por el build (CSS, imágenes que pasan por Vite).
- **`public/`** — Archivos servidos directamente sin procesamiento.
- **`nuxt.config.ts`** — Configuración central: módulos, SEO global, SSG, Tailwind.

---

## 💻 Ejemplos de Código

### Hero Section — Componente Vue 3

```vue
<!-- components/HeroSection.vue -->
<template>
  <section class="relative min-h-screen flex items-center justify-center bg-cover bg-center"
           :style="{ backgroundImage: `url(${heroImage})` }">
    <div class="absolute inset-0 bg-black/50" />
    <div class="relative z-10 text-center text-white px-6 max-w-3xl mx-auto">
      <h1 class="text-5xl font-light tracking-wide mb-4">
        Descubrí el mundo con nosotros
      </h1>
      <p class="text-xl font-light mb-8 text-white/90">
        Viajes internacionales diseñados a tu medida
      </p>
      <a href="#contacto"
         class="inline-block bg-white text-gray-900 px-8 py-3 font-medium tracking-wider hover:bg-gray-100 transition-colors">
        CONSULTANOS
      </a>
    </div>
  </section>
</template>

<script setup>
const heroImage = '/images/hero-bg.jpg'
</script>
```

---

### Configuración Nuxt — SEO y SSG

```typescript
// nuxt.config.ts
export default defineNuxtConfig({
  ssr: true,

  app: {
    head: {
      title: 'Tibaldi Way Viajes | Agencia de Turismo Internacional',
      meta: [
        { name: 'description', content: 'Agencia de turismo internacional en Mar del Plata. Viajes a Europa, Asia, América y más.' },
        { property: 'og:title', content: 'Tibaldi Way Viajes' },
        { property: 'og:type', content: 'website' },
      ],
      link: [
        { rel: 'icon', type: 'image/x-icon', href: '/favicon.ico' }
      ]
    }
  },

  modules: ['@nuxtjs/tailwindcss'],

  nitro: {
    preset: 'static'
  }
})
```

---

### Botón WhatsApp — Componente Reutilizable

```vue
<!-- components/WhatsAppButton.vue -->
<template>
  <a :href="whatsappUrl"
     target="_blank"
     rel="noopener noreferrer"
     class="fixed bottom-6 right-6 z-50 bg-green-500 hover:bg-green-600 text-white p-4 rounded-full shadow-lg transition-all hover:scale-110">
    <IconWhatsapp class="w-6 h-6" />
  </a>
</template>

<script setup>
const phone = '5492235000000'
const message = encodeURIComponent('Hola, me gustaría consultar sobre un viaje.')
const whatsappUrl = `https://wa.me/${phone}?text=${message}`
</script>
```

---

## 🎨 Diseño y Experiencia de Usuario

El diseño sigue una estética **minimalista y moderna**, priorizando:

- **Tipografía ligera** — Uso de pesos `light` y `regular` para transmitir elegancia
- **Paleta neutra** — Blancos, grises y tonos tierra que no compiten con las imágenes de destinos
- **Imágenes protagonistas** — Las fotografías de los destinos son el elemento visual central
- **Jerarquía clara** — El flujo de lectura guía naturalmente hacia los CTAs de contacto
- **Microinteracciones** — Transiciones suaves en hover y scroll para una experiencia fluida

---

## 🔍 SEO y Performance

**SEO:**
- Metadatos estáticos configurados en `nuxt.config.ts`
- Semántica HTML correcta (`h1`, `h2`, landmarks)
- URLs limpias y estructura de contenido optimizada

**Performance:**
- Generación estática (`nuxt generate`) para TTFB mínimo
- Imágenes optimizadas y servidas en formatos modernos
- CSS purificado por TailwindCSS en producción (solo clases utilizadas)
- Sin dependencias JS innecesarias en el bundle

---

## 🔒 Repositorio Privado

> ⚠️ **Este repositorio es únicamente un showcase del proyecto.**
>
> El código fuente completo, incluyendo la configuración de producción, variables de entorno y assets del cliente, se mantiene en un **repositorio privado** por razones de confidencialidad con el cliente.
>
> Este showcase existe con el propósito de documentar el trabajo realizado como parte de mi portfolio técnico.

---

## 👨‍💻 Autor

Desarrollado por **[Tu Nombre]**

- 🌐 Portfolio: [tuportfolio.dev](https://srojasweb.dev)
- 💼 LinkedIn: [linkedin.com/in/tuperfil](https://linkedin.com/in/secrojas)
- 🐙 GitHub: [@tuusuario](https://github.com/secrojas)

---

*Proyecto desarrollado para cliente real — Mar del Plata, Argentina*
