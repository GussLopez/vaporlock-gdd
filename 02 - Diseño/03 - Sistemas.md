# Sistemas del Juego

## Descripción de la sección

Los sistemas de **Vaporlock** coordinan el movimiento, el combate, la salud, los enemigos, la interacción, los recursos, la progresión, el guardado y las interfaces. Cada sistema establece entradas, reglas y resultados que se relacionan entre sí para mantener una experiencia coherente a lo largo de los tres niveles.

## Inventario de sistemas

| Sistema | Propósito | Dependencias principales |
|---|---|---|
| Movimiento y plataformas | Desplazamiento, salto, dash y escalada | Movimiento, físicas 2D y controles |
| Combate físico y energía | Ataques del brazo y RayPunch | Combate, energía y salud |
| Arsenal y consumibles | Blaster, munición y curación/buffs | Arsenal, estadísticas e inventario |
| Salud, daño y muerte | Reducir salud, proteger frente a impactos y morir | Salud, daño y reaparición |
| IA de enemigos | Detectar, perseguir y atacar a Jack | Comportamiento enemigo y salud |
| Interacción y objetivos | Usar elevador, estación, puertas y tanques | Interacción, colisiones y objetivos |
| Economía y mejoras | Obtener tuercas y comprar dos mejoras finales | Economía, mejoras y estadísticas |
| Checkpoints y oportunidades | Recuperar el avance tras morir | Salud, escenas, guardado, HUD |
| Guardado y continuación | Persistir partida, desbloqueos y estadísticas | Serialización JSON, progreso y gestor de escenas |
| Menús, HUD y flujo | Mostrar estado y conectar pantallas | Controles, interfaces, escenas y guardado |
| Progreso de niveles y victoria | Desbloquear puertas, niveles y créditos | Puertas, objetivos, jefe final y progreso |

## Plantilla de sistema

Cada sistema registra: **nombre, objetivo, entradas, procesamiento/reglas, salidas, estados posibles, dependencias, interacciones, datos que necesita, datos que genera, riesgos y criterios de aceptación**.

## Sistema 01 — Movimiento y navegación 2D

**Objetivo:** Controlar a Jack con precisión en recorridos de plataformas y espacios industriales.

**Entradas:** Movimiento horizontal y vertical contextual, salto y dash; contacto con suelo, pendientes, cadenas y plataformas.

**Procesamiento / reglas:** `Player` lee el Input System, calcula velocidad, saltos y dash; `PlayerClimb` permite movimiento vertical cuando existe una cadena disponible. Se evitan acciones incompatibles con daño, ataques o bloqueo de movimiento.

**Salidas:** Posición, velocidad, orientación, animaciones y eventos de colisión.

**Estados posibles:** En suelo, en aire, saltando, cayendo, en dash, escalando, herido o bloqueado.

**Dependencias:** `Rigidbody2D`, colliders, layer de suelo, `Player`, `PlayerClimb` y animator.

**Interacciones:** Combate, zonas letales, elevador, adrenalina y mejora de prótesis.

**Datos que necesita:** Entradas, posición, velocidad base, potencia de salto y modificadores activos.

**Datos que genera:** Estado de movilidad, posición del jugador y contacto con superficies.

**Riesgos:** Saltos inconsistentes, boosts acumulados sin control o movimientos disponibles durante estados bloqueados.

**Criterios de aceptación:** Jack se mueve y salta de forma reproducible; el dash respeta enfriamiento; puede trepar cadenas; las mejoras permanentes y temporales se aplican y retiran correctamente.

## Sistema 02 — Combate cuerpo a cuerpo y energía

**Objetivo:** Gestionar golpes de brazo mecánico, combos y ataque especial RayPunch.

**Entradas:** Comandos de ataque, estados de Jack, posición de objetivos, reserva de energía.

**Procesamiento / reglas:** Verifica si el movimiento es válido, reproduce la animación, calcula el área de golpe, aplica daño una vez por impacto y recupera o gasta energía. Los ataques disponibles dependen de ventanas de combo y estado físico. La mejora de prótesis aplica un multiplicador de daño físico **×1.5**.

**Salidas:** Daño, reacciones enemigas, efectos, cambios en la reserva energética y eventos de derrota.

