03 - Sistemas del Juego

# Sistemas del Juego

## Descripción de la sección

Los sistemas de **Vaporlock** comprenden el conjunto de componentes y reglas que permiten el funcionamiento del videojuego, coordinando las acciones del jugador, el comportamiento de los enemigos, las interacciones con el escenario y la progresión de la aventura.

Estos sistemas trabajan conjuntamente para proporcionar una experiencia de acción, aventura y plataformas en 2D, donde Jack Veil puede desplazarse, combatir, recolectar recursos, adquirir mejoras y completar los objetivos establecidos en cada nivel.

Su funcionamiento busca mantener una relación coherente entre las mecánicas, los recursos disponibles y las consecuencias de las acciones del jugador, asegurando una experiencia comprensible y progresiva.

El diseño contempla tanto los sistemas existentes en el proyecto de Unity como las funcionalidades previstas para la versión final del videojuego.

## Inventario de sistemas

| Sistema | Propósito | Dependencias | Estado |
|---|---|---|---|
| Movimiento y plataformas | Controlar el desplazamiento y las habilidades de movilidad de Jack. | Físicas 2D, controles y animaciones. | Implementado |
| Combate cuerpo a cuerpo | Gestionar los ataques físicos y las habilidades especiales del brazo mecánico. | Daño, energía, animaciones y enemigos. | Implementado |
| Arsenal y consumibles | Administrar el blaster, munición y objetos utilizables. | Combate, inventario y salud. | Parcial |
| Salud, daño y muerte | Controlar la supervivencia del personaje. | Combate, enemigos y escenarios. | Implementado; adaptación pendiente |
| Inteligencia artificial | Controlar el comportamiento de los enemigos. | Detección, movimiento y combate. | Implementado para enemigos actuales |
| Interacción y objetivos | Gestionar mecanismos, puertas y condiciones de avance. | Jugador, enemigos y escenarios. | Implementado en niveles 1 y 2 |
| Economía y mejoras | Administrar recursos y actualizaciones del personaje. | Recolección, estadísticas y estación de mejoras. | Parcial |
| Checkpoints y oportunidades | Administrar la reaparición y los intentos disponibles. | Salud, niveles y guardado. | Por implementar |
| Guardado y carga | Conservar y recuperar el progreso del jugador. | Progresión, recursos y serialización JSON. | Parcial |
| Interfaz y navegación | Mostrar información y controlar las pantallas del videojuego. | HUD, controles y escenas. | Parcial |
| Progresión y victoria | Coordinar la finalización de niveles y del videojuego. | Objetivos, enemigos, escenas y jefe final. | Parcial |

## Plantilla de sistema

Cada sistema se documenta mediante su objetivo, entradas, reglas de procesamiento, salidas, estados, dependencias e interacciones.

También se identifican los datos necesarios para su funcionamiento, los resultados que produce, los posibles riesgos y los criterios que permiten comprobar su funcionamiento correcto.

## Sistema 01 — Movimiento y plataformas

**Objetivo:**

Permitir que Jack Veil se desplace e interactúe físicamente con los escenarios bidimensionales, proporcionando las habilidades necesarias para superar obstáculos, plataformas y estructuras industriales.

**Entradas:**

Controles de movimiento horizontal, salto, dash y escalada, además de la detección de superficies, pendientes, cadenas y plataformas.

**Procesamiento / reglas:**

El sistema interpreta las entradas del jugador y modifica el movimiento del personaje mediante las físicas 2D de Unity.

Jack puede desplazarse horizontalmente, saltar sobre plataformas, utilizar un dash de corta duración y ascender o descender por cadenas.

Las acciones respetan las condiciones físicas del escenario y los estados del personaje. Su rendimiento puede modificarse mediante consumibles temporales o mejoras permanentes.

**Salidas:**

Desplazamiento del personaje, cambios de posición, animaciones de movimiento y detección de colisiones con el escenario.

**Estados posibles:**

En reposo, caminando, saltando, cayendo, realizando dash, escalando, recibiendo daño o incapacitado.

