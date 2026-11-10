02 - Mecanicas

# Mecánicas

## Descripción de la sección

Las mecánicas de *Vaporlock* comprenden las acciones, movimientos e interacciones que el jugador puede realizar durante su aventura. Estas permiten controlar a Jack Veil, desplazarse por los escenarios, enfrentar enemigos, superar obstáculos y utilizar los recursos disponibles para avanzar a través de los diferentes niveles.

El videojuego combina mecánicas de plataformas en 2D con un sistema de combate cuerpo a cuerpo y a distancia, incorporando habilidades de movilidad, ataques especiales, interacción con objetos y mejoras del personaje.

Cada mecánica está diseñada para ofrecer una experiencia dinámica, accesible y progresiva, permitiendo que el jugador desarrolle sus habilidades conforme enfrenta desafíos de mayor dificultad.

## Plantilla de mecánica

Las mecánicas se documentan considerando su propósito, forma de activación, reglas de funcionamiento, recursos utilizados y relación con otros elementos del videojuego.

Para facilitar su comprensión, se dividen en *mecánicas principales, que representan las acciones fundamentales del jugador, y **mecánicas secundarias*, que complementan la experiencia y proporcionan nuevas posibilidades de interacción.

## Mecánicas principales

### Mecánica 01: Movimiento y plataformas

*Propósito:*

Permitir que Jack Veil se desplace por los diferentes escenarios de Metronia, utilizando movimientos horizontales y saltos para explorar, superar obstáculos y alcanzar nuevas áreas del nivel.

*Activación:*

El jugador utiliza los controles de movimiento para desplazarse hacia la izquierda o derecha y el botón de salto para elevarse sobre plataformas u obstáculos.

*Reglas:*

- Jack puede desplazarse horizontalmente dentro de un entorno bidimensional.
- El personaje puede saltar cuando se encuentra sobre una superficie válida.
- La gravedad determina la trayectoria del salto y el descenso del personaje.
- El desplazamiento debe considerar las colisiones con plataformas, paredes y elementos del escenario.
- Las pendientes y superficies elevadas pueden modificar el recorrido del jugador.
- El movimiento puede quedar limitado temporalmente mientras Jack recibe daño, realiza determinadas acciones o interactúa con mecanismos.
- La velocidad y capacidad de salto pueden incrementarse mediante consumibles o mejoras específicas.

*Entrada:*

- A / D o flechas direccionales: movimiento horizontal.
- Espacio: salto.

*Estado inicial:*

Jack se encuentra sobre una plataforma o superficie válida, preparado para desplazarse.

*Estado final:*

El personaje alcanza una nueva posición, aterriza sobre otra superficie o se detiene después del movimiento.

*Recursos utilizados:*

Sistema de físicas 2D de Unity, detección de superficies, animaciones de movimiento y parámetros de velocidad, gravedad y salto.

*Recompensa:*

Permite explorar nuevas áreas, superar obstáculos, evitar peligros y avanzar hacia los objetivos establecidos.

*Penalización:*

Un movimiento incorrecto puede provocar que Jack caiga en zonas peligrosas, reciba daño o pierda la vida.

*Interacciones con otras mecánicas:*

Combate, dash, escalada, interacción con plataformas, trampas, inyección de adrenalina y mejora de prótesis de combate.

*Casos límite:*

Si el personaje cae fuera de los límites permitidos del escenario o entra en contacto con una zona letal, se activa su muerte. También deben evitarse saltos adicionales no autorizados o movimientos durante estados que bloqueen el control del personaje.

---

### Mecánica 02: Combate cuerpo a cuerpo

*Propósito:*

Permitir que Jack Veil enfrente y derrote enemigos utilizando su brazo mecánico, que funciona como su arma principal desde el comienzo del videojuego.

*Activación:*

El jugador ejecuta ataques mediante los controles correspondientes mientras Jack se encuentra en condiciones de combatir.

*Reglas:*

