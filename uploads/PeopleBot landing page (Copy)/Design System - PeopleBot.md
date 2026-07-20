# Sistema de Diseño PeopleBot

## Paleta de Colores

### Primarios
- **Indigo Principal**: `#4F46E5` (botones, CTA, textos destacados)
- **Indigo Oscuro**: `#4338CA` (hover estado botones)
- **Verde WhatsApp**: `#25D366` (accents, stats, énfasis)

### Neutrales
- **Negro Absoluto**: `#09090B` (fondos oscuros, textos principales)
- **Gris Oscuro**: `#52525B` (textos secundarios)
- **Gris Medio**: `#71717A` (textos terciarios)
- **Gris Claro**: `#E4E4E7` (bordes)
- **Blanco Cálido**: `#FAFAF8` (fondos light, fondos body)
- **Blanco Puro**: `#FFFFFF` (textos en fondo oscuro)

### Gradientes
- **Gradient Hero**: `radial-gradient(ellipse at 50% 0%, rgba(79,70,229,.22) 0%, transparent 60%)`
- **Glassmorphism**: `background: rgba(255,255,255,.03); backdrop-filter: blur(16px);`

## Tipografía

### Familias
- **Headlines (h1-h4)**: `Space Grotesk` — geométrica, moderna, confianza
  - Weights: 400, 500, 600, 700
- **Body (p, span, labels)**: `Plus Jakarta Sans` — legible, amigable
  - Weights: 400, 500, 600, 700, 800

### Escala
- **Hero H1**: `clamp(52px, 7.5vw, 92px)` — línea baja 1.0, -0.03em letter-spacing
- **H2 Large**: `clamp(30px, 4vw, 52px)` — línea 1.1, -0.02em letter-spacing
- **H2 Medium**: `clamp(26px, 2.8vw, 38px)` — línea 1.28
- **H3 Card**: `15px` — font-weight 800
- **Body Large**: `clamp(17px, 2vw, 21px)` — línea 1.55
- **Body Regular**: `14px` — línea 1.72
- **Small**: `12px-13px` — línea 2
- **Micro**: `11px` — letter-spacing 0.2em, text-transform uppercase

## Espaciado

### Vertical
- **Hero top padding**: `148px`
- **Section padding**: `100px 24px`
- **Card padding**: `32px 20px 24px` (interior cards)
- **Large section padding**: `88px 60px` (grillas de 2 col)
- **Gap grillas**: `18px` (cards), `12px-14px` (elementos densos)

### Horizontal
- **Max-width**: `1120px` (content container)
- **Margin lateral**: `24px` (mobile), `60px` (desktop large sections)
- **Padding contenedor**: `24px-40px`

## Componentes Base

### Botones
- **CTA Primario**: Fondo `#4F46E5`, color blanco, padding `16px 32px`, border-radius `10px`
  - Hover: background `#4338CA`, transform `translateY(-1px)`
  - Box-shadow: `0 0 0 1px rgba(79,70,229,.4), 0 4px 24px rgba(79,70,229,.25)`
  
- **Botón Secundario**: Fondo `#111`, color blanco, padding `12px 0`, border-radius `100px`
  - Usado en tarjetas de soluciones/bots
  - Font-size `13px`, font-weight `700`

### Cards / Contenedores
- **Card Blanca**: `background: #fff; border: 1px solid #E4E4E7; border-radius: 18px;`
- **Card Oscura**: `background: #09090B; border-radius: 18px;`
- **Card con Hover**: `transition: box-shadow 0.25s, transform 0.25s;` → `box-shadow: 0 12px 40px rgba(0,0,0,0.13); transform: translateY(-4px);`

### Badges/Pills
- **Ronda pequeña**: `border-radius: 100px; padding: 6px 18px;`
- **Con borde sutil**: `border: 1px solid rgba(255,255,255,.1); background: rgba(255,255,255,.03);`

### Grillas
- **2 columnas**: `grid-template-columns: 1fr 1fr;`
- **3 columnas**: `grid-template-columns: 1fr 1fr 1fr;`
- **4 columnas**: `grid-template-columns: repeat(4, 1fr);`
- **3 centrado**: `max-width: 885px; margin: 0 auto;`
- **Gap estándar**: `18px`

## Animaciones

```css
@keyframes blink { 
  0%, 100% { opacity: 1 } 
  50% { opacity: .3 } 
}

@keyframes fadeUp { 
  from { opacity: 0; transform: translateY(20px) } 
  to { opacity: 1; transform: translateY(0) } 
}

@keyframes floatCard { 
  0%, 100% { transform: translateY(0px) } 
  50% { transform: translateY(-7px) } 
}
```

- **Duración fade**: 0.7s ease
- **Duración hover**: 0.25s
- **Duración scroll nav**: 0.25s
- **Duration float cards**: 3.6s–4.6s (variable per card) ease-in-out infinite

## Bordes y Sombras

### Bordes
- **Border sutil**: `1px solid rgba(255,255,255,.06)` (sobre dark)
- **Border card**: `1px solid rgba(0,0,0,.05)` o `1px solid #E4E4E7` (sobre light)
- **Border navegación**: `1px solid transparent` (transición smooth)

### Sombras
- **Card hover**: `0 12px 40px rgba(0,0,0,0.13)`
- **CTA shadow**: `0 0 0 1px rgba(79,70,229,.4), 0 4px 24px rgba(79,70,229,.25)`
- **Orgánicas**: usar `filter: drop-shadow()` para SVG

## Responsive

### Breakpoint
- **768px y menor**: 
  - Stack 2-col a 1-col
  - Stack 4-col a 2x2
  - Stack 3-col a 1-col (con max-width 100%)
  - Hide nav desktop, show hamburger
  - Reduce padding `56px 24px` vs `88px 60px`
  - Font-sizes mantienen clamp()

## Patrones UI

### Navegación
- **Fixed top**: z-index 100, altura 64px
- **Blur glassmorphism**: `backdrop-filter: blur(16px)` cuando scroll > 80px
- **Transición suave**: todos colores en 0.25s
- **Logo dinámico**: blanco en hero, oscuro al hacer scroll

### Hero Section
- **Fondo**: `#09090B`
- **Decoración**: radial gradient en position absolute, pointer-events none
- **Contenedor**: max-width 840px, margin auto
- **Animación entrada**: fadeUp 0.7s both

### Secciones Alternadas
- **Fondo 1**: `#09090B`
- **Fondo 2**: `#FAFAF8`
- **Bordes divisores**: `1px solid rgba(255,255,255,.06)` en dark

## Iconografía

- **SVG inline**: siempre en template
- **Color primario**: `#4F46E5` o blanco según fondo
- **Tamaños**: 16px (micros), 18px (small), 20px (medium), 30px (logo)
- **Stroke**: 1.5–2.2px según escala

---

**Última actualización**: julio 2026  
**Versión**: 1.0  
**Aplicado en**: PeopleBot Landing Page