**Dependencias:**

Sistema de controles, Rigidbody2D, Collider2D, físicas de Unity y animaciones del personaje.

**Interacciones:**

Combate, obstáculos, elevadores, trampas, consumibles y mejoras de prótesis.

**Datos que necesita:**

Velocidad de movimiento, fuerza de salto, gravedad, duración y recuperación del dash, estado físico y modificadores activos.

**Datos que genera:**

Posición, velocidad, dirección, estado de movimiento y eventos de contacto con superficies.

**Riesgos:**

Errores de colisión, movimientos inconsistentes, saltos no permitidos o acumulación incorrecta de bonificaciones de velocidad y salto.

**Criterios de aceptación:**

El jugador puede desplazarse, saltar, realizar dash y trepar cadenas correctamente. Las mejoras y consumibles modifican los atributos correspondientes sin afectar el funcionamiento normal de las físicas.

---

## Sistema 02 — Combate cuerpo a cuerpo y energía

**Objetivo:**

Gestionar los ataques físicos que Jack Veil realiza mediante su brazo mecánico, permitiéndole enfrentar enemigos y utilizar habilidades especiales durante el combate.

**Entradas:**

Comandos de ataque, posición del jugador, presencia de enemigos, estado de combate y cantidad de energía disponible.

**Procesamiento / reglas:**

El sistema identifica el ataque seleccionado, comprueba que Jack se encuentre en condiciones de ejecutarlo y reproduce la animación correspondiente.

El brazo mecánico permite realizar combinaciones de golpes, ataques aéreos y movimientos especiales como Uppercut, CrossKick y RayPunch.

Los ataques aplican daño cuando alcanzan correctamente a un enemigo. Algunos movimientos permiten recuperar energía, mientras que los ataques especiales consumen parte de esta reserva.

Cuando el jugador adquiere la actualización a prótesis de combate, el daño físico aumenta un 50% respecto al valor original.

**Salidas:**

Daño a enemigos, animaciones de ataque, efectos de impacto, alteraciones en la energía disponible y eventos de derrota de enemigos.

**Estados posibles:**

Disponible, atacando, ejecutando combo, utilizando habilidad especial, recuperándose o incapacitado.

**Dependencias:**

Sistema de controles, animaciones, detección de impactos, energía y salud de enemigos.

**Interacciones:**

Movimiento, inteligencia artificial, salud, recolección de recursos y máquina de mejoras.

**Datos que necesita:**

Daño de ataques, alcance, duración, energía disponible, costo de habilidades y multiplicadores activos.

**Datos que genera:**

Ataques ejecutados, daño infligido, energía consumida o recuperada y eventos de eliminación de enemigos.

**Riesgos:**

Impactos registrados varias veces, ataques ejecutados durante estados incompatibles o consumo incorrecto de energía.

**Criterios de aceptación:**

Los ataques responden correctamente a los controles, producen daño únicamente cuando alcanzan un objetivo válido y respetan las condiciones de ejecución y consumo de energía.

---

## Sistema 03 — Arsenal y consumibles

**Objetivo:**

Administrar el armamento disponible y los objetos consumibles que Jack puede utilizar durante su aventura.

**Entradas:**

Obtención del blaster, comandos de disparo, recolección y utilización de consumibles, munición disponible y mejoras adquiridas.

**Procesamiento / reglas:**

Jack comienza el videojuego utilizando exclusivamente su brazo mecánico.

Al inicio del segundo nivel, después de derrotar al primer enemigo, este deja caer un blaster que el jugador puede recoger. Desde ese momento, el arma queda disponible permanentemente junto con el brazo mecánico.

El blaster permite disparar proyectiles de energía contra enemigos y determinados objetos destructibles.

El sistema también administra los siguientes consumibles:

- **Botiquín:** Recupera una cantidad determinada de salud.
- **Inyección de adrenalina:** Incrementa temporalmente la velocidad y capacidad de salto durante 5 segundos.
- **Inyección de carbón activado:** Proporciona un incremento temporal del 20% de la salud máxima de Jack. La salud adicional absorbe daño hasta agotarse y desaparece al morir.