- Jack comienza la aventura equipado con su brazo mecánico.
- Los ataques físicos tienen un alcance limitado y requieren acercarse a los enemigos.
- El jugador puede realizar una secuencia de hasta cuatro golpes consecutivos.
- El sistema incorpora movimientos adicionales como Uppercut, CrossKick y ataques aéreos.
- Los ataques deben respetar sus respectivas animaciones y tiempos de ejecución.
- Los enemigos reciben daño cuando entran en contacto con el área efectiva del ataque.
- Algunas acciones pueden interrumpirse cuando Jack recibe daño o queda incapacitado.
- El daño físico aumenta un 50% al adquirir la mejora *Actualización a prótesis de combate*.

*Entrada:*

- J: combo de golpes.
- K: Uppercut.
- L: CrossKick.
- I: RayPunch, ataque especial que requiere energía.

*Estado inicial:*

Jack se encuentra disponible para atacar y no presenta restricciones que impidan realizar la acción.

*Estado final:*

El personaje completa su movimiento de ataque y regresa a un estado que le permite continuar combatiendo o desplazándose.

*Recursos utilizados:*

Brazo mecánico, animaciones de combate, áreas de impacto, estadísticas de daño y sistema de salud de enemigos.

*Recompensa:*

Infligir daño, derrotar enemigos, obtener recursos y acumular energía para determinados ataques especiales.

*Penalización:*

Al acercarse a los enemigos, Jack queda expuesto a recibir ataques. Además, utilizar movimientos en momentos incorrectos puede dejarlo vulnerable durante sus animaciones.

*Interacciones con otras mecánicas:*

Movimiento, dash, ataques especiales, salud, inteligencia artificial enemiga, recolección de recursos y mejoras del personaje.

*Casos límite:*

Los ataques no deben ejecutarse cuando Jack se encuentra muerto o incapacitado. Cada golpe debe registrar correctamente sus impactos, evitando aplicar daño repetido de manera involuntaria a un mismo enemigo.

---

### Mecánica 03: Combate a distancia

*Propósito:*

Permitir que Jack Veil ataque enemigos y objetos destructibles desde una distancia segura mediante el uso de una pistola tecnológica denominada blaster.

*Activación:*

Al comienzo del segundo nivel, Jack debe derrotar al primer enemigo que encuentra utilizando su brazo mecánico. Una vez destruido, dicho enemigo deja caer el blaster, que puede ser recogido por el jugador.

Después de obtenerlo, el arma queda disponible como parte permanente del equipamiento del personaje.

*Reglas:*

- El blaster no está disponible durante el primer nivel.
- Jack debe adquirirlo derrotando al primer enemigo del Distrito Industrial.
- Una vez obtenido, el jugador puede alternar entre los ataques físicos del brazo mecánico y los disparos.
- Los proyectiles recorren una trayectoria horizontal hasta impactar contra un objetivo o desaparecer según las reglas del escenario.
- Los disparos infligen daño a enemigos y determinados objetos destructibles.
- El sistema actual de Unity dispone de munición y cargadores, por lo que el jugador debe administrar los disparos disponibles.
- El blaster puede recibir una única mejora denominada *Incremento ilegal de blaster*, que duplica su daño original.
- El arma debe conservarse después de completar el nivel y al recuperar una partida que ya haya registrado su adquisición.

*Entrada:*

- U: disparar con el blaster.
- Recogida del arma: interacción con el objeto soltado por el enemigo; entrada definitiva pendiente de implementar.

*Estado inicial:*

Durante el primer nivel, Jack solamente dispone del brazo mecánico. El blaster permanece bloqueado hasta su adquisición en el segundo nivel.

*Estado final:*

El arma dispara un proyectil que puede impactar contra un enemigo u objeto, provocando daño y actualizando los recursos de munición correspondientes.

*Recursos utilizados:*

Blaster, proyectiles de energía, animaciones de disparo, sistema de daño y munición.

*Recompensa:*

Permite enfrentar enemigos a distancia, ampliar las posibilidades de combate y destruir determinados objetivos sin necesidad de acercarse.

