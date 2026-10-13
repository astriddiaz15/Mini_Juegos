# PlayPop! — Mazo de minijuegos

Home page con estética de juguete vintage (tipo Mattel, formas orgánicas, primarios en pastel + blanco) donde eliges una carta de baraja y se abre el juego en la misma pestaña. Todo en HTML, CSS y JavaScript puro, sin frameworks ni dependencias.

## Juegos incluidos

| Carta | Juego | Archivo | Descripción |
|-------|-------|---------|-------------|
| 1 ♥ | Tetris | `juegos/tetris.html` | Apila bloques, borra líneas, sube de nivel |
| 2 ♣ | Snake | `juegos/snake.html` | Come manzanas, récord en `localStorage`, teclado + táctil |
| 3 ♦ | Gato | `juegos/gato.html` | 3 en línea, 2 jugadores o vs CPU |
| 4 ★ | Pin Pon | `juegos/pong.html` | Pong 1P vs IA o 2P local, a 5 puntos, sonidos WebAudio |
| 5 ♠ | Solitario | `juegos/solitario.html` | Klondike clásico con fundaciones A→K |

Cada juego tiene su propia identidad de color y su etiqueta de carta. Todos incluyen animación de serpentinas al ganar y de tristeza al perder (`js/fiesta.js`).

## Secciones del home (`index.html`)

- **Carrusel promo:** la CPU juega sola cada juego en vivo (demos automáticas en `js/demo.js`). Muestra uno a la vez, avanza cada 10 segundos, con flechas, puntos y swipe táctil.
- **Mazo:** 5 cartas estilo baraja (proporción póker, índices en esquina, número de agua al centro) con botón ¡Jugar! debajo de cada una.

## Estructura

```
arcade-mattel/
├── index.html
├── README.md
├── css/
│   ├── style.css    # home: mazo, carrusel, vintage
│   └── juegos.css   # layout compartido + temas por juego
├── js/
│   ├── main.js      # tilt de cartas + carrusel
│   ├── demo.js      # demos CPU del home
│   ├── fiesta.js    # serpentinas / tristeza
│   ├── tetris.js, snake.js, gato.js, pong.js, solitario.js
└── juegos/
    └── tetris.html, snake.html, gato.html, pong.html, solitario.html
```

## Cómo usarlo

1. Clona o descarga este repositorio.
2. Abre `index.html` en tu navegador. No requiere servidor ni build.
3. Elige una carta para jugar. Con `← Volver al mazo` regresas al home.

### Publicarlo en GitHub Pages

1. Sube esta carpeta como repositorio (ej. `playpop-arcade`).
2. En GitHub ve a **Settings → Pages → Deploy from a branch**, elige `main` y carpeta `/ (root)` si el repo contiene solo este proyecto, o `/arcade-mattel` si está dentro de otro repo (en ese caso mueve el contenido a la raíz del repo o configura la carpeta correspondiente).
3. Tu sitio quedará en `https://TU-USUARIO.github.io/NOMBRE-REPO/`.

## Controles rápidos

- **Tetris:** ← → mover, ↓ bajar, ↑/Z/X rotar, Espacio caer.
- **Snake:** flechas/WASD o deslizar el dedo.
- **Gato:** clic/tap en casilla; botón para cambiar entre 2P y vs CPU.
- **Pin Pon:** 1P W/S o mouse; 2P W/S vs ↑/↓.
- **Solitario:** toca para seleccionar y mover; doble toque manda a la fundación.

## Personalización

- Colores por juego en `:root` de `css/style.css` y `css/juegos.css` (`--rojo`, `--verde`, `--azul`, `--amarillo-f`, `--lila`, etc.).
- Intervalo del carrusel en `js/main.js` (línea del `setInterval` de 10000 ms).
- Frase del footer en `index.html` (`.foot`).
