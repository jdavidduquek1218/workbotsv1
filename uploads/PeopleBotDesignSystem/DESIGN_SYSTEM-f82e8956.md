# PeopleBot Design System

Documentación completa del sistema de diseño de la página de landing de PeopleBot.

---

## 🎨 Paleta de Colores

### Colores Primarios
- **Púrpura/Indigo Principal**: `#4F46E5`
  - Usado en: CTA buttons, accents, headings destacados
  - Hover: `#4338CA`
  - Versión transparente: `rgba(79, 70, 229, 0.x)`

- **Verde WhatsApp**: `#25D366`
  - Usado en: Indicadores de status, highlights temáticos
  - Ejemplo: "Demos disponibles" badge, números destacados

### Colores Neutros
- **Fondo Oscuro**: `#09090B`
  - Usado en: Secciones hero, tarjetas oscuras, fondo general

- **Blanco**: `#fff`
  - Usado en: Texto sobre fondo oscuro, elementos claros

- **Fondo Claro**: `#FAFAF8`
  - Usado en: Secciones de contenido general

- **Gris Light**: `#E4E4E7`
  - Usado en: Bordes, separadores

- **Gris Texto**: `#52525B`, `#71717A`
  - Usado en: Texto secundario en navegación

### Transparencias y Opacidades
- `rgba(255,255,255,.5)` - Texto/elementos semidisimulados
- `rgba(255,255,255,.35)` - Texto muy tenue
- `rgba(255,255,255,.65)` - Texto legible pero secundario
- `rgba(255,255,255,.06)` - Bordes sutiles
- `rgba(255,255,255,.07)` - Bordes y separadores
- `rgba(0,0,0,.13)` - Sombras

---

## 🔤 Tipografía

### Familias de Fuentes
- **Headings**: `'Space Grotesk'` - Sans-serif moderna y geométrica
  - Pesos: 700 (bold)
  - Usado en: h1, h2, h3, h4

- **Body**: `'Plus Jakarta Sans'` - Sans-serif legible
  - Pesos: 400 (regular), 500 (medium), 600 (semibold), 700 (bold), 800 (extrabold)
  - Usado en: Párrafos, textos, UI

### Importación
```html
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;600;700&family=Plus+Jakarta+Sans:wght@400;500;600;700;800&display=swap" rel="stylesheet">
```

### Escala Tipográfica (clamp)
- **Hero H1**: `clamp(52px, 7.5vw, 92px)`
  - font-weight: 700
  - line-height: 1.0
  - letter-spacing: -0.03em

- **Sección H2**: `clamp(30px, 4vw, 52px)`
  - font-weight: 700
  - letter-spacing: -0.02em

- **Card H3**: `21px`
  - font-weight: 700
  - line-height: 1.3

- **Párrafos grandes**: `clamp(17px, 2vw, 21px)`
  - font-weight: 400
  - line-height: 1.55

- **Texto UI normal**: `14px` - `16px`
- **Texto pequeño**: `12px` - `13px`
- **Etiquetas uppercase**: `11px`, letter-spacing: `0.2em`

---

## 📐 Sistema de Espaciado

### Padding Estándar
- Secciones: `100px 24px` (vertical), `100px 24px` (horizontal)
- Tarjetas: `44px 40px` o `32px 24px`
- Elementos UI: `16px 32px` (botones), `12px 14px` (nav links)

### Gaps y Espacios
- Grandes: `60px` (entre columnas), `52px` (entre elementos principales)
- Medios: `32px` (contenido), `28px` (headings a descripción)
- Pequeños: `16px` (elementos UI), `14px` (tarjetas), `8px` (iconos)

### Max-width
- Contenedor principal: `1120px`
- Contenedor hero: `840px`

---

## 🎯 Bordes y Radio

### Border Radius
- Cards principales: `18px`
- Botones: `10px`
- Elementos pequeños: `8px`
- Badges: `100px` (pill-shaped)
- Iconos: `10px`

### Bordes (Strokes)
- Estándar: `1px solid rgba(255,255,255,.06)` o `1px solid #E4E4E7`
- Suave: `1px solid rgba(255,255,255,.07)`
- Con color: `1px solid rgba(79,70,229,.25)`

---