*Penalización:*

El uso del arma requiere administrar su munición según el sistema que se conserve en la versión final. Los momentos de disparo también pueden dejar al jugador expuesto a ataques enemigos.

*Interacciones con otras mecánicas:*

Movimiento, combate cuerpo a cuerpo, salud de enemigos, destrucción de objetos, recolección de recursos y máquina de mejoras.

*Casos límite:*

El jugador no podrá utilizar el blaster antes de adquirirlo. Si Jack muere después de recogerlo, el arma deberá conservarse al reaparecer, siempre que su adquisición se haya registrado correctamente. El enemigo que lo entrega no debe generar múltiples copias del arma.

## Mecánicas secundarias

Las mecánicas secundarias complementan las acciones principales del jugador mediante habilidades especiales, interacciones con el entorno y sistemas de apoyo que permiten afrontar diferentes situaciones.

### Dash

*Propósito:* Permitir que Jack realice un desplazamiento rápido para esquivar ataques, superar distancias cortas y mejorar su movilidad.

*Activación:* El jugador presiona Shift.

*Reglas:* Jack ejecuta un impulso horizontal de corta duración. Después de utilizarlo, debe transcurrir un tiempo de recarga antes de volver a ejecutarlo.

*Estado inicial:* Dash disponible.

*Estado final:* El impulso termina y comienza su tiempo de recuperación.

*Recursos utilizados:* Sistema de movimiento, físicas 2D, animaciones y temporizador de recarga.

*Recompensa:* Mayor movilidad y capacidad para evitar determinados peligros.

*Penalización:* La habilidad no puede utilizarse continuamente mientras se encuentra en recuperación.

*Interacciones con otras mecánicas:* Movimiento, plataformas, combate y evasión.

*Casos límite:* El dash debe interrumpirse apropiadamente cuando Jack muere o entra en un estado incompatible con la habilidad.

### Escalada

*Propósito:* Permitir el desplazamiento vertical mediante cadenas y estructuras específicas del escenario.

*Activación:* El jugador se aproxima a una superficie escalable y utiliza los controles de movimiento vertical.

*Reglas:* Jack puede ascender o descender únicamente cuando se encuentra dentro del área que permite la escalada. Durante esta acción, su movimiento debe adaptarse a las condiciones de la estructura.

*Estado inicial:* Jack se encuentra próximo a una cadena.

*Estado final:* El personaje abandona la estructura y recupera su movimiento habitual.

*Recursos utilizados:* Detección de áreas escalables, físicas 2D y animaciones.

*Recompensa:* Acceso a plataformas elevadas y rutas alternativas.

*Penalización:* Durante la escalada, la movilidad del personaje se encuentra limitada.

*Interacciones con otras mecánicas:* Movimiento, salto, plataformas y mecanismos del escenario.

*Casos límite:* El personaje debe abandonar correctamente el estado de escalada cuando alcanza el extremo de una cadena o se separa de ella.

### Ataque especial y energía

*Propósito:* Complementar el combate físico mediante un ataque especial que requiere administrar una reserva de energía.

*Activación:* El jugador presiona I para ejecutar RayPunch cuando dispone de energía suficiente.

*Reglas:* Determinados ataques físicos permiten recuperar energía al impactar enemigos. El RayPunch consume parte de esta reserva y no puede ejecutarse si la cantidad disponible es insuficiente.

*Estado inicial:* Jack dispone de la energía necesaria para ejecutar el ataque.

*Estado final:* El ataque se realiza y la reserva de energía disminuye.

*Recursos utilizados:* Medidor de energía, animaciones, sistema de combate y parámetros de consumo.

*Recompensa:* Acceso a un ataque especial que amplía las posibilidades ofensivas.

*Penalización:* La energía gastada debe recuperarse mediante las acciones correspondientes.

*Interacciones con otras mecánicas:* Combate cuerpo a cuerpo, daño, HUD y enemigos.

