04 - Controles

# Controles

## Descripción de la sección

Los controles de **Vaporlock** permiten al jugador dirigir a Jack Veil, ejecutar ataques, utilizar armas e interactuar con los escenarios mediante las entradas físicas del dispositivo.

El videojuego está orientado principalmente a PC y navegador web, utilizando el teclado y el mouse como medios de entrada principales.

La distribución de controles busca facilitar el aprendizaje de las mecánicas, ofreciendo acciones accesibles y una respuesta inmediata a las instrucciones del jugador. A medida que avanza la aventura, se incorporan nuevas posibilidades de interacción, como el uso del blaster y la máquina de mejoras.

El proyecto utiliza el sistema de entradas de Unity (*Input System*), que permite administrar diferentes acciones y dispositivos. Aunque existen asignaciones para mando, su compatibilidad completa todavía requiere validación.

## Mapa de controles

| Acción | Teclado | Mouse | Control | Táctil |
|---|---|---|---|---|
| Mover | A / D o ← / → | — | Stick izquierdo* | — |
| Trepar cadenas | W / S o ↑ / ↓ | — | Stick izquierdo* | — |
| Saltar | Espacio | — | A / Cruz* | — |
| Dash | Shift izquierdo | — | RB / R1* | — |
| Interactuar | E | — | Cruceta arriba* | — |
| Ataque principal (brazo mecánico) | J o Enter | Clic izquierdo* | X / Cuadrado* | — |
| Uppercut | K | — | Y / Triángulo* | — |
| CrossKick | L | — | B / Círculo* | — |
| RayPunch | I | — | RT / R2* | — |
| Disparar blaster | U | — | LB / L1* | — |
| Usar frasco curativo actual | H | — | Cruceta abajo* | — |
| Abrir máquina de mejoras | E | — | Cruceta arriba* | — |
| Menú de pausa | Por definir | — | Por definir | — |
| Usar adrenalina | Por definir | — | Por definir | — |
| Usar carbón activado | Por definir | — | Por definir | — |

*Las asignaciones marcadas aparecen en los mapas de entrada de Unity, pero su funcionamiento completo en todas las escenas no ha sido verificado. El ataque principal también tiene una entrada táctil configurada, aunque no existe una interfaz táctil completa confirmada.*

### Controles de la máquina de mejoras

La máquina de mejoras utiliza controles específicos mientras su interfaz permanece abierta.

| Acción | Teclado |
|---|---|
| Abrir estación | E |
| Mover selección | WASD o flechas |
| Categoría anterior | Q |
| Categoría siguiente | R o Tab |
| Comprar mejora | E, Enter o Espacio |
| Cerrar estación | Esc o Retroceso |

Mientras la estación permanece abierta, el movimiento y las acciones de combate del personaje se desactivan temporalmente para evitar interacciones accidentales.

### Controles según la progresión

**Nivel 1: Tejados de Metronia:**

El jugador aprende los controles básicos de movimiento, salto, dash y combate mediante el brazo mecánico de Jack.

**Nivel 2: Distrito Industrial:**

Después de derrotar al primer enemigo y recoger el blaster, el jugador desbloquea el ataque a distancia mediante la tecla U.

También puede utilizar la máquina de mejoras y los mecanismos interactivos que aparecen durante el recorrido.

**Nivel 3: El Obelisco:**

El jugador conserva las acciones y herramientas adquiridas en los niveles anteriores, permitiéndole combinar movimientos, ataques físicos y disparos durante el enfrentamiento final.

## Principios de control

Los controles de Vaporlock deben mantener un comportamiento consistente y comprensible para que el jugador pueda concentrarse en superar los desafíos del videojuego.

1. **Consistencia:** Las acciones deben conservar sus controles durante toda la aventura, evitando cambios innecesarios entre niveles.
2. **Simplicidad:** Las mecánicas principales deben ejecutarse mediante botones accesibles, evitando combinaciones excesivamente complejas.
3. **Respuesta inmediata:** Cada acción válida debe producir una respuesta visual o sonora que confirme su ejecución.
4. **Aprendizaje progresivo:** Los controles de nuevas habilidades o herramientas deben introducirse cuando estas se encuentren disponibles.
5. **Claridad:** Las acciones interactivas deben acompañarse de indicadores que permitan identificar cuándo pueden ejecutarse.
6. **Restricciones comprensibles:** Los movimientos y ataques deben respetar sus condiciones de ejecución, como tiempos de recarga, disponibilidad de energía o estados del personaje.
7. **Prevención de errores:** Mientras el jugador utiliza menús o estaciones, las acciones de combate deben bloquearse para evitar movimientos involuntarios.
8. **Accesibilidad:** La distribución debe permitir una experiencia cómoda y ofrecer retroalimentación que no dependa exclusivamente de los colores.

## Reasignación

Actualmente, Vaporlock utiliza una distribución predeterminada de controles mediante el sistema de entradas de Unity.

Aunque el framework permite técnicamente modificar las asignaciones de las acciones, el proyecto todavía no cuenta con una interfaz confirmada para que el jugador cambie las teclas desde el videojuego.

Por el momento, **la reasignación de controles no forma parte de las funcionalidades implementadas**.

En caso de incorporarse posteriormente, el sistema deberá permitir seleccionar nuevas teclas, identificar posibles conflictos entre acciones, restaurar la configuración original y conservar las preferencias del jugador.

La compatibilidad completa con controles externos y dispositivos táctiles también permanece pendiente de validación.

## Entrada y retroalimentación

Cada acción del jugador debe generar una respuesta inmediata que permita reconocer su ejecución y comprender las consecuencias dentro del videojuego.

| Entrada | Retroalimentación |
|---|---|
| Movimiento | Jack se desplaza y reproduce las animaciones correspondientes. |
| Salto | El personaje realiza un impulso vertical y cambia a su animación de salto. |
| Dash | Jack se desplaza rápidamente y ejecuta la animación correspondiente. |
| Escalada | El personaje se sujeta a una cadena y reproduce la animación de ascenso o descenso. |
| Ataque físico | Jack realiza el golpe correspondiente y genera efectos de impacto al alcanzar un enemigo. |
| RayPunch | Se ejecuta el ataque especial y disminuye la energía disponible. |
| Disparo | El blaster genera un proyectil, reproduce los efectos de disparo y actualiza la munición. |
| Interacción | Se activa el mecanismo correspondiente o se informa que todavía no cumple los requisitos. |
| Recolección | El objeto desaparece del escenario y se actualiza el recurso correspondiente. |
| Máquina de mejoras | La interfaz muestra la selección, el costo y la confirmación de adquisición. |
| Botiquín | La salud aumenta y se actualiza su indicador visual. |
| Adrenalina | Se aplica el aumento temporal de movimiento y salto durante cinco segundos. |
| Carbón activado | El indicador de salud muestra el incremento temporal del 20%. |
| Checkpoint | Se muestra una confirmación visual de su activación. |
| Derrota | Se presenta la pantalla correspondiente y se actualizan las oportunidades restantes. |
| Victoria | Se activa la pantalla final y posteriormente los créditos. |

Las respuestas deben combinar animaciones, efectos visuales, sonidos y elementos de interfaz para mantener informado al jugador sobre las acciones realizadas.

Los controles y respuestas relacionados con adrenalina, carbón activado, checkpoints, oportunidades y pantallas finales forman parte del diseño previsto y requieren su implementación correspondiente.

---

**Navegación:** [[00 - Índice]] · ← [[03 - Sistemas]] · [[05 - Progresión]] →