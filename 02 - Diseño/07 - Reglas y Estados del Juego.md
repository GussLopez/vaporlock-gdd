# Reglas y Estados del Juego

## Descripción de la sección

Los estados y las reglas globales de **Vaporlock** determinan cómo se comporta el videojuego en cada momento, qué acciones puede realizar el jugador y bajo qué condiciones cambia de una pantalla, nivel o situación a otra.

El juego sigue el recorrido de Jack Veil por los Tejados de Metronia, el Distrito Industrial y El Obelisco. A lo largo de la aventura, el jugador combate, supera obstáculos, activa mecanismos y administra su salud, recursos y oportunidades hasta enfrentarse a Lucius Corr.

El recorrido comienza con la presentación de Jack Veil y se desarrolla a través de los tres niveles. Los estados de menú, carga, partida, pausa, derrota, reaparición, Game Over, victoria y créditos organizan el flujo completo del videojuego.

## Estados principales

- **Menú principal:** Pantalla de entrada desde la que el jugador puede iniciar una nueva partida o continuar un progreso guardado. La opción Continuar solo debe habilitarse si existe una partida válida.
- **Carga:** Estado temporal que prepara la escena, los datos guardados y los recursos necesarios antes de permitir el control de Jack.
- **Presentación inicial:** Breve secuencia de introducción de Jack Veil antes del primer nivel.
- **Jugando:** Estado principal de la aventura. El jugador puede moverse, combatir, recoger recursos, activar mecanismos y cumplir los objetivos del nivel.
- **Interacción con estación de mejoras:** Estado de interfaz dentro de la partida en el que se muestran las dos mejoras disponibles. Las acciones de movimiento y combate quedan temporalmente bloqueadas mientras se utiliza la estación.
- **Pausa:** Estado que suspende temporalmente el desarrollo normal de la partida y permite reanudarla o acceder a las opciones disponibles.
- **Derrota:** Estado activado al llegar la salud de Jack a cero. Se presenta la derrota y se descuenta una oportunidad, una sola vez por muerte.
- **Reaparición:** Si quedan oportunidades, el personaje regresa al último checkpoint válido, recuperando la salud normal y sin los efectos temporales que deban eliminarse al morir.
- **Game Over:** Se alcanza cuando Jack muere y no quedan oportunidades para reaparecer. El jugador debe regresar al menú principal.
- **Victoria:** Se activa tras cumplir el objetivo final y derrotar a Lucius Corr en El Obelisco. Se registran el resultado de la partida y las estadísticas de la partida.
- **Créditos:** Pantalla final que se presenta después de la victoria y cierra la experiencia.

Los estados **Derrota** y **Game Over** son diferentes: la derrota corresponde a una muerte individual; Game Over significa que ya no quedan oportunidades para reanudar el intento desde un checkpoint.

## Transiciones

| Estado origen | Evento | Estado destino | Condición |
|---|---|---|---|
| Inicio | Ejecutar Vaporlock | Menú principal | El juego inicia correctamente. |
| Menú principal | Seleccionar Nueva partida | Carga | Se inicia una partida con progreso nuevo. |
| Menú principal | Seleccionar Continuar partida | Carga | Existe un guardado válido que puede recuperarse. |
| Carga | Finalizar la preparación inicial | Presentación inicial o Jugando | La escena y los datos están listos; presentación según el tipo de partida. |
| Presentación inicial | Finalizar secuencia | Jugando | Se activa el control de Jack en el nivel correspondiente. |
| Jugando | Abrir estación de mejoras | Interacción con estación de mejoras | Jack está junto a la estación y puede interactuar. |
| Interacción con estación de mejoras | Cerrar interfaz | Jugando | Se cierra la estación y se restauran los controles normales. |
| Jugando | Solicitar pausa | Pausa | No existe otra pantalla bloqueante activa. |
| Pausa | Reanudar | Jugando | Se cierra la pausa. |
| Jugando | Salud de Jack llega a cero | Derrota | La muerte no ha sido procesada previamente. |
| Derrota | Descontar oportunidad y continuar | Reaparición | Queda al menos una oportunidad. |
| Reaparición | Restaurar el personaje | Jugando | Se posiciona a Jack en el checkpoint válido. |
| Derrota | Descontar última oportunidad | Game Over | El contador de oportunidades llega a cero. |
| Game Over | Volver al menú | Menú principal | Finaliza el intento actual. |
| Jugando — Nivel 1 | Alcanzar la salida industrial | Carga | Se eliminaron los enemigos obligatorios y la salida está habilitada. |
| Jugando — Nivel 2 | Alcanzar la salida al Obelisco | Carga | Se destruyeron los tres tanques industriales. |
| Carga | Completar cambio de nivel | Jugando | Se restaura el estado permanente y se inicia el siguiente escenario. |
| Jugando — Nivel 3 | Derrotar a Lucius Corr | Victoria | Se cumplen las condiciones del combate final. |
| Victoria | Finalizar secuencia de victoria | Créditos | Se registraron el resultado y las estadísticas correspondientes. |
| Créditos | Regresar al menú | Menú principal | Termina la presentación final. |

**Continuidad:** La presentación inicial se reproduce al comenzar una nueva partida; al continuar una partida se restablece directamente el progreso guardado para no reiniciar involuntariamente la aventura.

