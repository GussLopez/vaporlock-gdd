# Interfaz Visual

## Descripción de la sección

Documenta la información que el juego muestra al jugador y las reglas visuales de la interfaz.

## HUD

Elementos:

- **Vida (Salud de Jack):** Representada por una barra segmentada con fluido azul cian o verde. Al recibir daño, el segmento perdido parpadea en Resalte rojo.
- **Energía (Presión de Vapor):** Medidor estilo manómetro con una aguja metálica. Almacena la presión necesaria para realizar impulsos/esquivas (dash) y habilidades especiales de las prótesis mecánicas.
- **Munición:** Contador numérico en la esquina del HUD junto al icono del arma/brazo cargador de Jack.
- **Objetivo:** Texto breve e intuitivo ubicado en la parte superior derecha (ej. "Llega a los Tejados de Metronia"), que aparece solo al cambiar de misión o pulsar el botón de mapa/pausa.
- **Recursos:** Contador de engranajes y componentes metálicos recolectados para la Máquina de Mejoras, ubicado justo debajo del HUD de vida.
- **Indicadores contextuales:** Iconos flotantes sobre el mundo en S (ej. un botón interactivo o Borde dorado) que aparecen cuando Jack está cerca de una palanca, una puerta o la Bandera / Checkpoint.

## Jerarquía visual

¿Qué información debe verse primero, segundo y tercero?

- **Primera prioridad (Atención inmediata):** Barra de vida del jugador, medidor de vapor/energía y alertas de daño crítico o trampas en Resalte rojo.
- **Segunda prioridad (Acción táctica):** Cantidad de munición, cooldowns de habilidades e indicadores contextuales interactivos en el entorno.
- **Tercera prioridad (Consulta/Pasiva):** Contador de recursos acumulados y texto de objetivo actual.
## Estados

Documenta estados normales, advertencias, daño, éxito, error y bloqueo.

## Convenciones

- **Tipografía:** Fuente en Aseprite legible, con estilo retro-industrial (ej. Press Start 2P, Monofett o Silkscreen).
- **Iconografía:** Pictogramas simples en píxel art (un corazón/tuerca para vida, una nube de vapor para energía, una bala/proyectil para munición).
- **Tamaños mínimos:** Altura mínima de texto de $8\text{ px}$ en pantalla para legibilidad; botones e iconos interactivos de $32 \times 32\text{ px}$.
- **Contraste:** Todo texto o icono sobre la pantalla de juego lleva un borde fino en Contorno oscuro o un fondo semitransparente en Sombra profunda para garantizar lectura sobre cualquier fondo.
- **Animaciones:** Transiciones rápidas de menús (100–150 ms) mediante deslices de placas metálicas y efectos de escape de vapor al abrir/cerrar pantallas.

## Pantallas

- **Menú principal:** Fondo animado con la silueta de Metronia y chimeneas soltando vapor. Opciones: Jugar / Cargar Partida, Configuración, Créditos y Salir.

- **Pausa:** Oscurece la pantalla de juego con un panel central de acero y cobre. Opciones: Reanudar, Opciones, Reiniciar Checkpoint y Menú Principal.

- **Configuración:** Ajustes divididos en pestañas metálicas: Audio (música, SFX), Controles (mapeo de botones) y Video (resolución, modo ventana, V-Sync).

- **Inventario / Máquina de Mejoras:** Interfaz estilo esquema/plano técnico del cuerpo de Jack. Permite asignar componentes recolectados para mejorar el brazo mecánico, las piernas o el tanque de vapor.

- **Mapa:** Vista de plano esquemático de los sectores descubiertos del nivel, mostrando la ubicación actual de Jack y el punto de la `Bandera / Checkpoint.

- **Victoria / Gano (Nivel o Juego completado):** Muestra el resumen del tiempo de nivel, componentes recolectados y enemigos derrotados sobre una placa dorada triunfal.

- **Murió / Derrota (Game Over):** Pantalla en tonos rojos y gris azabache con humo flotando. Muestra las opciones: Reintentar desde Checkpoint o Salir al Menú.+


> **Navegación:** [[00 - Índice]] · ← [[03 - Entornos]] · [[05 - Audio y Música]] →