**Estados posibles:** Listo, ejecutando ataque, recuperándose, combo en progreso, bloqueado o sin energía suficiente.

**Dependencias:** `PlayerCombat`, `AttackData`, `DamageInfo`, `Health`, animaciones y HUD de energía.

**Interacciones:** Movimiento, daño del jugador, IA y recurso de combate.

**Datos que necesita:** Daño base, multiplicador físico, alcance, costo del RayPunch y energía actual.

**Datos que genera:** Impactos confirmados, daño aplicado y energía actualizada.

**Riesgos:** Doble registro de impacto, discrepancia entre animación y hitbox, recursos negativos o mal llamados.

**Criterios de aceptación:** Combo, Uppercut, CrossKick, ataque aéreo y RayPunch responden a las entradas; no se ejecutan ataques inválidos; el daño aumenta ×1.5 solo cuando la mejora correspondiente está activa.

## Sistema 03 — Arsenal y objetos consumibles

**Objetivo:** Administrar blaster, munición cuando aplique, botiquín, adrenalina y carbón activado.

**Entradas:** Recogida de la pistola, uso de arma, daño/curación, uso de objetos y compra de mejora.

**Procesamiento / reglas:** Jack no posee blaster en el nivel 1; al derrotar al primer enemigo del nivel 2, recoge el objeto y se habilita la capacidad de disparar de forma permanente. El botiquín cura sin rebasar el máximo. La adrenalina aumenta movilidad durante **5 segundos**. El carbón activado otorga **+20% de salud temporal**, consumida prioritariamente por daño o eliminada al morir. El blaster puede recibir una mejora única **×2 de daño**.

**Salidas:** Inventario y estado de armas, barras/indicadores, proyectiles, curación y buffs.

**Estados posibles:** Blaster bloqueado/disponible; arma lista/recargando; consumible disponible/en uso/agotado; buff activo/inactivo.

**Dependencias:** Arsenal, estadísticas, salud, progresión e interfaz.

**Interacciones:** Combate, salud, IA, reaparición, máquina y guardado.

**Datos que necesita:** `hasBlaster`, munición, cantidad de consumibles, duración de buffs, vida base y mejorada.

**Datos que genera:** Cambios de inventario, salud, temporizadores, proyectiles y desbloqueos.

**Riesgos:** Pérdida del blaster al reiniciar, efecto de salud permanente por error o adquisición repetida.

**Criterios de aceptación:** Arma obtenida exactamente una vez, guardada correctamente y nunca revendida; botiquín funcional; adrenalina expira a los 5 s; el +20% temporal desaparece después de agotarse o al morir; daño del blaster duplica solo tras la compra.

## Sistema 04 — Salud, daño y muerte

**Objetivo:** Representar el estado vital y responder de forma coherente a ataques y riesgos.

**Entradas:** Daño de enemigo, colisión con zona letal, curación, bonificaciones de salud y eventos de muerte.

**Procesamiento / reglas:** La salud disminuye al recibir daño válido y respeta los periodos de invulnerabilidad que correspondan. La reacción a impactos incluye daño, aturdimiento y animaciones. Al morir, Jack pierde una oportunidad, se muestra la derrota y reaparece desde un checkpoint o pasa a Game Over.

**Salidas:** Salud restante, animación de daño/muerte, HUD y solicitud de transición.

**Estados posibles:** Vivo, herido, invulnerable brevemente, aturdido, derrotado, esperando respawn / Game Over.

**Dependencias:** Salud, daño y reaparición, prefabs de jugador y sistema de oportunidades futuro.

**Interacciones:** Combate, consumibles, checkpoints, economía y guardado.

**Datos que necesita:** Salud base de 80 puntos, salud actual, bono temporal, oportunidades y último checkpoint.

**Datos que genera:** Evento de daño/muerte, salud actual y estadísticas de derrotas.

**Riesgos:** Descontar dos veces la misma muerte, conservar el +20% después del respawn o reiniciar una escena incorrecta.

**Criterios de aceptación:** El daño se registra una sola vez por evento válido; zonas letales provocan muerte; respawn restaura salud normal y cancela buffs; el sistema de oportunidades y checkpoints mantiene una reaparición coherente.