## 🖱️ Animaciones

### Keyframes Definidas
```css
@keyframes blink {
  0%, 100% { opacity: 1; }
  50% { opacity: 0.3; }
}

@keyframes fadeUp {
  from { opacity: 0; transform: translateY(20px); }
  to { opacity: 1; transform: translateY(0); }
}

@keyframes floatCard {
  0%, 100% { transform: translateY(0px); }
  50% { transform: translateY(-7px); }
}
```

### Transiciones
- Estándar: `transition: all .25s` o `transition: box-shadow .25s, transform .25s`
- Rápidas: `transition: all .2s` o `.2s`
- Color: `transition: color .25s`
- Backdrop: `transition: all .25s`

### Efectos en Hover
- Cards: `box-shadow: 0 12px 40px rgba(0,0,0,0.13)` + `transform: translateY(-4px)`
- Botones: `transform: translateY(-1px)` + cambio de background
- Links: `color` fade-in

---

## 🔘 Componentes

### Botones

#### Botón Primario (CTA)
```css
background: #4F46E5;
color: #fff;
font-size: 16px;
font-weight: 600;
padding: 16px 32px;
border-radius: 10px;
box-shadow: 0 0 0 1px rgba(79,70,229,.4), 0 4px 24px rgba(79,70,229,.25);
```
- Hover: background `#4338CA`, `transform: translateY(-1px)`

#### Botón Secundario
```css
font-size: 15px;
font-weight: 500;
color: rgba(255,255,255,.4);
```
- Hover: `color: rgba(255,255,255,.8)`

### Badges / Chips
```css
display: inline-flex;
align-items: center;
gap: 8px;
border: 1px solid rgba(255,255,255,.1);
border-radius: 100px;
padding: 6px 18px;
background: rgba(255,255,255,.03);
font-size: 13px;
font-weight: 500;
```

### Cards
- **Dark Card (Hero)**:
  - background: `#09090B`
  - border-radius: `18px`
  - padding: `44px 40px 48px`
  - Posición: `relative;` con pseudoelementos de gradiente

- **Light Card**:
  - background: `#fff`
  - border: `1px solid #E8E8E8`
  - border-radius: `18px`

### Tarjeta de Solución
```css
background: #09090B;
border-radius: 18px;
padding: 44px 40px 48px;
display: flex;
flex-direction: column;
min-height: 500px;
position: relative;
overflow: hidden;
```

---

## 📱 Layout Grid System

### Grid Layouts
- **two-col**: `grid-template-columns: 1fr 1fr; gap: 32px;`
- **three-col**: `grid-template-columns: 1fr 1fr 1fr; gap: 14px;`
- **four-col**: `grid-template-columns: 1fr 1fr 1fr 1fr;`
- **stats-grid**: `grid-template-columns: 1fr 1fr; gap: 0;`
- **reto-grid**: `grid-template-columns: 1fr 1fr;`
- **acc-panel**: `grid-template-columns: 1fr 1fr 1fr;`
- **contact-row**: `grid-template-columns: 1fr 1fr 1fr;`
- **footer-checks**: `grid-template-columns: 1fr 1fr 1fr 1fr;`

### Flexbox
- **nav**: `display: flex; align-items: center; gap: 2px;`
- **hero buttons**: `display: flex; align-items: center; justify-content: center; gap: 16px; flex-wrap: wrap;`

---

## 📦 Sombras

### Drop Shadows
- **Hover cards**: `0 12px 40px rgba(0,0,0,0.13)`
- **Button glow**: `0 0 0 1px rgba(79,70,229,.4), 0 4px 24px rgba(79,70,229,.25)`

---

## 🎬 Navegación

### Barra de Navegación Fija
```css
position: fixed;
top: 0;
left: 0;
right: 0;
z-index: 100;
height: 64px;
display: flex;
align-items: center;
justify-content: space-between;
padding: 0 32px;
background: transparent;
border-bottom: 1px solid transparent;
transition: all .25s;
```

#### Scroll Effect
Al hacer scroll > 80px:
- Background: `rgba(250, 250, 248, 0.96)` con `backdrop-filter: blur(16px)`
- Border: `#E4E4E7`
- Logo text: `#09090B` (desde `#fff`)
- Links: `#52525B` (desde `rgba(255, 255, 255, 0.65)`)

