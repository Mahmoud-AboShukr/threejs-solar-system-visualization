# Solar System Visualization with Three.js

This repository presents a browser-based **Three.js** project that visualizes a simplified Sun–Earth–Moon system using textured spheres, hierarchical orbital motion, and real-time WebGL rendering.

The project is implemented as a single HTML file and uses image textures for the Sun, Earth, and Moon to create an interactive 3D scene directly in the browser.

## Project Overview

The scene models a simple solar system with:

- a textured Sun at the center,
- a textured Earth orbiting the Sun,
- a textured Moon orbiting the Earth,
- point, ambient, and directional lighting,
- continuous animation using `setAnimationLoop`,
- responsive resizing for full-screen browser rendering.

The code uses hierarchical transforms through pivot objects so that:
- the Earth revolves around the Sun,
- the Moon revolves around the Earth,
- the Sun also rotates slowly around its own axis.

## Main Features

- Three.js scene rendered directly in the browser
- Textured Sun, Earth, and Moon using equirectangular image maps
- Hierarchical orbital motion using pivot objects
- Full-screen WebGL canvas
- Real-time animation loop
- Basic lighting setup with:
  - point light at the Sun
  - ambient light
  - directional light
- Responsive rendering on window resize
- Simple and clean single-file structure

## Repository Structure

```text
threejs-solar-system-visualization/
├── solar_system.html
├── README.md
├── WEB_REQUIREMENTS.md
└── textures/
    ├── sunmap.jpg
    ├── EarthMap_2500x1250.jpg
    └── moonmap1k.jpg
```

## Methodology

### 1. Scene Setup

The project initializes a Three.js scene with a black background to simulate space.

### 2. Camera and Renderer

A `PerspectiveCamera` is placed far enough from the origin to capture the Sun and the orbital paths of the Earth and Moon. A `WebGLRenderer` is configured with antialiasing and full-window rendering.

### 3. Lighting

The lighting setup includes:
- a **PointLight** at the Sun position,
- a low-intensity **AmbientLight**,
- a **DirectionalLight** to improve texture visibility.

This gives the textured objects a more readable 3D appearance. fileciteturn2file0

### 4. Textured Planetary Bodies

The project loads three textures with `THREE.TextureLoader()`:
- `sunmap.jpg`
- `EarthMap_2500x1250.jpg`
- `moonmap1k.jpg`

These are applied to sphere meshes representing the Sun, Earth, and Moon. The Sun also uses an emissive material effect to make it appear luminous. fileciteturn2file0

### 5. Orbital Motion

The orbital system is created with pivot objects:
- the Earth mesh is attached to an Earth pivot that rotates around the Sun,
- the Moon mesh is attached to a Moon pivot that rotates around the Earth.

In the uploaded code, the Earth is placed 150 units from the Sun, the Moon is placed 22 units from the Earth, and orbit periods are defined as 60 seconds for the Earth and 5 seconds for the Moon. fileciteturn2file0

### 6. Animation Loop

The animation uses `renderer.setAnimationLoop(...)` to:
- rotate the Earth around the Sun,
- rotate the Moon around the Earth,
- slowly rotate the Sun,
- render the updated scene continuously. fileciteturn2file0

## How to Run

Because the project uses a direct ES module import of Three.js from a CDN, no build step is required.

### Option 1: Open directly
Open `solar_system.html` in a modern browser.

### Option 2: Use a local server
For more reliable texture loading, serve the folder locally, for example with Python:

```bash
python -m http.server 8000
```

Then open:

```text
http://localhost:8000/solar_system.html
```

## Assets

The project expects the following textures inside a `textures/` folder:

- `sunmap.jpg`
- `EarthMap_2500x1250.jpg`
- `moonmap1k.jpg`

## Notes

- The current project uses a CDN import for Three.js rather than npm or Vite.
- For a cleaner public repo, I recommend renaming the HTML title from its current informal wording to something more professional. fileciteturn2file0
- The project is best presented as a **Three.js solar system visualization** rather than a simple class exercise.
- You may later extend it with orbit lines, camera controls, labels, or more planets.

## Possible Improvements

- add `OrbitControls` for mouse interaction,
- add stars or a skybox background,
- include more planets and orbit paths,
- add planet self-rotation and axial tilt,
- convert the project to a modular npm/Vite structure.

## License

This repository is shared as part of a personal portfolio in computer graphics, scientific visualization, and web-based 3D rendering.
