# PeopleBot Design System - Implementation Guide

Guía práctica para implementar el sistema de diseño de PeopleBot en nuevos proyectos.

---

## 🚀 Quick Start

### 1. Importar los archivos CSS

```html
<head>
  <!-- Google Fonts -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin="anonymous">
  <link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;600;700&family=Plus+Jakarta+Sans:wght@400;500;600;700;800&display=swap" rel="stylesheet">

  <!-- Design System CSS -->
  <link rel="stylesheet" href="css/design-tokens.css">
  <link rel="stylesheet" href="css/components.css">
  <link rel="stylesheet" href="css/utilities.css">
</head>
```

### 2. Base HTML Reset

```html
<style>
  *, *::before, *::after {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }
  html { scroll-behavior: smooth; }
  body {
    font-family: var(--font-body);
    background: var(--color-light-bg);
    color: var(--color-dark-bg);
    -webkit-font-smoothing: antialiased;
  }
  h1, h2, h3, h4 {
    font-family: var(--font-heading);
  }
</style>
```

---

## 🎨 Usar Variables CSS

### Colores

```html
<!-- Texto primario -->
<p style="color: var(--color-primary);">Texto en púrpura</p>

<!-- Fondo oscuro -->
<section style="background: var(--color-dark-bg);">...</section>

<!-- Texto muted -->
<p style="color: var(--color-white-opacity-45);">Texto tenue</p>

<!-- Accent verde -->
<span style="color: var(--color-accent-green);">Destacado WhatsApp</span>
```

### Tipografía

```html
<!-- Headings -->
<h1 style="
  font-size: var(--font-size-h1);
  font-weight: var(--font-weight-bold);
  line-height: var(--line-height-tight);
">Título Principal</h1>

<!-- Párrafos -->
<p style="
  font-size: var(--font-size-p-large);
  line-height: var(--line-height-relaxed);
">Párrafo descriptivo</p>

<!-- Labels -->
<span style="
  font-size: var(--font-size-label-uppercase);
  font-weight: var(--font-weight-bold);
  letter-spacing: var(--letter-spacing-widest);
  text-transform: uppercase;
">Label</span>
```

### Espaciado

```html
<!-- Padding uniforme -->
<div style="padding: var(--spacing-xl);">Contenido</div>

<!-- Padding horizontal -->
<div style="padding: 0 var(--spacing-lg);">Contenido</div>

<!-- Margin bottom -->
<div style="margin-bottom: var(--spacing-2xl);">Elemento</div>

<!-- Gap en flex -->
<div style="display: flex; gap: var(--spacing-md);">Elementos</div>
```

---

## 🔧 Usar Clases CSS

### Botones

```html
<!-- Botón Primario -->
<button class="btn btn-primary">Agendar Demo</button>

<!-- Botón Secundario -->
<a href="#" class="btn btn-secondary">Ver Demo</a>

<!-- Botón Pequeño -->
<button class="btn btn-primary btn-sm">Compacto</button>
```

### Tarjetas

```html
<!-- Card Oscura -->
<div class="card card-dark">
  <div class="icon-box">
    <svg>...</svg>
  </div>
  <h3>Título</h3>
  <p>Descripción</p>
</div>

<!-- Card Clara -->
<div class="card card-light">
  Contenido
</div>

<!-- Card con Hover -->
<div class="card card-dark card-hover">
  Clickeable
</div>
```

### Grids

```html
<!-- 2 Columnas -->
<div class="grid-2col">
  <div>Columna 1</div>
  <div>Columna 2</div>
</div>

<!-- 3 Columnas -->
<div class="grid-3col">
  <div>Col 1</div>
  <div>Col 2</div>
  <div>Col 3</div>
</div>

<!-- 4 Columnas -->
<div class="grid-4col">
  <div>Col 1</div>
  <div>Col 2</div>
  <div>Col 3</div>
  <div>Col 4</div>
</div>
```

### Badges

```html
<!-- Badge con indicador -->
<div class="badge">
  <div class="badge-dot"></div>
  <span>Demos disponibles</span>
</div>
```

### Layouts

```html
<!-- Flex Center -->
<div class="flex-center">Centrado</div>

<!-- Flex Between -->
<div class="flex-between">
  <div>Izquierda</div>
  <div>Derecha</div>
</div>

<!-- Flex Column -->
<div class="flex-col gap-lg">
  <div>Item 1</div>
  <div>Item 2</div>
</div>
```

---

## 📐 Patrones Comunes

### Sección Hero

```html
<section class="section-dark py-7xl px-lg">
  <div class="section-inner">
    <div class="gradient-radial-hero" style="bottom: auto;"></div>
    
    <div class="text-center animate-fade-up">
      <div class="badge mb-2xl m-auto">
        <div class="badge-dot"></div>
        <span>Nuevo · Fecha actual</span>
      </div>
      
      <h1 class="mb-lg text-white">Tu título principal</h1>
      <p class="text-large text-muted-light mb-4xl">
        Descripción convincente
      </p>
      
      <div class="flex-center gap-lg flex-wrap">
        <button class="btn btn-primary">Acción Principal</button>
        <button class="btn btn-secondary">Acción Secundaria</button>
      </div>
    </div>
  </div>
</section>
```

### Sección de Contenido

```html
<section class="section-light py-6xl px-lg">
  <div class="section-inner">
    <div class="mb-4xl">
      <span class="text-label text-primary mb-md">Sección</span>
      <h2 class="text-white">Título de sección</h2>
    </div>
    
    <div class="grid-3col">
      <div class="card card-dark card-hover">
        <div class="icon-box">
          <svg>...</svg>
        </div>
        <h3 class="mb-md">Característica 1</h3>
        <p class="text-small text-muted-light">Descripción</p>
      </div>
      <!-- Más cards... -->
    </div>
  </div>
</section>
```