---

## 📱 Responsive Design

### Breakpoint: max-width 768px
```css
.nav-links { display: none !important; }
.nav-toggle { display: flex !important; }
.two-col { grid-template-columns: 1fr !important; gap: 32px !important; }
.three-col { grid-template-columns: 1fr !important; }
.four-col { grid-template-columns: 1fr 1fr !important; }
.stats-grid { grid-template-columns: 1fr 1fr !important; }
.reto-grid { grid-template-columns: 1fr !important; }
.reto-col { 
  padding: 56px 24px !important;
  border-right: none !important;
  border-bottom: 1px solid rgba(255,255,255,.06) !important;
}
section, footer { 
  padding-left: 20px !important;
  padding-right: 20px !important;
}
```

---

## 🎯 Patrones de Diseño

### Fondo con Gradiente Radial
```css
position: absolute;
top: 0;
left: 50%;
transform: translateX(-50%);
width: 1000px;
height: 600px;
background: radial-gradient(ellipse at 50% 0%, rgba(79,70,229,.22) 0%, transparent 60%);
pointer-events: none;
```

### Estado de Animación "Blink" (Indicador Activo)
```css
width: 7px;
height: 7px;
background: #25D366;
border-radius: 50%;
animation: blink 2s infinite;
```

### Overlay de Color Suave
```css
position: absolute;
width: 260px;
height: 260px;
background: radial-gradient(circle, rgba(79,70,229,.28) 0%, transparent 68%);
pointer-events: none;
```

---

## ✨ Secciones Principales

### Hero Section
- Background: `#09090B`
- Padding: `148px 24px 100px`
- Gradiente radial de fondo
- Fade-up animation en contenido

### "El Reto" Section
- Background: `#09090B`
- Grid 2 columnas con borde vertical central
- Padding: `88px 60px` por columna
- Border-right: `1px solid rgba(255,255,255,.06)`

### "La Solución" Section
- Background: `#FAFAF8`
- Grid 3 columnas
- Tarjetas con animaciones hover

### Navegación Mobile
- Position: fixed
- Top: 64px
- Z-index: 99
- Background: `#09090B`
- Flex column layout

---

## 🔧 Utilities

### Scroll Behavior
```css
html { scroll-behavior: smooth; }
```

### Font Smoothing
```css
body { -webkit-font-smoothing: antialiased; }
```

### Reset Base
```css
*, *::before, *::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
```

### Text Wrapping
```css
text-wrap: balance;
```

### Overflow Hidden (Scrolling Mobile)
```css
overflow-x: auto;
-webkit-overflow-scrolling: touch;
scrollbar-width: none;
```

---

## 📋 Checklist de Componentes Disponibles

- [x] Botón primario (CTA)
- [x] Botón secundario
- [x] Badge/Chip con indicador
- [x] Cards oscuras
- [x] Cards claras
- [x] Tarjetas de solución
- [x] Navegación fija con scroll effect
- [x] Navegación mobile
- [x] Sección Hero
- [x] Grid layouts (2, 3, 4 columnas)
- [x] Tabbed content (acordeones)
- [x] Stats display
- [x] Gradientes radiales de fondo
- [x] Animaciones (fadeUp, floatCard, blink)

---

## 🚀 Guía de Uso

### Para Crear Nuevas Secciones
1. Usar el grid system (two-col, three-col, etc.)
2. Mantener la paleta de colores consistente
3. Aplicar padding estándar: `100px 24px` para secciones
4. Usar border-radius: `18px` para cards
5. Implementar transiciones: `transition: all .25s`
6. Mantener responsive con media query en 768px

### Para Crear Componentes
1. Usar Space Grotesk para headings
2. Usar Plus Jakarta Sans para body
3. Aplicar la escala tipográfica con clamp()
4. Seguir la paleta de colores primarios
5. Usar opacidades de la tabla de transparencias

### Animaciones a Usar
- **fadeUp**: Para contenido que entra desde abajo
- **floatCard**: Para elementos que flotan
- **blink**: Para indicadores de estado

---

## 📸 Referencia Visual

El archivo `index.html` contiene todas las implementaciones de estos patrones.