## Sistema 05 — Inteligencia artificial de enemigos

**Objetivo:** Crear enfrentamientos progresivamente más exigentes y bloquear zonas cuando sea necesario.

**Entradas:** Posición y proximidad de Jack, límites de terreno, estado del enemigo y daño recibido.

**Procesamiento / reglas:** Cada variante Sentinela emplea sus rutinas de detección y ataque. En el nivel 1 se utilizan Beta32 y Beta64; el nivel 2 incorpora además Alpha16 y KAR. La eliminación de determinados enemigos desbloquea el acceso industrial.

**Salidas:** Movimiento, ataques, daño, eventos de muerte y posibles tuercas.

**Estados posibles:** Inactivo/patrullando (según variante), detectando, persiguiendo, atacando, reaccionando a daño y destruido.

**Dependencias:** Arquetipos de Sentinela, colisiones y sistema de salud.

**Interacciones:** Combate del jugador, progreso de puertas, recompensas y adquisición del blaster.

**Datos que necesita:** Salud, alcance y tiempos de ataque configurados por prefab.

**Datos que genera:** Daño a Jack, destrucción, notificación de muerte y drop de recursos.

**Riesgos:** Enemigos fuera de alcance que bloqueen progresión, duplicación de drops o falta de entrega del blaster.

**Criterios de aceptación:** Las cuatro variantes actúan de acuerdo con sus patrones; el enemigo obligatorio del nivel 2 entrega el blaster; las puertas reciben los eventos de muerte correctos.

## Sistema 06 — Interacciones, puertas y objetivos de nivel

**Objetivo:** Permitir que el jugador active mecanismos y cumpla condiciones de avance.

**Entradas:** Cercanía e interacción `E`, enemigos eliminados, tanques destruidos, nivel activo.

**Procesamiento / reglas:** El sistema identifica objetos interactivos cercanos. En el Nivel 1, la puerta industrial se habilita tras derrotar a dos enemigos específicos. En el Nivel 2, la estación de mejoras y el elevador permiten interacción contextual; la salida al Obelisco se desbloquea cuando los tres tanques industriales quedan destruidos.

**Salidas:** Puertas abiertas, movimiento de elevador, UI de estación y carga de nueva escena.

**Estados posibles:** Sin detectar, disponible, bloqueado, activado y transición de nivel.

**Dependencias:** Detección de interacción, mecanismos, puertas, tanques y objetivos del escenario.

**Interacciones:** Combate, objetivos, escenarios y guardado.

**Datos que necesita:** Enemigos obligatorios vivos, tanques restantes y escena siguiente.

**Datos que genera:** Banderas de objetivo completo, animaciones, transición y desbloqueo de nivel.

**Riesgos:** Puerta atascada al perder referencias, escenario 3 inexistente o transiciones múltiples.

**Criterios de aceptación:** La puerta del nivel 1 se abre al destruir los enemigos asignados; la del nivel 2 exige exactamente tres tanques; la salida conduce al escenario correspondiente.

## Sistema 07 — Economía y máquina de mejoras

**Objetivo:** Vincular derrotas y exploración con mejoras comprensibles.

**Entradas:** Tuercas recogidas, apertura de estación, selección y confirmación de compra.

**Procesamiento / reglas:** Los enemigos pueden soltar tuercas; el saldo de tuercas se registra y la estación verifica los requisitos de compra. El catálogo contiene **dos mejoras, con un nivel cada una**. La mejora del blaster requiere que el arma haya sido obtenida. El precio de cada mejora corresponde al costo indicado por la estación.

**Salidas:** Recursos descontados, mejora persistente y HUD actualizado.

**Estados posibles:** Recurso insuficiente, compra disponible, compra efectuada, mejora al máximo, mejora bloqueada.

**Dependencias:** Recolección de tuercas, estadísticas, estación de mejoras y registro del progreso.

**Interacciones:** Enemigos, estadísticas, guardado, combate y movilidad.

**Datos que necesita:** Saldo, precios, posesión del blaster y estados de compra.

**Datos que genera:** Balance de recursos y banderas permanentes de actualización.

**Riesgos:** Que se permitan compras no autorizadas; que morir revierta mejoras adquiridas; precios imposibles.