La mejora Incremento ilegal de blaster duplica el daño original de sus disparos.

El sistema de munición existente en Unity deberá mantenerse o adaptarse de acuerdo con las reglas definitivas del arma.

**Salidas:**

Disparos, consumo de munición, recuperación de salud, bonificaciones temporales y actualización de los objetos disponibles.

**Estados posibles:**

Arma bloqueada, arma disponible, disparando, recargando, consumible disponible, efecto activo o efecto terminado.

**Dependencias:**

Sistema de combate, salud, inventario, estadísticas, mejoras y controles.

**Interacciones:**

Enemigos, objetos destructibles, exploración, guardado y reaparición.

**Datos que necesita:**

Armas adquiridas, munición, cantidades de consumibles, salud actual, duración de efectos y mejoras permanentes.

**Datos que genera:**

Cambios de equipamiento, consumo de objetos, modificaciones temporales de estadísticas y eventos de disparo.

**Riesgos:**

Pérdida de armas al cambiar de nivel, utilización repetida de objetos consumidos o conservación incorrecta de bonificaciones temporales.

**Criterios de aceptación:**

El blaster se obtiene únicamente mediante el evento establecido en el segundo nivel y permanece disponible después de adquirirlo.

Los consumibles aplican correctamente sus efectos, respetan las condiciones de duración y no permanecen activos después de una muerte cuando corresponda eliminarlos.

---

## Sistema 04 — Salud, daño y muerte

**Objetivo:**

Gestionar los puntos de salud de Jack Veil, el daño recibido y las consecuencias de perder toda su vida.

**Entradas:**

Ataques enemigos, contacto con trampas, caídas en zonas peligrosas, objetos curativos y bonificaciones de salud.

**Procesamiento / reglas:**

El sistema administra la salud del jugador y disminuye los puntos disponibles cuando recibe daño válido.

Jack dispone actualmente de una salud máxima base de 80 puntos en la configuración de Unity.

Los impactos pueden producir animaciones de daño, aturdimiento o periodos breves de invulnerabilidad para evitar recibir múltiples golpes de manera inmediata.

Cuando la salud llega a cero, se activa la secuencia de muerte.

Según el flujo previsto del videojuego, el jugador pierde una oportunidad y debe acceder a la pantalla de derrota. Si conserva oportunidades disponibles, podrá reaparecer en el último checkpoint activado.

En caso contrario, deberá regresar al menú principal.

**Salidas:**

Cambios en la salud, animaciones de daño, eventos de muerte y activación del sistema de derrota y reaparición.

**Estados posibles:**

Vivo, herido, invulnerable temporalmente, aturdido, muerto o esperando reaparición.

**Dependencias:**

Sistema de salud, daño, animaciones, oportunidades y checkpoints.

**Interacciones:**

Combate, consumibles, enemigos, trampas, guardado y progresión.

**Datos que necesita:**

Salud máxima, salud actual, cantidad de daño, protección temporal, oportunidades restantes y checkpoint activo.

**Datos que genera:**

Salud actualizada, eventos de daño, muerte, pérdida de oportunidades y estadísticas de derrotas.

**Riesgos:**

Daño duplicado, activación repetida de la muerte, reaparición incorrecta o permanencia de bonificaciones temporales después de morir.

**Criterios de aceptación:**

La salud disminuye correctamente al recibir daño y nunca permanece por debajo de cero.

La muerte se activa una sola vez por evento y, cuando se implemente el sistema completo de oportunidades, el jugador reaparece correctamente o regresa al menú según corresponda.

---

## Sistema 05 — Inteligencia artificial de enemigos

**Objetivo:**

Controlar el comportamiento de los enemigos para generar enfrentamientos dinámicos y desafíos progresivos.

**Entradas:**

Posición del jugador, distancia de detección, estado de cada enemigo, condiciones del escenario y daño recibido.

**Procesamiento / reglas:**

Cada enemigo utiliza un conjunto de comportamientos que determina cómo detecta, persigue y ataca a Jack.

