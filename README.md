# 3 en Raya (Tres en Línea)

[Español](#español) · [English](#english)

---

## Español

### Índice

- [Descripción](#descripción)
- [Características](#características)
- [Cómo jugar](#cómo-jugar)
- [Niveles de la IA](#niveles-de-la-ia)
- [Instalación](#instalación)
- [Personalización](#personalización)
- [Compatibilidad](#compatibilidad)
- [Estructura del proyecto](#estructura-del-proyecto)
- [Cómo funciona](#cómo-funciona)
- [Licencia](#licencia)

### Descripción

Tres en raya moderno con interfaz web. Está hecho con **HTML, CSS y JavaScript vanilla**: no usa frameworks, ni dependencias, ni proceso de build. Incluye modo **jugador contra jugador** y modo **jugador contra la IA** con tres niveles de dificultad.

El tablero es una cuadrícula de 3 × 3 generada con **CSS Grid**, sobre un fondo con efecto *glassmorphism*, gradientes y animaciones.

### Características

- **Dos modos de juego**: jugador vs jugador y jugador vs IA.
- **Tres niveles de IA**: fácil, medio y difícil.
- **Interfaz glassmorphism** con gradientes y desenfoque (`backdrop-filter`).
- **Efectos**: confeti al ganar y resaltado de la línea ganadora.
- **Modal de bienvenida** para elegir modo y dificultad antes de empezar.
- **Detección de empate** y bloqueo de movimientos inválidos.
- **Diseño responsive** para móvil, tablet y escritorio.
- **Sin instalación**: se abre directamente en el navegador.

### Cómo jugar

**Jugador vs jugador**

1. Elige el modo **PVP** en el modal de bienvenida.
2. Los jugadores se alternan haciendo clic en las casillas.
3. **X** siempre empieza.
4. Gana quien consiga **3 en línea** en horizontal, vertical o diagonal.

**Jugador vs IA**

1. Elige el modo **PVE** y un nivel de dificultad.
2. Tú siempre juegas como **X** y mueves primero.
3. La IA responde automáticamente como **O** con una pausa de 800 ms.
4. El botón de reinicio limpia el tablero y empieza otra partida.

### Niveles de la IA

| Nivel | Comportamiento |
|---|---|
| 🟢 Fácil | Movimientos aleatorios entre las casillas libres |
| 🟡 Medio | Estrategia básica con errores ocasionales |
| 🔴 Difícil | Estrategia óptima y consistente |

La IA del nivel difícil sigue este orden de prioridad:

1. **Ganar** si hay una jugada ganadora disponible.
2. **Bloquear** al jugador humano si va a ganar.
3. Ocupar el **centro** (casilla 4).
4. Ocupar una **esquina** libre.
5. Cualquier casilla libre.

### Instalación

No hace falta instalar nada.

```bash
git clone https://github.com/alberto2005-coder/3-en-raya.git
cd 3-en-raya
```

Después abre `index.html` en el navegador (doble clic o arrastrarlo a la ventana).

Si prefieres servirlo con un servidor local:

```bash
python -m http.server 8000
```

y visita <http://localhost:8000>.

### Personalización

**Colores y formas**: las variables están en `:root` dentro de `styles.css`.

```css
:root {
    --primary-color: #667eea;     /* Color principal */
    --secondary-color: #764ba2;   /* Color secundario */
    --accent-color: #f093fb;      /* Color de acento */
    --success-color: #4ecdc4;     /* Color de éxito */
    --danger-color: #ff6b6b;      /* Color de peligro */
    --border-radius: 15px;        /* Radio de bordes */
}
```

**Dificultad**: la lógica está en `main.js`, en `getRandomMove()`, `getMediumMove()` y `getHardMove()`. `setDifficulty()` guarda el nivel elegido en la variable `aiDifficulty`.

**Tipografía**: se carga **Poppins** desde Google Fonts. Para cambiarla, edita el `<link>` de `index.html`.

### Compatibilidad

- Chrome 88+
- Firefox 94+
- Safari 14+
- Edge 88+
- Móviles y tablets

### Estructura del proyecto

```text
3-en-raya/
├── index.html        # Estructura, modal de bienvenida y tablero
├── main.js           # Estado, turnos, victoria e IA
├── styles.css        # Glassmorphism, grid y animaciones
├── tres-en-raya.png  # Icono / favicon
├── LICENSE
└── README.md
```

### Cómo funciona

- `board` es un array de 9 posiciones; `winCombinations` contiene las 8 combinaciones ganadoras.
- `playerMove()` valida el clic, llama a `makeMove()` y comprueba `checkWin()` y `checkDraw()`.
- `switchPlayer()` alterna entre `X` y `O` y actualiza el indicador de turno.
- En modo PVE, tras el turno humano se programa `aiMove()` con `setTimeout(..., 800)`.
- `checkWin()` recorre `winCombinations` y, si encuentra una línea, la resalta y lanza `createConfetti()`.
- `resetGame()` deja el array vacío y restaura el turno inicial.

### Licencia

Este proyecto se distribuye bajo la **licencia MIT**. Consulta [LICENSE](LICENSE).

---

## English

### Table of contents

- [Overview](#overview)
- [Features](#features)
- [How to play](#how-to-play)
- [AI levels](#ai-levels)
- [Installation](#installation)
- [Customization](#customization)
- [Browser support](#browser-support)
- [Project structure](#project-structure)
- [How it works](#how-it-works)
- [License](#license)

### Overview

A modern tic-tac-toe game with a web interface, built with **plain HTML, CSS and JavaScript**: no frameworks, no dependencies and no build step. It ships a **player vs player** mode and a **player vs AI** mode with three difficulty levels.

The board is a 3 × 3 **CSS Grid** on a *glassmorphism* background with gradients and animations.

### Features

- **Two game modes**: player vs player and player vs AI.
- **Three AI levels**: easy, medium and hard.
- **Glassmorphism UI** with gradients and `backdrop-filter` blur.
- **Effects**: confetti on victory and a highlighted winning line.
- **Welcome modal** to pick mode and difficulty before playing.
- **Draw detection** and rejection of invalid moves.
- **Responsive design** for mobile, tablet and desktop.
- **No installation**: it runs straight from the browser.

### How to play

**Player vs player**

1. Choose **PVP** in the welcome modal.
2. Players take turns clicking cells.
3. **X** always goes first.
4. The first to get **3 in a row** horizontally, vertically or diagonally wins.

**Player vs AI**

1. Choose **PVE** and a difficulty level.
2. You always play as **X** and move first.
3. The AI answers automatically as **O** after an 800 ms delay.
4. The reset button clears the board and starts a new game.

### AI levels

| Level | Behavior |
|---|---|
| 🟢 Easy | Random moves among free cells |
| 🟡 Medium | Basic strategy with occasional mistakes |
| 🔴 Hard | Consistently optimal strategy |

The hard AI follows this priority order:

1. **Win** if a winning move exists.
2. **Block** the human player if they are about to win.
3. Take the **center** (cell 4).
4. Take a free **corner**.
5. Any free cell.

### Installation

Nothing to install.

```bash
git clone https://github.com/alberto2005-coder/3-en-raya.git
cd 3-en-raya
```

Then open `index.html` in your browser (double-click it or drag it into the window).

If you prefer a local server:

```bash
python -m http.server 8000
```

and visit <http://localhost:8000>.

### Customization

**Colors and shapes**: the variables live in `:root` inside `styles.css`.

```css
:root {
    --primary-color: #667eea;     /* Primary color */
    --secondary-color: #764ba2;   /* Secondary color */
    --accent-color: #f093fb;      /* Accent color */
    --success-color: #4ecdc4;     /* Success color */
    --danger-color: #ff6b6b;      /* Danger color */
    --border-radius: 15px;        /* Border radius */
}
```

**Difficulty**: the logic lives in `main.js`, in `getRandomMove()`, `getMediumMove()` and `getHardMove()`. `setDifficulty()` stores the chosen level in `aiDifficulty`.

**Typography**: **Poppins** is loaded from Google Fonts. To change it, edit the `<link>` in `index.html`.

### Browser support

- Chrome 88+
- Firefox 94+
- Safari 14+
- Edge 88+
- Mobile and tablets

### Project structure

```text
3-en-raya/
├── index.html        # Markup, welcome modal and board
├── main.js           # State, turns, win detection and AI
├── styles.css        # Glassmorphism, grid and animations
├── tres-en-raya.png  # Icon / favicon
├── LICENSE
└── README.md
```

### How it works

- `board` is a 9-slot array; `winCombinations` holds the 8 winning lines.
- `playerMove()` validates the click, calls `makeMove()` and checks `checkWin()` and `checkDraw()`.
- `switchPlayer()` alternates `X` and `O` and updates the turn indicator.
- In PVE mode, the human move is followed by `aiMove()` scheduled with `setTimeout(..., 800)`.
- `checkWin()` walks `winCombinations` and, on a match, highlights the line and fires `createConfetti()`.
- `resetGame()` empties the array and restores the starting turn.

### License

This project is released under the **MIT License**. See [LICENSE](LICENSE).