**Criterios de aceptación:** Solo se muestran las dos mejoras; cada una puede comprarse una vez; los multiplicadores se aplican de forma exacta sobre sus valores base; el saldo no puede ser negativo.

## Sistema 08 — Checkpoints, oportunidades y reaparición

**Objetivo:** Administrar el ciclo derrota → oportunidad restante → reaparición o Game Over del videojuego.

**Entradas:** Activar checkpoint, daño letal, cantidad actual de oportunidades y progreso guardado.

**Procesamiento / reglas:** Un checkpoint registra escena y posición. Al morir, el juego descuenta **una** oportunidad; si queda alguna, muestra derrota y reaparece en el último checkpoint. Si no quedan, pasa a Game Over y habilita retorno al menú. El número inicial de oportunidades se establece para la partida y se descuenta según las reglas de derrota.

**Salidas:** Pantalla de derrota, oportunidades actualizadas, posición de reaparición, Game Over.

**Estados posibles:** Sin checkpoint, checkpoint activo, jugando, derrotado, respawning y sin oportunidades.

**Dependencias:** Salud, muerte, gestión de niveles, datos de guardado e interfaz.

**Interacciones:** Guardado, inventario, salud, consumibles y progreso de misión.

**Datos que necesita:** Escena, checkpoint activo, oportunidades, estado de mejoras y objetos temporales.

**Datos que genera:** Nuevo estado vital, contador y reaparición.

**Riesgos:** Doble descuento, teletransportación al checkpoint incorrecto o inconsistencias al cerrar el juego.

**Criterios de aceptación:** Una muerte descuenta solo una oportunidad; siempre respawnea en checkpoint válido cuando queden oportunidades; con cero oportunidades no respawnea automáticamente; los buffs temporales se eliminan.

## Sistema 09 — Guardado, carga y continuidad (JSON)

**Objetivo:** Recuperar el avance del jugador al seleccionar **Continuar partida** y registrar la conclusión de la aventura.

**Entradas:** Inicio de partida nueva, activación de checkpoint, cambio de nivel, compra, muerte y victoria.

**Procesamiento / reglas:** El sistema serializa en JSON el progreso del jugador, incluyendo nivel, checkpoint, oportunidades, armamento, mejoras, recursos, objetivos y estadísticas. «Nueva partida» establece un estado limpio y «Continuar partida» restaura el último guardado válido.

**Salidas:** Partida restaurada, datos guardados, estado de menú «Continuar» habilitado/deshabilitado y estadísticas finales.

**Estados posibles:** Sin partida, partida válida, guardando, cargando, partida terminada, guardado inválido.

**Dependencias:** Progresión, serialización JSON, gestión de escenas, checkpoints y menú principal.

**Interacciones:** Compras, recursos, inventario, desbloqueos, muerte, niveles y créditos.

**Datos que necesita:** `saveVersion`, escena, checkpoint, oportunidades, `hasBlaster`, mejoras, recursos, consumibles, objetivos completados, tiempo, muertes y enemigos derrotados. Los campos forman parte del registro de progreso.

**Datos que genera:** JSON de progreso y estadísticas, marcas de actualización y estado de partida.

**Riesgos:** Archivos corruptos, reinicio incompleto en «Nueva partida», persistencia de buffs temporales no deseada, incoherencia entre formatos.

**Criterios de aceptación:** «Nueva partida» crea estado inicial limpio tras confirmación; «Continuar» restaura un estado válido; el guardado conserva adquisiciones permanentes; la victoria registra estadísticas y permite mostrar créditos.

## Sistema 10 — Interfaz, menús y flujo de escenas

**Objetivo:** Informar al jugador y enlazar las pantallas y las rutas de navegación.

**Entradas:** Selección de menú, interacción, salud/recursos, eventos de muerte, finalización de nivel y victoria.

**Procesamiento / reglas:** HUD muestra salud, energía y arsenal cuando corresponde. En estación, la UI permite elegir y comprar mejoras y suspende el tiempo durante su uso. El menú principal, la presentación de Jack, la pantalla de derrota, las oportunidades, el Game Over y los créditos componen la navegación del videojuego.

**Salidas:** Mensajes de estado, HUD, interfaces, menús y transiciones.

