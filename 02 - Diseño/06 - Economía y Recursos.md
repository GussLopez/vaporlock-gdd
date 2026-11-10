06 - Economia y Recursos

# Economía y Recursos

## Descripción de la sección

La economía de **Vaporlock** comprende los recursos que Jack Veil puede obtener, utilizar y administrar durante su recorrido por Metronia. Estos recursos permiten recuperar salud, ejecutar habilidades especiales, utilizar armas y adquirir mejoras que facilitan la superación de los desafíos del videojuego.

El sistema utiliza principalmente **tuercas** como recurso de intercambio, las cuales pueden obtenerse al derrotar enemigos y utilizarse en la máquina de mejoras.

Además, el videojuego contempla otros recursos como la salud, energía de combate, munición, consumibles y oportunidades, los cuales influyen directamente en la supervivencia y progresión del jugador.

La administración de estos elementos busca fomentar la exploración, el combate estratégico y el aprovechamiento de los recursos disponibles, sin convertir su recolección en una actividad obligatoria que interrumpa el desarrollo de la aventura.

## Recursos

| Recurso | Obtención | Uso | Límite | Pérdida |
|---|---|---|---|---|
| Tuercas | Derrotar enemigos y recoger sus recompensas. | Comprar mejoras permanentes. | Por definir. | Al comprar mejoras o morir, según el sistema de recuperación. |
| Salud | Salud inicial, reaparición y botiquines. | Resistir ataques y peligros. | 80 HP base actualmente. | Al recibir daño. |
| Energía | Conectar determinados ataques físicos. | Ejecutar RayPunch. | Por definir. | Al utilizar el ataque especial. |
| Munición | Disponible con el blaster; fuentes de recarga por confirmar. | Disparar proyectiles. | Por definir. | Al disparar. |
| Botiquín | Recolección en el escenario. | Recuperar salud. | Por definir. | Al utilizarlo. |
| Inyección de adrenalina | Recolección en el escenario. | Aumentar velocidad y salto durante 5 segundos. | Por definir. | Al utilizarla. |
| Inyección de carbón activado | Recolección en el escenario. | Incrementar temporalmente la salud máxima en un 20%. | Por definir. | Al utilizarla. |
| Oportunidades | Disponibles al iniciar o recuperar una partida. | Permitir reaparecer después de morir. | Por definir. | Se pierde una por muerte. |

## Fuentes y sumideros

### Fuentes

Las fuentes representan las acciones mediante las cuales el jugador obtiene recursos durante la aventura.

**Derrotar enemigos:** Algunos enemigos pueden dejar caer tuercas al ser eliminados. Estas pueden recogerse y acumularse para adquirir mejoras.

**Recolectar objetos:** Durante la exploración, el jugador podrá encontrar botiquines e inyecciones que proporcionan beneficios de recuperación o fortalecimiento temporal.

**Recuperar recursos:** El proyecto actual permite recuperar las tuercas perdidas al morir mediante una bolsa que permanece en el lugar de la derrota.

**Generar energía:** Determinados ataques cuerpo a cuerpo permiten recuperar energía que posteriormente puede utilizarse para ejecutar RayPunch.

**Obtener equipamiento:** Al comenzar el segundo nivel, el primer enemigo derrotado deja caer el blaster. Una vez recogido, pasa a formar parte permanente del equipamiento de Jack.

### Sumideros

Los sumideros representan las acciones o acontecimientos que consumen recursos.

**Máquina de mejoras:** El jugador utiliza tuercas para adquirir la actualización a prótesis de combate o el incremento ilegal de blaster.

**Combate:** Los ataques especiales consumen energía y los disparos utilizan munición.

**Daño recibido:** Los ataques enemigos y peligros del escenario disminuyen la salud de Jack.

**Uso de consumibles:** Los botiquines y las inyecciones se consumen al utilizarse.

**Muerte:** Al perder toda su salud, Jack pierde una oportunidad y los efectos temporales activos. El sistema actual también contempla la pérdida recuperable de tuercas.

## Reglas

### Administración de tuercas

Las tuercas constituyen la unidad de intercambio principal de Vaporlock.

El jugador puede obtenerlas al derrotar determinados enemigos y utilizarlas en la máquina de mejoras, ubicada en el Distrito Industrial.

La máquina cuenta únicamente con dos actualizaciones:

**1. Actualización a prótesis de combate**

- Velocidad de movimiento: ×1.3 (+30%).
- Capacidad de salto: ×1.3 (+30%).
- Daño físico: ×1.5 (+50%).

**2. Incremento ilegal de blaster**

- Daño del blaster: ×2 (+100%).

Cada mejora puede adquirirse una sola vez y mantiene sus beneficios durante el resto de la partida.

Las mejoras requieren una cantidad determinada de tuercas. Sus costos definitivos todavía están pendientes de establecerse.

Si el jugador no dispone de recursos suficientes, la máquina no permite realizar la compra.

La mejora del blaster requiere que Jack haya obtenido previamente la pistola.

### Administración de salud

La salud determina la cantidad de daño que Jack puede recibir antes de morir.

Actualmente, el personaje dispone de **80 puntos de salud máxima base** en la configuración de Unity.

Cuando recibe daño, su salud disminuye según el ataque recibido. Si llega a cero, el personaje muere.

Los botiquines permiten recuperar salud perdida, sin superar el máximo establecido.

La cantidad definitiva que recupera cada botiquín permanece por definir. El proyecto actual dispone de un frasco de aceite que restaura 35 HP, pero este objeto deberá adaptarse al diseño definitivo del botiquín.