### Navegación

```html
<nav class="nav-main">
  <a href="/" class="font-heading font-bold text-white">Logo</a>
  
  <div class="nav-links">
    <a href="#section" class="nav-link">Link 1</a>
    <a href="#section" class="nav-link">Link 2</a>
    <a href="#cta" class="nav-link nav-link-cta">CTA</a>
  </div>
  
  <button class="nav-toggle" onclick="toggleNav()">
    <span class="hamburger-line"></span>
    <span class="hamburger-line"></span>
    <span class="hamburger-line"></span>
  </button>
</nav>

<!-- Mobile Nav -->
<div class="nav-mobile">
  <a href="#section" class="nav-mobile-link">Link 1</a>
  <a href="#section" class="nav-mobile-link">Link 2</a>
  <a href="#cta" class="btn btn-primary w-full">CTA</a>
</div>
```

### Gradientes de Fondo

```html
<!-- Hero Gradient -->
<div class="gradient-radial-hero"></div>

<!-- Accent Gradient (grande) -->
<div class="gradient-radial-accent" style="bottom: -60px; left: -60px;"></div>

<!-- Accent Gradient (pequeño) -->
<div class="gradient-radial-accent-sm" style="top: -30px; right: -30px;"></div>
```

---

## 🎬 Animaciones

### En HTML

```html
<!-- Fade Up Animation -->
<div class="animate-fade-up">
  Contenido que aparece
</div>

<!-- Float Animation -->
<div class="animate-float">
  Elemento flotante
</div>

<!-- Blink Animation -->
<div class="animate-blink">
  Elemento que parpadea
</div>
```

### En CSS Personalizado

```css
.mi-animacion {
  animation: fadeUp 0.7s both;
}

.otro-elemento {
  animation: floatCard 0.6s ease-in-out infinite;
}
```

---

## 🎯 Estados de Hover

### Botones

```html
<!-- Automático con clase btn -->
<button class="btn btn-primary">
  Automáticamente tiene hover
</button>
```

### Cards

```html
<!-- Automático con clase card-hover -->
<div class="card card-dark card-hover">
  Se eleva al hover
</div>
```

### Links Personalizados

```html
<a href="#" class="hover-lift">
  Se eleva al pasar mouse
</a>

<a href="#" class="hover-text-primary">
  Cambia color al hover
</a>
```

---

## 📱 Responsive

Todos los componentes incluyen media queries para pantallas pequeñas (max-width: 768px).

### Clases Responsivas

```html
<!-- Ocultar en móvil -->
<div class="md-hidden">
  Solo desktop
</div>

<!-- Mostrar solo en móvil -->
<div class="hidden md-flex">
  Solo móvil
</div>

<!-- Grid responsivo -->
<div class="grid-3col">
  <!-- Automáticamente 1 columna en móvil -->
</div>
```

### Personalización

Si necesitas lógica responsiva personalizada:

```javascript
function toggleNav() {
  const nav = document.getElementById('navMobile');
  nav.style.display = nav.style.display === 'flex' ? 'none' : 'flex';
}

window.addEventListener('scroll', function() {
  const nav = document.getElementById('mainNav');
  nav.classList.toggle('scrolled', window.scrollY > 80);
});
```

---

## 🎨 Personalización

### Cambiar Colores

Sobrescribe las variables en tu CSS:

```css
:root {
  --color-primary: #tu-color;
  --color-accent-green: #tu-verde;
  --color-dark-bg: #tu-oscuro;
}
```

### Cambiar Tipografía

```css
:root {
  --font-heading: 'Tu Font', sans-serif;
  --font-body: 'Tu Font', sans-serif;
}
```

### Ajustar Espaciado

```css
:root {
  --spacing-lg: 28px;
  --spacing-xl: 36px;
}
```

---

## ✅ Checklist para Nuevas Secciones

- [ ] Importar CSS design system
- [ ] Usar variables CSS para colores y tipografía
- [ ] Aplicar grid system (grid-2col, grid-3col, etc.)
- [ ] Usar clases de componentes (btn, card, badge)
- [ ] Implementar transiciones (`transition-normal`)
- [ ] Agregar animaciones si es apropiado
- [ ] Verificar responsive (768px breakpoint)
- [ ] Probar hover states
- [ ] Validar contraste de colores
- [ ] Revisar accesibilidad

---

## 🔍 Debugging

### Verificar que los tokens se carguen

```javascript
console.log(getComputedStyle(document.documentElement).getPropertyValue('--color-primary'));
// Debe mostrar: #4F46E5
```

### Verificar clases

```javascript
// Verificar que la clase existe
console.log(document.querySelector('.btn')?.classList);
```

### Problemas Comunes

| Problema | Solución |
|----------|----------|
| Colores no aplican | Verificar orden de importación de CSS |
| Tipografía diferente | Asegurar que Google Fonts esté cargada |
| Responsive no funciona | Verificar viewport meta tag |
| Animaciones entrecortadas | Reducir complejidad de animaciones |
| Z-index incorrecto | Usar clases z-nav, z-nav-mobile |

---

## 📚 Recursos

- `DESIGN_SYSTEM.md` - Documentación completa del sistema
- `css/design-tokens.css` - Variables CSS y animaciones
- `css/components.css` - Componentes reutilizables
- `css/utilities.css` - Clases utilitarias
- `index.html` - Ejemplo de implementación completa

---

## 🤝 Contribuir

Para agregar nuevos componentes o mejorar el sistema:

1. Documentar en `DESIGN_SYSTEM.md`
2. Implementar en archivos CSS correspondientes
3. Crear ejemplo en `index.html`
4. Actualizar este guide si es necesario