*Casos límite:* El ataque debe impedirse cuando la reserva es insuficiente. La denominación definitiva del recurso debe unificarse, ya que el proyecto utiliza términos relacionados con vapor y aceite.

### Recolección de recursos

*Propósito:* Permitir que el jugador obtenga materiales para adquirir mejoras y fortalecer las capacidades de Jack.

*Activación:* El personaje recoge los recursos que aparecen durante el recorrido, principalmente después de derrotar enemigos.

*Reglas:* Los recursos recolectados se acumulan y pueden utilizarse en la máquina de mejoras. El proyecto utiliza actualmente tuercas como unidad de intercambio.

*Estado inicial:* El recurso se encuentra disponible dentro del escenario.

*Estado final:* El recurso desaparece del entorno y su valor se agrega al total del jugador.

*Recursos utilizados:* Objetos recolectables, contador de tuercas e interfaz.

*Recompensa:* Obtener los materiales necesarios para adquirir mejoras.

*Penalización:* Los recursos gastados disminuyen del total disponible. El sistema actual permite perder temporalmente las tuercas al morir.

*Interacciones con otras mecánicas:* Combate, muerte, máquina de mejoras y progresión.

*Casos límite:* Evitar que un mismo recurso se recoja varias veces. Si se conserva el sistema de bolsa de tuercas, debe impedirse su duplicación al reaparecer.

### Interacción con objetos y mecanismos

*Propósito:* Permitir que Jack utilice elementos del entorno necesarios para avanzar.

*Activación:* El jugador se aproxima a un objeto interactivo y utiliza la acción correspondiente, actualmente E.

*Reglas:* Algunos mecanismos solamente pueden activarse cuando se cumplen determinadas condiciones, como eliminar enemigos, destruir objetos o encontrarse dentro del área de interacción.

*Estado inicial:* El objeto está disponible, desactivado o bloqueado según sus condiciones.

*Estado final:* El mecanismo se activa, cambia de estado o permite continuar el recorrido.

*Recursos utilizados:* Detectores de proximidad, animaciones, componentes interactivos y eventos.

*Recompensa:* Apertura de puertas, activación de elevadores y acceso a nuevas zonas.

*Penalización:* No cumplir los requisitos impide activar determinados mecanismos.

*Interacciones con otras mecánicas:* Exploración, combate, destrucción de objetos y progresión.

*Casos límite:* Evitar activar repetidamente un mecanismo mientras su animación o proceso de transición todavía está ejecutándose.

### Destrucción de objetos

*Propósito:* Permitir que el jugador destruya elementos específicos del escenario para completar objetivos o desbloquear caminos.

*Activación:* Jack utiliza sus ataques contra objetos identificados como destructibles.

*Reglas:* Los objetos cuentan con condiciones de destrucción que deben cumplirse antes de considerarlos eliminados. Durante el segundo nivel, el jugador debe destruir los tres tanques industriales vinculados a la salida.

*Estado inicial:* El objeto permanece intacto y puede recibir daño.

*Estado final:* El objeto queda destruido y se actualiza el progreso del objetivo correspondiente.

*Recursos utilizados:* Sistema de daño, colisiones, animaciones de destrucción y eventos.

*Recompensa:* Cumplimiento de objetivos y desbloqueo de nuevas áreas.

*Penalización:* Los caminos que dependen de su destrucción permanecen bloqueados hasta completar la condición.

*Interacciones con otras mecánicas:* Combate, exploración, misiones y mecanismos.

*Casos límite:* Un objeto destruido no debe registrar nuevamente su destrucción ni incrementar varias veces el contador de objetivos.

### Uso de consumibles

*Propósito:* Proporcionar beneficios de recuperación o fortalecimiento temporal durante los enfrentamientos y la exploración.

*Activación:* El jugador utiliza un consumible disponible.

*Reglas:*