Los enemigos pueden realizar diferentes acciones dependiendo de su tipo, distancia y estado.

Actualmente, el proyecto utiliza cuatro variantes principales:

- **Sentinela Beta32:** Enemigo básico de combate cercano.
- **Sentinela Beta64:** Enemigo pesado con ataques físicos de mayor intensidad.
- **Sentinela Alpha16:** Enemigo ágil con diferentes ataques y capacidad de aturdimiento.
- **Sentinela KAR:** Robot que utiliza ataques eléctricos de área.

Cuando un enemigo pierde toda su salud, se destruye y puede generar recursos para el jugador.

Algunos enemigos también participan en el cumplimiento de objetivos, como desbloquear puertas o entregar el blaster al inicio del segundo nivel.

**Salidas:**

Movimiento enemigo, ataques, daño al jugador, animaciones, destrucción y generación de recompensas.

**Estados posibles:**

Inactivo, patrullando, detectando, persiguiendo, atacando, recibiendo daño, aturdido o destruido, según las capacidades de cada variante.

**Dependencias:**

Sistema de movimiento enemigo, detección, combate, salud y animaciones.

**Interacciones:**

Combate del jugador, recolección de recursos, objetivos de nivel y progresión.

**Datos que necesita:**

Posición del jugador, salud, velocidad, daño, rango de detección y tiempos de ataque.

**Datos que genera:**

Acciones enemigas, daño producido, eventos de eliminación y recursos disponibles.

**Riesgos:**

Enemigos que no detectan correctamente al jugador, comportamientos repetitivos, ataques imposibles de evitar o bloqueos de progreso.

**Criterios de aceptación:**

Cada enemigo ejecuta sus comportamientos conforme a sus características y responde correctamente a la presencia, ataques y movimientos del jugador.

Las eliminaciones necesarias para completar objetivos deben registrarse correctamente.

---

## Sistema 06 — Interacción y objetivos del escenario

**Objetivo:**

Permitir que Jack Veil interactúe con elementos del entorno y complete las condiciones necesarias para avanzar por los niveles.

**Entradas:**

Comandos de interacción, cercanía a mecanismos, enemigos eliminados y objetos destructibles.

**Procesamiento / reglas:**

El jugador puede interactuar con determinados objetos del escenario cuando se encuentra dentro de su área de activación.

Los mecanismos pueden incluir puertas, elevadores, terminales y estaciones de mejora.

Algunos requieren cumplir condiciones específicas antes de activarse.

En el primer nivel, la puerta industrial permanece bloqueada hasta eliminar los enemigos establecidos.

En el segundo nivel, el jugador debe destruir los tres tanques de gas para desbloquear la salida hacia el Obelisco.

**Salidas:**

Apertura de puertas, activación de elevadores, acceso a estaciones, actualización de objetivos y transiciones de nivel.

**Estados posibles:**

Inactivo, disponible, bloqueado, activado, completado o en transición.

**Dependencias:**

Detección de interacciones, objetos del escenario, combate, eventos de destrucción y gestión de niveles.

**Interacciones:**

Exploración, enemigos, objetos destructibles, máquina de mejoras y guardado.

**Datos que necesita:**

Posición del jugador, condiciones de activación, enemigos restantes, objetos destruidos y nivel actual.

**Datos que genera:**

Eventos de activación, objetivos completados, mecanismos desbloqueados y solicitudes de cambio de escenario.

**Riesgos:**

Puertas que no reconocen objetivos completados, mecanismos activados anticipadamente o transiciones repetidas.

**Criterios de aceptación:**

Los mecanismos responden únicamente cuando se cumplen sus requisitos.

Las puertas permiten avanzar después de completar los objetivos correspondientes y comunican visualmente su estado al jugador.

---

## Sistema 07 — Economía y mejoras

**Objetivo:**

Administrar los recursos recolectados y permitir que el jugador los utilice para mejorar permanentemente las capacidades de Jack.

**Entradas:**

Recolección de tuercas, interacción con la máquina de mejoras y selección de actualizaciones.