## Reglas globales

1. **Inicio y continuidad:** Una nueva partida establece el progreso inicial de Jack. Continuar recupera una partida válida; la ausencia de guardado impide utilizar esa opción.
2. **Control según estado:** Las acciones de movimiento, combate e interacción solo se permiten cuando el estado activo lo autoriza. La pausa, carga, derrota y pantallas finales deben impedir entradas de combate accidentales.
3. **Salud y derrota:** Cuando la salud llega a cero, Jack muere y se procesa una sola pérdida de oportunidad, independientemente de cuántos impactos ocurran en ese instante.
4. **Reaparición:** Si quedan oportunidades, Jack vuelve al último checkpoint activado o, si no existe, al inicio válido del nivel. Reaparece con salud normal, sin el incremento temporal del carbón activado ni otros efectos que terminen al morir.
5. **Oportunidades:** El contador de oportunidades comienza con el valor establecido para cada partida. Cuando se agotan, se activa Game Over y el intento termina.
6. **Persistencia del equipo:** Jack comienza con el brazo mecánico. Obtiene el blaster al derrotar al primer enemigo del Nivel 2 y recogerlo; desde entonces debe conservarse al cambiar de nivel y al recuperar una partida válida.
7. **Mejoras permanentes:** Solo existen dos mejoras de máquina y cada una se adquiere una vez: prótesis de combate (velocidad ×1.3, salto ×1.3, daño físico ×1.5) e incremento ilegal de blaster (daño ×2). Sus efectos no deben acumularse mediante compras repetidas.
8. **Consumibles:** El botiquín recupera salud sin exceder el límite aplicable; la adrenalina incrementa movimiento y salto durante cinco segundos; el carbón activado añade una reserva temporal equivalente al 20% de la salud base, que se consume primero con el daño y se pierde al morir.
9. **Recursos y economía:** Las tuercas se obtienen durante el recorrido y se gastan en mejoras. El tratamiento de las tuercas perdidas al morir debe mantenerse coherente con los checkpoints y con el sistema de bolsa recuperable.
10. **Condiciones de avance:** No es posible completar el Nivel 1 sin satisfacer la condición de enemigos que habilita su puerta ni el Nivel 2 sin destruir los tres tanques vinculados a la salida. El Nivel 3 concluye al derrotar a Lucius Corr.
11. **Guardado:** El guardado registra el nivel, el checkpoint, las oportunidades, armas, mejoras, recursos y objetivos relevantes mediante datos JSON. 
12. **Victoria:** La partida solo se considera terminada exitosamente cuando se derrota al jefe final. La victoria conduce a la pantalla correspondiente y, después, a los créditos.

## Casos especiales

- **Muerte sin checkpoint:** Si Jack muere antes de activar uno, su punto de reaparición será el inicio válido del nivel, siempre que queden oportunidades.
- **Muerte con cero oportunidades:** No debe activarse una reaparición adicional ni descontarse el contador por debajo de cero; se presenta Game Over.
- **Daño simultáneo:** Varios impactos recibidos durante la misma muerte no deben descontar más de una oportunidad ni lanzar repetidamente la pantalla de derrota.
- **Pérdida de salud adicional:** Si Jack tiene salud temporal del carbón activado, el daño consume primero esa reserva. Cuando se agota, el daño restante afecta la salud normal. Al morir, el beneficio desaparece.
- **Cambio de nivel con efectos temporales:** Los efectos de duración limitada conservan únicamente el tiempo restante al cambiar de escena; no se duplican ni se transforman en mejoras permanentes.
- **Recoger el blaster por segunda vez:** Si el arma ya está registrada como adquirida, el evento de obtención no debe generar copias ni reiniciar el estado del inventario.
- **Compras duplicadas:** La máquina no debe descontar tuercas ni aplicar nuevamente una mejora adquirida. La mejora del blaster no puede comprarse antes de obtener la pistola.
- **Recursos perdidos al morir:** La bolsa recuperable registra una sola vez las tuercas perdidas por muerte, evitando duplicaciones entre reapariciones, checkpoints y cargas.
- **Guardado ausente o inválido:** Continuar debe aparecer deshabilitado o comunicar que no existe un progreso recuperable. El error no debe impedir comenzar una nueva partida.
- **Carga en un estado imposible:** Si un guardado referencia un checkpoint, escena u objetivo inexistente, el juego debe recuperar un punto seguro válido o informar del error, sin colocar a Jack fuera del escenario.
- **Interacciones durante una pantalla bloqueante:** No deben activarse puertas, compras, disparos ni ataques mientras se encuentra abierto un menú de pausa, derrota, victoria o carga.
- **Victoria y muerte simultáneas:** Debe existir una prioridad definida para evitar activar Game Over y Victoria al mismo tiempo. La victoria tiene prioridad si la derrota de Lucius queda registrada antes del daño letal al jugador; en otro caso se procesa la derrota.
- **Salida sin requisitos cumplidos:** Si faltan enemigos obligatorios o tanques por destruir, la puerta debe permanecer bloqueada y el jugador debe recibir una indicación clara de la condición pendiente.

---

**Navegación:** [[00 - Índice]] · ← [[06 - Economía y Recursos]] · [[01 - Premisa y Trama]] →
