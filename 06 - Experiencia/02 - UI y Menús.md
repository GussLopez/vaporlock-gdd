	# UI y Menús

## Descripción de la sección

Define la estructura funcional de las interfaces y menús.

## Mapa de navegación

```text
Menú principal
├── Nueva partida
├── Continuar
|-- Ayuda
├── Configuración
│   ├── Audio
│   ├── Video
│   ├── Controles
│   └── Accesibilidad
└── Salir
```

## Pantallas

### Pantalla

**Propósito:** El propósito es brindar asistencia y ayuda al jugador cuando no sabe como usar los controles y el mismo da consejos de como hacer tales acciones. en la pantalla muestra explicaciones que facilitan el aprendizaje y mecánica del videojuego

**Elementos:**
- **Título:** Identifica la pantalla como la sección de ayuda.

- **Instrucciones:** Explican cómo utilizar los controles del videojuego.

- **Consejos:** Proporcionan recomendaciones para realizar acciones y superar posibles dificultades.

- **Botón de regresar:** Permite volver a la pantalla anterior o al menú principal.

**Acciones disponibles:**

- Consultar las instrucciones de los controles.
- Leer consejos sobre las mecánicas y acciones del videojuego.
- Regresar al menú anterior mediante el botón correspondiente

**Estados:**

- **Visible:** La pantalla de ayuda se encuentra abierta y muestra las instrucciones disponibles.
- **Inactiva:** La pantalla de ayuda está cerrada y el jugador se encuentra en otra sección del videojuego.

**Transiciones:**

- **Menú principal → Pantalla de ayuda:** El jugador selecciona la opción de ayuda.
- **Pantalla de ayuda → Consulta de instrucciones:** El jugador revisa los controles y consejos disponibles.
- **Pantalla de ayuda → Menú principal:** El jugador selecciona el botón para regresar al menú
  **Pantalla de ayuda → Pantalla anterior:** El jugador cierra la ayuda y vuelve a la sección desde la que accedió
## Confirmaciones

Documenta acciones destructivas o irreversibles y cómo se confirman.
*Propósito:* Evitar que el jugador realice acciones por accidente que puedan provocar la pérdida de su progreso o interrumpir su partida.

**Salir del juego:** Se solicita una confirmación antes de cerrar el videojuego.
*Reiniciar partida:* Se muestra un mensaje de advertencia para confirmar si el jugador desea comenzar nuevamente y perder el progreso actual.

**Regresar al menú principal:** Si el jugador tiene una partida en curso, se le pregunta si desea abandonar la partida actual.


> **Navegación:** [[00 - Índice]] · ← [[01 - UX y Flujo del Jugador]] · [[03 - Accesibilidad]] →