**Procesamiento / reglas:**

Los enemigos pueden dejar caer tuercas que el jugador recolecta durante su recorrido.

Estas funcionan como recurso de intercambio dentro de la máquina de mejoras.

La versión final contempla únicamente dos actualizaciones:

**1. Actualización a prótesis de combate**

- Velocidad de movimiento: ×1.3.
- Capacidad de salto: ×1.3.
- Daño físico: ×1.5.

**2. Incremento ilegal de blaster**

- Daño del blaster: ×2.

Cada mejora podrá adquirirse una sola vez.

El sistema comprueba que Jack tenga los recursos suficientes y cumpla los requisitos correspondientes antes de completar la compra.

**Salidas:**

Descuento de recursos, aplicación de mejoras, actualización de estadísticas y cambios en la interfaz.

**Estados posibles:**

Disponible, bloqueado, recursos insuficientes, adquirido o mejora completada.

**Dependencias:**

Recolección de tuercas, estadísticas del jugador, máquina de mejoras, interfaz y guardado.

**Interacciones:**

Combate, movilidad, blaster, progresión y persistencia del personaje.

**Datos que necesita:**

Cantidad de tuercas, costos de las mejoras, estadísticas originales, armas adquiridas y mejoras previamente compradas.

**Datos que genera:**

Nuevo saldo de recursos, estadísticas actualizadas y registro permanente de mejoras.

**Riesgos:**

Aplicar bonificaciones varias veces, permitir compras sin recursos suficientes o perder mejoras después de cargar una partida.

**Criterios de aceptación:**

La máquina presenta únicamente las dos mejoras establecidas y permite adquirirlas una vez cada una.

Los valores se actualizan correctamente y permanecen disponibles durante el resto de la partida.

---

## Sistema 08 — Checkpoints y oportunidades

**Objetivo:**

Administrar los puntos de reaparición y las oportunidades disponibles cuando Jack pierde toda su salud.

**Entradas:**

Activación de checkpoints, eventos de muerte, oportunidades restantes y progreso del nivel.

**Procesamiento / reglas:**

Los checkpoints registran puntos específicos del escenario que pueden utilizarse para reaparecer.

Cuando Jack muere, el sistema disminuye una oportunidad y muestra la pantalla de derrota.

Si todavía dispone de oportunidades, puede reaparecer en el último checkpoint activado.

Cuando las oportunidades se agotan, la partida entra en estado de Game Over y el jugador debe regresar al menú principal.

La cantidad inicial de oportunidades y su posible recuperación permanecen pendientes de definir.

**Salidas:**

Actualización del contador de oportunidades, activación de pantalla de derrota, reaparición o Game Over.

**Estados posibles:**

Sin checkpoint, checkpoint activado, jugando, derrotado, reapareciendo o sin oportunidades.

**Dependencias:**

Salud, muerte, escenas, guardado e interfaz.

**Interacciones:**

Progresión, consumibles, combate y navegación.

**Datos que necesita:**

Nivel actual, último checkpoint, posición de reaparición y oportunidades restantes.

**Datos que genera:**

Contador actualizado, punto de reaparición y estado de continuación o derrota definitiva.

**Riesgos:**

Descontar varias oportunidades por una sola muerte, registrar checkpoints incorrectos o reaparecer dentro de obstáculos.

**Criterios de aceptación:**

Cada muerte descuenta exactamente una oportunidad.

Mientras existan oportunidades, el personaje reaparece correctamente. Cuando se agotan, el jugador no puede continuar inmediatamente y debe regresar al menú principal.

*Estado: Sistema previsto en el flujo de juego. Su implementación definitiva permanece pendiente.*

---

## Sistema 09 — Guardado y carga de partida

**Objetivo:**

Conservar el progreso del jugador y permitir que continúe una partida previamente iniciada.

**Entradas:**

Nueva partida, selección de continuar, activación de checkpoints, cambio de nivel, adquisición de mejoras y finalización del videojuego.

**Procesamiento / reglas:**

El sistema registra la información necesaria para restaurar la partida posteriormente.

