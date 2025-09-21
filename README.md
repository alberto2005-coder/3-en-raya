# 🎮 Juego de 3 en Raya Moderno

Un juego de tres en raya (tic-tac-toe) moderno y elegante con interfaz web, diseñado con CSS avanzado y JavaScript vanilla. Incluye modo jugador vs jugador y jugador vs IA con diferentes niveles de dificultad.


## ✨ Características

### 🎯 Modos de Juego
- **👥 Jugador vs Jugador**: Modo clásico para dos personas
- **🤖 Jugador vs IA**: Enfréntate a la inteligencia artificial

### 🧠 Inteligencia Artificial
- **🟢 Nivel Fácil**: Movimientos aleatorios, perfecto para principiantes
- **🟡 Nivel Medio**: Estrategia básica con ocasionales movimientos subóptimos
- **🔴 Nivel Difícil**: IA estratégica que prioriza ganar, bloquear y posiciones clave

### 🎨 Interfaz Moderna
- **Diseño Glassmorphism**: Efectos de cristal esmerilado
- **Gradientes Vibrantes**: Colores modernos y atractivos
- **Animaciones Fluidas**: Transiciones suaves en hover y clicks
- **Efectos Especiales**: Confeti al ganar y resaltado de línea ganadora
- **Responsive Design**: Se adapta a móviles y escritorio

### 🚀 Tecnologías Avanzadas
- **CSS Grid**: Para el tablero de juego
- **CSS Custom Properties**: Variables para temas consistentes
- **Backdrop Filter**: Efectos de desenfoque
- **CSS Animations**: Animaciones keyframe personalizadas
- **Google Fonts**: Tipografía moderna (Poppins)

## 📱 Compatibilidad

- ✅ Chrome 88+
- ✅ Firefox 94+
- ✅ Safari 14+
- ✅ Edge 88+
- ✅ Móviles y tablets

## 🛠️ Instalación

1. **Clona o descarga** el repositorio:
```bash
git clone https://github.com/tu-usuario/tres-en-raya.git
```

2. **Abre el archivo** `index.html` en tu navegador favorito

3. **¡Disfruta jugando!** 🎉

No requiere instalación de dependencias ni servidor web.

## 🎮 Cómo Jugar

### Modo Jugador vs Jugador
1. Ambos jugadores se alternan haciendo clic en las casillas
2. **X** siempre comienza primero
3. Gana quien consiga **3 en línea** (horizontal, vertical o diagonal)

### Modo Jugador vs IA
1. **Tú siempre juegas como X** (primer turno)
2. Selecciona tu nivel de dificultad preferido
3. La IA responde automáticamente como **O**
4. ¡Intenta vencer a la máquina!

## 🏗️ Estructura del Proyecto

```
tres-en-raya/
│
├── index.html          # Archivo principal del juego
├── README.md           # Este archivo
└── tres-en-raya.png    # Icono del juego (opcional)
```

## 🎯 Estrategia de la IA

### Algoritmo de Decisión
1. **🥇 Prioridad 1**: Ganar si es posible
2. **🛡️ Prioridad 2**: Bloquear al jugador humano
3. **🎯 Prioridad 3**: Tomar el centro (posición estratégica)
4. **📐 Prioridad 4**: Ocupar esquinas
5. **🔄 Prioridad 5**: Cualquier posición disponible

### Niveles de Dificultad
- **Fácil**: 100% movimientos aleatorios
- **Medio**: Aplica estrategia con cierta probabilidad de errores
- **Difícil**: Estrategia óptima consistente

## 🎨 Personalización

### Variables CSS Personalizables
```css
:root {
    --primary-color: #667eea;      /* Color principal */
    --secondary-color: #764ba2;    /* Color secundario */
    --accent-color: #f093fb;       /* Color de acento */
    --success-color: #4ecdc4;      /* Color de éxito */
    --danger-color: #ff6b6b;       /* Color de peligro */
    --border-radius: 15px;         /* Radio de bordes */
}
```

### Modificar Dificultad de IA
Puedes ajustar la lógica de la IA editando las funciones:
- `getRandomMove()` - Movimientos aleatorios
- `getMediumMove()` - Estrategia intermedia  
- `getHardMove()` - Estrategia avanzada

## 🔧 Funcionalidades Técnicas

- **Estado del Juego**: Gestión completa con JavaScript vanilla
- **Validación de Movimientos**: Previene movimientos inválidos
- **Detección de Victoria**: Algoritmo eficiente para todas las combinaciones
- **Animaciones CSS**: Efectos visuales sin librerías externas
- **Responsive Grid**: Layout que se adapta a cualquier pantalla

## 📈 Versiones

### v2.0 (Actual)
- ➕ Modo IA con 3 niveles de dificultad
- ➕ Interfaz completamente rediseñada
- ➕ Efectos visuales avanzados
- ➕ Design responsive

### v1.0 (Original)
- ✅ Modo básico jugador vs jugador
- ✅ Interfaz simple
- ✅ Funcionalidad core

## 🤝 Contribuir

¡Las contribuciones son bienvenidas! Si quieres mejorar el juego:

1. **Fork** el proyecto
2. Crea una **rama** para tu feature (`git checkout -b feature/AmazingFeature`)
3. **Commit** tus cambios (`git commit -m 'Add some AmazingFeature'`)
4. **Push** a la rama (`git push origin feature/AmazingFeature`)
5. Abre un **Pull Request**

## 💡 Ideas para Futuras Mejoras

- 🏆 Sistema de puntuación y estadísticas
- 🎵 Efectos de sonido
- 🌙 Modo oscuro/claro
- 📊 Historial de partidas
- 🎨 Temas visuales personalizables
- 🔄 Modo online multijugador
- 📱 App móvil con PWA

## 📄 Licencia

Este proyecto está bajo la Licencia MIT. Ver el archivo `LICENSE` para más detalles.

