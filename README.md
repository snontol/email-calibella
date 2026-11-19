# Email Calibella – Cumpleaños de diciembre

Email de campaña para **Calibella**, pastelería creativa y panadería latina de Vitoria-Gasteiz: diseño en Figma, maquetación con MJML y envío desde HubSpot.

**Ver el email:** https://snontol.github.io/email-calibella/
**Diseño en Figma:** https://www.figma.com/design/0YV0BCnOKbEtu9O8tQzgts/Email-Calibella-%E2%80%93-Cumplea%C3%B1os-diciembre?node-id=0-1&t=ObVtErXX8TxAAOKq-1

## Proceso

1. **Diseño en Figma**: marco de 600 px con versión móvil, guía de estilo con variables de color (magenta `#D4178C` con contraste WCAG AA) y estilos de texto.
2. **Maquetación con MJML** (`index.mjml`), compilada a HTML (`index.html`) con tablas, estilos en línea y comentarios condicionales para Outlook.
3. **Pruebas** en Outlook 2013 (Windows) y en el gestor de correo nativo de Android.
4. **Envío desde HubSpot** a un segmento activo, con token de personalización del nombre y enlaces con parámetros UTM.

## Decisiones técnicas

- **Tablas en lugar de flexbox o grid**, porque Outlook para Windows usa el motor de Word y no entiende el CSS moderno.
- **Fuentes de respaldo**: `Fredoka` y `Poppins` con `Arial` como alternativa. En Outlook el diseño se mantiene con Arial (degradación elegante).
- **Botón a prueba de fallos** generado por `mj-button`: se ve aunque las imágenes estén bloqueadas.
- **Columnas responsive**: las tarjetas de producto se apilan por debajo de 480 px.
- **Imágenes en JPG/PNG** con URL absoluta y texto alternativo en todas.
- **Texto de vista previa** definido con `mj-preview`.

## Estructura

```
email-calibella/
├── index.mjml   # código fuente
├── index.html   # HTML compilado para enviar
└── img/         # imágenes del email
```

## Cómo compilarlo

Con la extensión MJML de VS Code: `Ctrl + Shift + P` → **MJML: Export HTML**.
O con Node.js: `npx mjml index.mjml -o index.html`

---

Proyecto de portafolio de **Samuel Nontol** · [nontol.dev](https://snontol.github.io/nontol.dev)
