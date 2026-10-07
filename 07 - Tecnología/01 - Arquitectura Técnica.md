# Arquitectura Técnica

## Descripción de la sección

Explica cómo está construido técnicamente el videojuego y cómo se comunican sus componentes.

## Arquitectura

```text
Entrada
  ↓
Controlador
  ↓
Lógica de juego
  ↓
Sistemas
  ↓
Datos / Persistencia
  ↓
Presentación
```

## Componentes principales

| Componente            | Responsabilidad                                                       | Dependencias            |
| --------------------- | --------------------------------------------------------------------- | ----------------------- |
| Entrada               | Detectar las acciones del jugador mediante teclado o control          | Unity Input System      |
| Control de personajes | Gestionar movimiento, acciones e interacción del personaje            | Entrada, física 2D      |
| Lógica del juego      | Gestionar reglas, estados y comportamiento general del juego          | Sistemas del juego      |
| Sistemas              | Gestionar combate, enemigos, inventario, progresión y otras mecánicas | Lógica del juego, datos |
| Datos y persistencia  | Gestionar información del jugador, progreso y configuración           | Sistemas                |
| Presentación          | Mostrar personajes, escenarios, interfaces, animaciones y efectos     | Datos, sistemas         |

## Comunicación

¿Cómo intercambian información los sistemas?

Los componentes intercambian información mediante scripts y componentes de Unity. Las acciones detectadas por el sistema de entrada son utilizadas por los controladores correspondientes, que interactúan con la lógica y los sistemas del juego.

Los sistemas pueden consultar o modificar datos del juego y comunicar los cambios a los componentes de presentación para actualizar la información mostrada al jugador.

Cuando sea necesario, los componentes utilizarán eventos para comunicar cambios sin crear dependencias directas innecesarias entre sistemas.
## Principios técnicos

- Bajo acoplamiento cuando sea razonable.
- Responsabilidades claras.
- Código mantenible.
- Datos separados de lógica cuando corresponda.
- Evitar dependencias innecesarias.


> **Navegación:** [[00 - Índice]] · ← [[04 - Guardado y Configuración]] · [[02 - Motor y Herramientas]] →
