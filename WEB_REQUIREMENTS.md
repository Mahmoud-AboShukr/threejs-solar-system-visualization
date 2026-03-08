# Web Requirements

## Runtime
- A modern web browser with WebGL support
- Internet connection for loading Three.js from the CDN import in `solar_system.html`

## Project Files
The project expects:

- `solar_system.html`
- `textures/sunmap.jpg`
- `textures/EarthMap_2500x1250.jpg`
- `textures/moonmap1k.jpg`

## External Dependency
The HTML file imports Three.js directly from:

- `https://unpkg.com/three@0.174.0/build/three.module.min.js`

## Notes
- No npm install step is required in the current version.
- No build tool is required.
- For more robust local execution, serve the project with a small local HTTP server instead of opening the HTML file directly.
