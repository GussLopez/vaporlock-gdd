# Controles

## Descripción de la sección

Los controles de **Vaporlock** permiten al jugador dirigir a Jack Veil, ejecutar ataques, utilizar armas e interactuar con los escenarios mediante entradas físicas del dispositivo. El videojuego está orientado principalmente a **PC y navegador web**, utilizando teclado y mouse como medios de entrada principales.

La distribución agrupa movimiento, combate e interacción en teclas fácilmente identificables. La navegación de menús y los comandos para consumibles se integran al mismo esquema sin alterar las acciones principales. El control principal se realiza mediante teclado y mouse.

## Mapa de controles

| Acción | Teclado | Mouse | Control (mando) | Táctil |
|---|---|---|---|---|
| Mover a Jack | `A` / `D` o `←` / `→` | — | — | — |
| Subir o bajar cadenas | `W` / `S` o `↑` / `↓` | — | — | — |
| Saltar / soltarse de una cadena | `Espacio` | — | — | — |
| Dash | `Shift izquierdo` | — | — | — |
| Interactuar | `E` | — | — | — |
| Ataque principal: brazo mecánico / combo | `J` o `Enter` | Clic izquierdo | — | — |
| Uppercut | `K` | — | — | — |
| CrossKick | `L` | — | — | — |
| RayPunch (consume energía) | `I` | — | — | — |
| Disparar blaster | `U` | — | — | — |
| Usar botiquín | `H` | — | — | — |
| Abrir máquina de mejoras | `E`, estando cerca | — | — | — |
| Navegar por máquina de mejoras | `WASD` o flechas | — | — | — |
| Cambiar categoría de mejoras | `Q` (anterior), `R` o `Tab` (siguiente) | — | — | — |
| Comprar mejora seleccionada | `E`, `Enter` o `Espacio` | — | — | — |
| Cerrar máquina de mejoras | `Esc` o `Retroceso` | — | — | — |
| Menú de pausa general | Por definir | — | — | — |
| Usar adrenalina | Por definir | — | — | — |
| Usar carbón activado | Por definir | — | — | — |
| Nueva partida / Continuar | Selección en menú | Selección en menú | — | — |

**Controles según la progresión:** En el Nivel 1 Jack utiliza su brazo mecánico. En el Nivel 2, tras derrotar al primer enemigo y recoger el blaster, se habilita el disparo con `U`. Las demás acciones permanecen disponibles en el Nivel 3.

El esquema de control principal corresponde a teclado y mouse; las entradas de mando y táctiles no forman parte de este mapa.

## Principios de control

1. **Consistencia:** Una misma acción conserva su control durante los diferentes niveles, incluso después de obtener nuevas armas.
2. **Simplicidad:** Las acciones esenciales —mover, saltar, atacar e interactuar— deben poder aprenderse sin combinaciones complejas.
3. **Respuesta inmediata:** Cada entrada válida debe generar movimiento, animación, efecto de sonido, cambio en la interfaz o la respuesta correspondiente.
4. **Disponibilidad progresiva:** Los controles de habilidades o armas todavía no adquiridas no deben ejecutar acciones antes de su desbloqueo.
5. **Prioridad de contexto:** Al interactuar con una estación o abrir un menú, los controles de navegación sustituyen a los de combate para evitar acciones accidentales.
6. **Restricciones comprensibles:** Si una acción está impedida por falta de energía, munición, distancia, recarga o estado del personaje, el jugador debe recibir una señal clara cuando corresponda.
7. **Accesibilidad:** Los indicadores importantes deben ser comprensibles más allá del color; el control debe ser cómodo para sesiones cortas de plataformas y combate.
8. **Coherencia de progresión:** Morir, activar un checkpoint o recuperar una partida no debe cambiar arbitrariamente la distribución de controles.

## Reasignación

Vaporlock utiliza una **distribución predeterminada de controles** que permanece constante durante la partida. La configuración básica no incluye reasignación libre de teclas; las acciones se ejecutan mediante las entradas indicadas en el mapa de controles.

## Entrada y retroalimentación

Las acciones deben generar respuestas coherentes que indiquen al jugador si fueron ejecutadas correctamente y qué efecto tuvieron.

| Entrada del jugador | Retroalimentación esperada |
|---|---|
| Moverse | Desplazamiento inmediato y animaciones de caminar o detenerse. |
| Saltar | Impulso vertical, animación de salto y aterrizaje al tocar una superficie. |
| Dash | Desplazamiento rápido y transición de animación; no se repite hasta concluir la recarga. |
| Trepar cadenas | Animación de escalada y movimiento vertical; al saltar se suelta de la cadena. |
| Ataque con brazo mecánico | Animación y efecto de impacto al golpear a un enemigo; sin daño cuando el ataque falla. |
| RayPunch | Efecto de ataque especial y disminución de energía; no se ejecuta con energía insuficiente. |
| Disparar blaster | Animación y proyectil, daño al impactar y actualización de munición; no se dispara antes de obtener el arma. |
| Interactuar (`E`) | Activación de puertas, elevadores u otros mecanismos, o indicación del requisito de apertura. |
| Comprar mejora | Descuento de tuercas, actualización de atributos y confirmación de compra; bloqueo si faltan recursos. |
| Usar botiquín | Aumento de salud e indicación de consumo, sin superar el máximo permitido. |
| Usar adrenalina | Indicador temporal del aumento de movilidad durante cinco segundos y retorno posterior a valores normales. |
| Usar carbón activado | Visualización de la salud adicional; desaparición del beneficio al agotarse o morir. |
| Activar checkpoint | Señal visual de activación y registro del nuevo punto de reaparición. |
| Abrir menú / pantalla de derrota | Cambio de interfaz y bloqueo de comandos de movimiento o combate mientras corresponda. |
| Continuar partida | Recuperación de nivel, recursos, equipo y progreso desde datos guardados válidos. |

La retroalimentación debe utilizar una combinación de **animaciones, efectos sonoros, indicadores visuales y mensajes breves**.

> **Navegación:** [[00 - Índice]] · ← [[03 - Sistemas]] · [[05 - Progresión]] →