El diseño contempla el almacenamiento de datos mediante serialización JSON.

Actualmente, Unity utiliza una estructura serializada como JSON dentro de PlayerPrefs para almacenar parte de los recursos y mejoras. Este sistema deberá ampliarse para incluir el progreso completo de la aventura.

La información prevista comprende:

- Nivel actual.
- Checkpoint activado.
- Oportunidades restantes.
- Armas adquiridas.
- Mejoras permanentes.
- Recursos disponibles.
- Consumibles conservados.
- Objetivos completados.
- Estadísticas de la partida.

Al seleccionar Nueva partida, se debe establecer un estado inicial limpio.

Al seleccionar Continuar partida, se recupera el último progreso guardado válido.

**Salidas:**

Datos guardados, restauración del progreso y habilitación de la opción Continuar partida.

**Estados posibles:**

Sin partida guardada, partida disponible, guardando, cargando, partida completada o guardado inválido.

**Dependencias:**

Serialización JSON, administración de escenas, progresión, checkpoints e inventario.

**Interacciones:**

Menú principal, recursos, mejoras, muerte, desbloqueos y victoria.

**Datos que necesita:**

Estado del jugador, nivel, checkpoint, inventario, estadísticas y progresión de objetivos.

**Datos que genera:**

Información persistente de partida, registros de progreso y estadísticas finales.

**Riesgos:**

Pérdida de información, archivos dañados, recuperación incorrecta de objetos o conservación de efectos temporales después de reaparecer.

**Criterios de aceptación:**

El progreso se conserva correctamente entre sesiones y permite restaurar una partida desde un estado válido.

Las mejoras permanentes y armas adquiridas deben mantenerse, mientras que los efectos temporales deben eliminarse cuando corresponda.

---

## Sistema 10 — Interfaz y navegación

**Objetivo:**

Administrar las pantallas del videojuego y proporcionar al jugador información clara sobre su estado y las acciones disponibles.

**Entradas:**

Selecciones del menú, comandos del jugador, cambios de salud, recolección de recursos, eventos de derrota y cumplimiento de objetivos.

**Procesamiento / reglas:**

El sistema muestra la información correspondiente al estado actual del videojuego.

Durante la partida, la interfaz permite consultar elementos como salud, energía, munición y recursos disponibles.

También administra las pantallas y transiciones definidas en el flujo de navegación:

- Menú principal.
- Nueva partida.
- Continuar partida.
- Presentación inicial de Jack, pendiente de definir.
- Interfaz de juego.
- Máquina de mejoras.
- Pantalla de derrota.
- Game Over.
- Pantalla de victoria.
- Créditos.

La presentación inicial no incluye la antigua secuencia del ataque, hospital o conversación con el Tecnócrata.

**Salidas:**

Pantallas, indicadores, notificaciones, mensajes de interacción y transiciones entre estados.

**Estados posibles:**

Menú principal, carga, jugando, interfaz de mejoras, pausa, derrota, Game Over, victoria o créditos.

**Dependencias:**

Sistema de controles, HUD, progreso, guardado, salud y administración de escenas.

**Interacciones:**

Todos los sistemas principales del videojuego.

**Datos que necesita:**

Salud, energía, recursos, munición, objetivos, oportunidades y estado de la partida.

**Datos que genera:**

Solicitudes de navegación, selecciones del jugador y cambios de estado de interfaz.

**Riesgos:**

Información incorrecta, botones sin respuesta, transiciones duplicadas o acciones del jugador que continúan ejecutándose mientras una pantalla bloqueante está abierta.

**Criterios de aceptación:**

Cada pantalla presenta la información correspondiente y permite realizar las acciones establecidas.

Las transiciones respetan el flujo de navegación y las opciones que requieren condiciones previas solo se habilitan cuando estas se cumplen.

---

## Sistema 11 — Progresión de niveles y victoria final

**Objetivo:**

Coordinar el avance del jugador a través de los tres niveles de Vaporlock, administrando los objetivos necesarios para completar la aventura.

**Entradas:**