### Inyección de adrenalina

La inyección de adrenalina proporciona un aumento temporal de la velocidad de movimiento y capacidad de salto de Jack.

Su efecto dura **5 segundos**, después de los cuales el personaje recupera sus estadísticas correspondientes.

Los porcentajes exactos de aumento todavía están pendientes de definir.

El efecto no representa una mejora permanente y debe desaparecer al finalizar su duración o cuando Jack muera.

También queda pendiente determinar el comportamiento de una segunda inyección utilizada mientras la primera permanece activa.

### Inyección de carbón activado

La inyección de carbón activado incrementa temporalmente la salud máxima de Jack en un **20% respecto a su salud máxima base**.

Con la configuración actual de 80 HP, el beneficio proporciona 16 puntos adicionales, permitiendo alcanzar un máximo temporal de 96 HP.

El daño recibido consume primero la salud adicional. Cuando esta se agota, Jack vuelve a disponer únicamente de su salud máxima normal.

Si el daño supera la cantidad de salud adicional restante, el excedente se descuenta de la salud normal.

El beneficio también desaparece cuando Jack muere, por lo que reaparece sin el incremento temporal.

Los botiquines no restauran automáticamente la reserva adicional ya consumida.

### Administración de energía

Jack dispone de una reserva de energía utilizada principalmente para ejecutar el ataque especial RayPunch.

Esta energía puede acumularse mediante determinados ataques físicos contra enemigos.

Cada ejecución del ataque especial consume una cantidad determinada de energía.

Cuando la reserva disponible resulta insuficiente, el jugador no puede ejecutar la habilidad hasta recuperar la cantidad necesaria.

La capacidad máxima y el costo exacto del ataque deberán verificarse antes de establecer sus valores definitivos en el GDD.

### Administración de munición

El blaster utiliza proyectiles para atacar enemigos y determinados objetos destructibles.

El sistema actual de Unity contempla cargadores y recarga de munición.

Cada disparo consume munición disponible, por lo que el jugador debe administrar su uso durante los enfrentamientos.

La capacidad de los cargadores, la reserva máxima y las fuentes de obtención de munición todavía requieren confirmación para el diseño definitivo.

La mejora Incremento ilegal de blaster duplica el daño de los disparos, pero no modifica automáticamente la capacidad de munición.

### Pérdida de recursos y oportunidades

Cuando Jack pierde toda su salud, se activa la secuencia de derrota.

De acuerdo con el flujo de juego previsto, cada muerte consume una oportunidad.

Si todavía dispone de oportunidades, el jugador puede reaparecer en el último checkpoint activado.

Cuando las oportunidades se agotan, la partida entra en estado de Game Over y el jugador debe regresar al menú principal.

El proyecto actual de Unity también contempla la pérdida temporal de tuercas, que pueden recuperarse al regresar al lugar donde murió el personaje.

La integración definitiva de este comportamiento con los checkpoints y las oportunidades está pendiente de implementación.

Las armas adquiridas y mejoras permanentes deberán conservarse al reaparecer, mientras que las bonificaciones temporales deben eliminarse según sus reglas.

### Persistencia de recursos

El sistema de guardado previsto debe conservar los recursos y elementos permanentes necesarios para continuar una partida.

Esto comprende principalmente las tuercas, el armamento adquirido, las mejoras permanentes y los datos correspondientes a la progresión.

También deben registrarse el nivel, checkpoint y oportunidades restantes.

La persistencia exacta de los consumibles y munición todavía requiere definirse.

El almacenamiento actual de Unity utiliza parcialmente datos serializados como JSON, pero todavía debe adaptarse al sistema completo de guardado y recuperación de partidas.

## Balance

### ¿Qué comportamiento queremos incentivar?

La economía de Vaporlock busca incentivar la exploración, el combate estratégico y la administración responsable de los recursos.

El jugador debe sentirse recompensado por derrotar enemigos, recolectar tuercas y aprovechar las oportunidades disponibles para fortalecer a Jack.

Las mejoras permiten adaptar su rendimiento a diferentes situaciones: la actualización de prótesis beneficia la movilidad y los ataques físicos, mientras que el incremento ilegal de blaster fortalece el combate a distancia.

Los consumibles proporcionan ventajas que pueden utilizarse durante enfrentamientos difíciles, incentivando al jugador a elegir los momentos más adecuados para aprovecharlos.

También se busca que el jugador comprenda las consecuencias de sus decisiones, especialmente al administrar salud, energía y munición.

### ¿Qué comportamiento queremos evitar?

El sistema debe evitar que el jugador dependa excesivamente de la recolección de recursos para avanzar.

Las mejoras deben resultar útiles, pero no convertirse en requisitos obligatorios para completar los niveles.

Tampoco se busca fomentar la repetición innecesaria de enfrentamientos únicamente para acumular tuercas, especialmente considerando la duración relativamente corta de los escenarios.

Los consumibles no deben eliminar completamente el desafío de los enemigos ni permitir acumular beneficios desproporcionados.

Asimismo, deben evitarse situaciones en las que el jugador pierda recursos de manera injustificada, pueda adquirir mejoras repetidamente o quede bloqueado por falta de munición o consumibles.

El balance definitivo de los recursos deberá ajustarse mediante pruebas de juego, considerando la cantidad de enemigos, la disponibilidad de objetos, los costos de las mejoras y la dificultad de cada nivel.

---

**Navegación:** [[00 - Índice]] · ← [[05 - Progresión]] · [[07 - Reglas y Estados del Juego]] →