**Estados posibles:** Menú principal, carga, jugando, estación abierta, pausa, derrota, Game Over, victoria y créditos.

**Dependencias:** Controles, interfaz de estación, HUD, gestor de escenas y persistencia.

**Interacciones:** Todos los sistemas jugables y guardado.

**Datos que necesita:** Salud, energía, munición, oportunidades, recursos, objetivos y partida existente.

**Datos que genera:** Selecciones, eventos de pantalla y solicitudes de carga.

**Riesgos:** Interfaces que ocultan acciones; falta de opción para salir/cargar; pausa sin restaurar el tiempo; botones que cargan escenas inexistentes.

**Criterios de aceptación:** Cada pantalla respeta las transiciones establecidas entre estados; durante derrota y menús el jugador no puede seguir atacando; «Continuar» solo se activa con partida válida; «Volver al menú» no genera pérdidas accidentales.

## Sistema 11 — Progresión de niveles y victoria final

**Objetivo:** Coordinar la secuencia de los tres niveles y sus condiciones de salida, culminando en la victoria contra Lucius Corr.

**Entradas:** Selección de nueva partida o continuar, eventos de objetivos completados, transiciones de puertas, derrota de Lucius y datos de progreso.

**Procesamiento / reglas:** El flujo comienza con el menú principal y una presentación de Jack, seguida del **Nivel 1 — Tejados de Metronia**. Para salir del Nivel 1 deben derrotarse los dos enemigos asociados a la puerta industrial; en el **Nivel 2 — Distrito Industrial** se obtiene el blaster del primer enemigo  y deben destruirse los tres tanques de gas para habilitar la salida. En el **Nivel 3 — El Obelisco**, el desafío final consiste en derrotar a Lucius Corr, registrar el resultado y mostrar victoria y créditos.

**Salidas:** Cambio de escena, actualización de misión, nuevos desbloqueos y estado de victoria al finalizar el Nivel 3.

**Estados posibles:** Nivel bloqueado, iniciado, en progreso, objetivo cumplido, salida disponible, completado y victoria final.

**Dependencias:** Puertas, tanques, gestión de escenas, guardado, jefe final y créditos.

**Interacciones:** IA enemiga, combate, objetos destructibles, desbloqueo del blaster, economía, checkpoints, guardado e interfaz.

**Datos que necesita:** Nivel actual, enemigos obligatorios eliminados, cantidad de tanques destruidos, posesión del blaster, estado del jefe y progreso guardado.

**Datos que genera:** Marcadores de misión, nivel completado, escena siguiente desbloqueada, estadísticas y condición de victoria.

**Riesgos:** Abrir salidas sin completar objetivos; perder progresión entre niveles; intentar cargar una escena inválida; activar créditos sin derrotar al jefe.

**Criterios de aceptación:** Nivel 1 transfiere al Nivel 2 después de desbloquear su puerta; Nivel 2 habilita salida únicamente tras destruir los tres tanques; el blaster se obtiene de su enemigo asignado; Nivel 3 termina tras derrotar a Lucius y muestra victoria y créditos. 

## Relaciones entre sistemas

```text
Controles → Movimiento ───────┐
         ├→ Combate físico ─────┼→ Daño y salud → Muerte → Oportunidades → Checkpoint
         ├→ Blaster/consumibles ┤                          │                     │
         └→ Interacciones ──────┘                          └────→ Guardado ←─────┤
                    │                                            ↑               │
Enemigos → Drops → Tuercas → Máquina de mejoras ────────────────┤               │
                    │                                            │               │
Enemigos / tanques → Objetivos → Puertas → Niveles ──────────────┘               │
                                             │                                   │
                                      Jefe final → Victoria → Créditos           │
                                             ↑                                   │
                                        Menú / Continuar ←────────────────────────┘
```

Los datos de **economía, mejoras, posesión del blaster y progreso** se deben compartir con el guardado. Los **efectos temporales** (adrenalina y carbón activado) deben gestionarse por separado para que no reaparezcan incorrectamente después de una muerte. Las oportunidades y checkpoints regulan la continuidad de la partida.

> **Navegación:** [[00 - Índice]] · ← [[02 - Mecánicas]] · [[04 - Controles]] →