- *Botiquín:* Recupera una cantidad determinada de salud sin superar el máximo permitido.
- *Inyección de adrenalina:* Incrementa temporalmente la velocidad de movimiento y la capacidad de salto de Jack durante 5 segundos.
- *Inyección de carbón activado:* Aumenta la salud total efectiva del personaje en un 20%. Los puntos adicionales absorben daño hasta agotarse. Al perder completamente el beneficio o morir, Jack regresa a su salud máxima normal.

*Estado inicial:* El jugador dispone del consumible correspondiente.

*Estado final:* El objeto se consume y se aplica su efecto durante las condiciones establecidas.

*Recursos utilizados:* Inventario de consumibles, sistema de salud, estadísticas de movimiento y temporizadores.

*Recompensa:* Recuperación de salud o ventajas temporales de supervivencia y movilidad.

*Penalización:* El objeto desaparece del inventario después de su utilización.

*Interacciones con otras mecánicas:* Combate, movimiento, salud, mejoras y muerte.

*Casos límite:* Los efectos temporales deben desaparecer correctamente al finalizar su duración o cumplirse su condición de terminación. La inyección de carbón activado no debe permitir conservar salud adicional después de morir.

### Máquina de mejoras

*Propósito:* Permitir que el jugador fortalezca las capacidades de Jack mediante la utilización de los recursos recolectados.

*Activación:* El jugador interactúa con la máquina de mejoras disponible en el Distrito Industrial.

*Reglas:*

La máquina dispone de dos mejoras principales, cada una con un único nivel de actualización:

1. *Actualización a prótesis de combate:* Incrementa la velocidad de movimiento un 30% (×1.3), la capacidad de salto un 30% (×1.3) y el daño físico un 50% (×1.5).
2. *Incremento ilegal de blaster:* Duplica el daño de la pistola (×2).

Las mejoras deben adquirirse utilizando los recursos necesarios y no pueden comprarse más de una vez. La mejora del blaster requiere que Jack haya obtenido previamente el arma.

*Estado inicial:* Las mejoras están disponibles para adquirir, siempre que se cumplan sus requisitos.

*Estado final:* Se descuentan los recursos correspondientes y se aplican permanentemente los beneficios adquiridos.

*Recursos utilizados:* Tuercas, interfaz de mejoras y estadísticas del personaje.

*Recompensa:* Incremento permanente de las capacidades de combate y movimiento.

*Penalización:* Consumo de los recursos necesarios para adquirir cada actualización.

*Interacciones con otras mecánicas:* Combate físico, blaster, movimiento, salto, recolección de recursos y guardado.

*Casos límite:* Las mejoras adquiridas no deben aplicarse varias veces ni desaparecer al cambiar de nivel o recuperar una partida guardada.

### Checkpoints y reaparición

*Propósito:* Permitir que el jugador continúe su progreso después de perder una vida, evitando repetir completamente las secciones superadas.

*Activación:* El jugador activa un checkpoint durante el recorrido. Cuando su salud llega a cero, se ejecuta la secuencia de derrota.

*Reglas:* Al morir, Jack pierde una oportunidad. Si dispone de oportunidades restantes, puede reaparecer en el último checkpoint activado. Cuando estas se agotan, debe regresar al menú principal.

*Estado inicial:* Jack se encuentra jugando, con salud y oportunidades disponibles.

*Estado final:* El personaje reaparece en un checkpoint válido o termina su intento.

*Recursos utilizados:* Sistema de salud, checkpoints, oportunidades, interfaz de derrota y datos de progreso.

*Recompensa:* Continuar desde una sección alcanzada anteriormente.

*Penalización:* Pérdida de una oportunidad y de los beneficios temporales que deban eliminarse al morir.

*Interacciones con otras mecánicas:* Salud, consumibles, progresión, guardado y recuperación de partida.

*Casos límite:* Si Jack muere antes de activar un checkpoint, debe utilizarse el punto inicial del nivel. Las oportunidades restantes y el último checkpoint válido deben registrarse correctamente cuando se implemente el sistema de guardado definitivo.

Esta mecánica corresponde al flujo de juego previsto y todavía requiere implementación en Unity.