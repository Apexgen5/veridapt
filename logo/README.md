# Veridapt Logo & Branding

This directory contains official Veridapt logos and branding assets.

## Files

- **veridapt-animated.svg** - Animated SVG logo for web use
- **veridapt-static.svg** - Static logo (high resolution)
- **veridapt-icon.svg** - Square icon for favicon/app
- **veridapt-wordmark.svg** - Text-based logo variant
- **veridapt-dark.svg** - Dark mode version
- **veridapt-light.svg** - Light mode version

## Usage Guidelines

### Web
Use animated SVG on landing pages and dashboards:
```html
<img src="/logo/veridapt-animated.svg" alt="Veridapt" />
```

### Print
Use high-resolution static SVG for printed materials:
```
veridapt-static.svg (print-quality)
```

### Favicon
Use the square icon:
```html
<link rel="icon" href="/logo/veridapt-icon.svg" type="image/svg+xml" />
```

### Dark/Light Modes
Switch based on theme:
```html
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="/logo/veridapt-dark.svg" />
  <img src="/logo/veridapt-light.svg" alt="Veridapt" />
</picture>
```

## Color Palette

- **Primary**: #1F2937 (Dark Gray)
- **Accent**: #3B82F6 (Bright Blue)
- **Success**: #10B981 (Emerald)
- **Warning**: #F59E0B (Amber)
- **Error**: #EF4444 (Red)

## Brand Values Reflected

- **Cryptography**: Geometric, precise design
- **Privacy**: Layered visual structure
- **Trust**: Professional, clean aesthetic
- **Innovation**: Modern, dynamic elements