Inicio o recuperación de partida, cumplimiento de misiones, eliminación de enemigos, destrucción de objetivos y derrota del jefe final.

**Procesamiento / reglas:**

El videojuego se divide en tres niveles principales.

**Nivel 1 — Tejados de Metronia:**

Jack comienza su recorrido y utiliza sus habilidades de movimiento y combate cuerpo a cuerpo para atravesar los tejados.

El jugador debe superar los obstáculos y eliminar los enemigos necesarios para desbloquear la entrada al Distrito Industrial.

**Nivel 2 — Distrito Industrial:**

Jack obtiene el blaster después de derrotar al primer enemigo del nivel.

Durante el recorrido, debe superar enemigos, utilizar mecanismos industriales y destruir los tres tanques de gas necesarios para desbloquear la salida hacia el Obelisco.

También puede utilizar la máquina de mejoras para fortalecer sus capacidades.

**Nivel 3 — El Obelisco:**

El jugador debe superar los obstáculos y enemigos del escenario final hasta llegar al enfrentamiento contra Lucius Corr.

Al derrotar al jefe, el sistema registra la victoria, guarda el progreso y las estadísticas correspondientes y presenta la pantalla final con los créditos.

Este tercer nivel permanece pendiente de implementación en Unity.

**Salidas:**

Actualización de objetivos, cambios de nivel, desbloqueo de escenarios, registro de victoria y activación de créditos.

**Estados posibles:**

Nivel bloqueado, disponible, iniciado, en progreso, objetivo completado, nivel finalizado o victoria definitiva.

**Dependencias:**

Gestión de escenas, combate, enemigos, puertas, objetivos, jefe final, guardado e interfaz.

**Interacciones:**

Movimiento, combate, mejoras, recolección, guardado, checkpoints y navegación.

**Datos que necesita:**

Nivel actual, objetivos completados, enemigos obligatorios eliminados, tanques destruidos y estado del jefe final.

**Datos que genera:**

Progreso de la aventura, niveles completados, desbloqueos y estadísticas finales.

**Riesgos:**

Permitir transiciones sin completar los objetivos, perder información entre niveles o activar el final antes de derrotar a Lucius Corr.

**Criterios de aceptación:**

Cada nivel permite avanzar únicamente después de cumplir sus condiciones de salida.

La victoria definitiva se registra solamente después de derrotar al jefe final y completar los requisitos establecidos.

## Relaciones entre sistemas

Los sistemas de Vaporlock funcionan de manera interdependiente, intercambiando información para mantener la continuidad de las acciones del jugador y el desarrollo de los niveles.

El **sistema de controles** comunica las acciones del jugador a los sistemas de movimiento, combate e interacción.

El **sistema de combate** se relaciona directamente con la salud y la inteligencia artificial de los enemigos, mientras que las derrotas permiten generar recursos utilizados por el sistema de economía.

El **sistema de economía y mejoras** modifica las estadísticas del personaje, afectando directamente su movilidad y capacidad de combate.

El **sistema de interacción** se comunica con los objetivos de cada nivel para activar mecanismos, desbloquear puertas y permitir nuevas transiciones.

Por su parte, los sistemas de **salud, checkpoints y oportunidades** administran las consecuencias de la muerte del personaje.

Finalmente, el **sistema de guardado** recopila la información permanente de los demás sistemas para conservar el progreso del jugador, mientras que la interfaz representa visualmente los acontecimientos importantes.

**Flujo general de relaciones:**

`Controles → Movimiento / Combate / Interacción → Enemigos y objetivos → Recursos y mejoras → Progresión de niveles → Guardado → Victoria`

**Flujo de derrota:**

`Daño recibido → Salud llega a cero → Muerte → Pérdida de oportunidad → Checkpoint o Game Over`

**Flujo de mejoras:**

`Derrotar enemigos → Recolectar tuercas → Máquina de mejoras → Actualizar estadísticas → Continuar aventura`

---

**Navegación:** [[00 - Índice]] · ← [[02 - Mecánicas]] · [[04 - Controles]] →