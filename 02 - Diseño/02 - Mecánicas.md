# Mecánicas

## Descripción de la sección

Las mecánicas de **Vaporlock** definen las acciones y reglas que permiten a Jack Veil explorar, desplazarse, combatir e interactuar con el entorno. Cada una establece condiciones de activación, resultados y relaciones con el resto de la experiencia jugable.

## Plantilla de mecánica

Para cada mecánica se define: **propósito, activación, reglas, entrada, estado inicial, estado final, recursos utilizados, recompensa, penalización, interacciones con otras mecánicas y casos límite**.

## Mecánicas principales

### Mecánica 01 — Desplazamiento y plataformas

**Propósito:** Permitir a Jack desplazarse por los niveles, cruzar obstáculos y alcanzar zonas elevadas.

**Activación:** El jugador controla horizontalmente a Jack y pulsa salto cuando las condiciones del personaje lo permiten.

**Reglas:** El desplazamiento se realiza en un plano 2D; el salto depende del contacto con suelo y de las condiciones físicas. Pendientes, gravedad, plataformas móviles y cadenas modifican el movimiento. El dash ofrece un desplazamiento breve con enfriamiento. Mientras Jack está inmovilizado por daño, ciertas animaciones o interacción, su movimiento puede limitarse.

**Entrada:** `A/D` o flechas izquierda/derecha para movimiento, `Espacio` para salto y `Shift` para dash. `W/S` o flechas verticales intervienen con la escalada cuando Jack está cerca de una cadena.

**Estado inicial:** Jack puede moverse, siempre que no esté muerto, aturdido o bloqueado por otra acción.

**Estado final:** Jack aterriza, se detiene o completa el desplazamiento, o cae a una zona letal.

**Recursos utilizados:** Físicas 2D, detección de suelo, parámetros de velocidad/salto, animaciones y enfriamiento de dash.

**Recompensa:** Avance espacial, evasión y acceso a nuevas secciones.

**Penalización:** Una caída o el contacto con un peligro puede causar daño o muerte.

**Interacciones con otras mecánicas:** Combate, escalada, obstáculos, elevador, dash, adrenalina y mejora de prótesis.

**Casos límite:** No permitir saltos adicionales accidentales; impedir dash ilimitado; conservar comportamiento predecible en bordes, pendientes y plataformas móviles; evitar que los efectos de velocidad queden activos después de morir.

### Mecánica 02 — Combate cuerpo a cuerpo con brazo mecánico

**Propósito:** Permitir que Jack derrote enemigos próximos usando sus prótesis, sin requerir armas externas.

**Activación:** El jugador pulsa el ataque correspondiente durante el desplazamiento o cuando está frente a un enemigo.

**Reglas:** Jack comienza el juego con el **brazo mecánico** como arma principal. El sistema contiene una secuencia de hasta cuatro golpes, ataque aéreo, Uppercut, CrossKick y un ataque especial RayPunch. Las acciones se encuentran sujetas a ventanas de animación, estados de daño y reglas de transición entre golpes. El daño físico puede aumentar mediante la **Actualización a prótesis de combate** (×1.5; un solo nivel).

**Entrada:** `J` (combo básico), `K` (Uppercut), `L` (CrossKick), `I` (RayPunch); también puede utilizarse `Enter` o clic izquierdo para el ataque principal.

**Estado inicial:** Jack está activo, sin bloqueo de ataque, y dispone de las condiciones necesarias para la acción solicitada.

**Estado final:** Se ejecuta la animación, se verifica contacto, se aplica daño o se registra un ataque fallido; el personaje vuelve a un estado disponible.

**Recursos utilizados:** Animaciones, hitboxes, datos de ataque, reserva de energía y salud de los objetivos.

**Recompensa:** Infligir daño, conseguir recursos de enemigos y recuperar energía al acertar golpes cuando corresponda.

**Penalización:** Atacar fuera de rango deja a Jack expuesto; el RayPunch gasta energía y no se ejecuta si es insuficiente.

**Interacciones con otras mecánicas:** Movimiento, caída, dash, salud, IA enemiga, energía y mejora de prótesis.

**Casos límite:** Evitar múltiples impactos indebidos al mismo objetivo por un golpe; cancelar ataques apropiadamente al recibir daño; no permitir ataques estando muerto o bloqueado; verificar la persistencia de mejoras tras reaparición.

### Mecánica 03 — Combate a distancia con blaster

**Propósito:** Ofrecer un segundo estilo de combate, con ataques a distancia que complementan el brazo mecánico.

**Activación:** Al inicio del Nivel 2, Jack derrota al **primer enemigo** y recoge la pistola que este deja caer. Desde ese momento, el blaster queda disponible permanentemente como arma predeterminada secundaria.

**Reglas:** Antes de recoger la pistola no puede dispararse. Una vez adquirida, puede utilizarse en los niveles restantes, con las restricciones de munición y recarga. La mejora **Incremento ilegal de blaster** duplica su daño (×2) una sola vez; no modifica el brazo mecánico.

**Entrada:** `U` para disparar y acción de recoger para adquirir el arma.

**Estado inicial:** Blaster bloqueado hasta obtener el objeto.

**Estado final:** Proyectil disparado, daño aplicado cuando impacta y munición actualizada según las reglas activas.

**Recursos utilizados:** Proyectiles de plasma, animaciones, munición y variable de daño a distancia.

**Recompensa:** Alcance superior, nuevas posibilidades tácticas y daño duplicado si se adquiere la mejora.

**Penalización:** Tiempo de recarga y consumo de munición y limitación de movimiento durante ciertas animaciones de disparo.

**Interacciones con otras mecánicas:** IA, salud de enemigos, objetos destructibles, guardado, HUD y máquina de mejoras.

**Casos límite:** Garantizar que el primer enemigo entregue el arma exactamente una vez; permitir recuperarla después de una muerte antes de recogerla; conservarla tras checkpoints, cambios de nivel y carga de partida; impedir comprar una pistola ya obtenida.

## Mecánicas secundarias

### Dash

**Propósito:** Evasión o movilidad breve. **Activación / entrada:** `Shift`. **Reglas:** impulso de duración limitada y enfriamiento; velocidad 15, duración 0.2 s y recarga 1 s. **Estado inicial/final:** listo → desplazamiento → enfriamiento → listo. **Recompensa:** evita peligros y facilita desplazamientos. **Penalización:** no puede encadenarse sin esperar. **Interacción:** movimiento, daño y plataformas. **Caso límite:** no reutilizarlo durante la recarga.

### Escalada de cadenas

**Propósito:** Acceder a alturas industriales. **Activación / entrada:** aproximarse a una cadena y utilizar movimiento vertical. **Reglas:** depende de proximidad y estado del jugador. **Estado inicial/final:** cerca de cadena → escalando → salida por extremo o salto. **Recursos:** áreas escalables, física y animación. **Recompensa:** acceso vertical. **Penalización:** vulnerabilidad frente a peligros. **Interacción:** salto, combate y elevador. **Caso límite:** evitar engancharse repetidamente al salir.

### RayPunch y energía de combate

**Propósito:** Introducir decisiones sobre ataques especiales. **Activación / entrada:** `I` con suficiente energía. **Reglas:** Jack dispone de una reserva de energía que aumenta al conectar determinados golpes y disminuye al ejecutar el ataque. **Estado inicial/final:** reserva disponible → gasto → ataque → recarga posterior. **Recompensa:** ataque especial. **Penalización:** no usarlo sin energía suficiente. **Interacción:** combo, HUD y sistema de daño. **Caso límite:** la interfaz utiliza una denominación consistente para la energía.

### Interacción con mecanismos

**Propósito:** Activar elementos del escenario. **Activación / entrada:** acercarse e interactuar con `E`. **Reglas:** solo interactuar con objetivos accesibles y habilitados. **Estado inicial/final:** objeto inactivo/bloqueado → interacción válida → acción o transición. **Recompensa:** utilizar elevador, máquina de mejoras o puerta. **Penalización:** imposibilidad temporal si no se cumple el requisito. **Interacción:** objetivos, salud de tanques, nivel actual y HUD. **Caso límite:** pulsaciones repetidas no deben abrir dos interfaces ni cargar dos escenas.

### Destrucción de objetivos industriales

**Propósito:** Convertir el combate en una condición de progreso del nivel 2. **Activación:** dañar los tres tanques vinculados a la puerta del Obelisco. **Reglas:** los tres deben quedar destruidos para desbloquear la salida. **Estado inicial/final:** tanques intactos → destruidos → puerta disponible. **Recompensa:** acceso al próximo nivel. **Penalización:** ruta bloqueada hasta cumplir el objetivo. **Interacción:** armas, efectos y mecanismo de desbloqueo de la salida. **Caso límite:** no contabilizar dos veces el mismo tanque.

### Uso de botiquín

**Propósito:** Recuperar salud. **Activación:** consumir un botiquín disponible. **Reglas:** no superar la salud máxima vigente. **Estado inicial/final:** salud dañada → curación → consumo de unidad. **Recompensa:** resistencia adicional. **Penalización:** pierde el consumible. **Interacción:** salud, HUD e inventario. **Caso límite:** evitar consumo accidental al estar al máximo.

### Inyección de adrenalina

**Propósito:** Mejorar movilidad durante un periodo breve. **Activación:** consumir una inyección. **Reglas:** Jack corre más rápido y salta más alto durante **5 segundos**, sin reemplazar la mejora permanente de prótesis. **Estado inicial/final:** valores vigentes → boost activo → regreso automático a valores anteriores. **Recompensa:** facilitar escape o plataformas. **Penalización:** consumo del objeto. **Interacción:** velocidad, salto y mejora ×1.3. **Casos límite:** una segunda aplicación no acumula el bono mientras el efecto está activo; al morir se cancela.

### Inyección de carbón activado

**Propósito:** Otorgar una reserva temporal de salud. **Activación:** consumir la inyección. **Reglas:** incrementa la salud máxima efectiva en **20%** respecto de la salud máxima base vigente. Los puntos extra absorben daño hasta agotarse; entonces se pierde el incremento. Morir cancela el efecto y Jack reaparece con salud normal. **Estado inicial/final:** salud normal → +20% temporal → absorción del bono o muerte → salud normal. **Recompensa:** mayor supervivencia. **Penalización:** consumible gastado. **Interacción:** daño, HUD, respawn y botiquín. **Caso límite:** evitar bonificaciones duplicadas y que la vida normal permanezca inflada.

### Checkpoints y oportunidades

**Propósito:** Reducir repetición y ofrecer consecuencias comprensibles a la muerte. **Activación:** alcanzar/activar un checkpoint; morir cuando se tiene una oportunidad. **Reglas:** registrar la posición y nivel del checkpoint, descontar una oportunidad por muerte y elegir respawn o Game Over según saldo. **Estado inicial/final:** jugando → derrota → reaparecer o menú. **Recompensa:** continuidad desde una zona alcanzada. **Penalización:** pérdida de oportunidad y, si aplica, recursos temporales. **Interacción:** salud, guardado JSON, inventario y UI. **Caso límite:** cada muerte descuenta solo una oportunidad y la reaparición respeta el punto de control válido.

### Mejoras de la máquina

**Propósito:** Fortalecer a Jack mediante inversión de recursos. **Activación:** interactuar con la máquina, ubicada en el nivel 2. **Reglas:** **Actualización a prótesis de combate** (movimiento ×1.3, salto ×1.3, daño físico ×1.5) e **Incremento ilegal de blaster** (daño del blaster ×2); máximo una compra por mejora. La segunda debe exigir que Jack ya tenga el blaster. **Estado inicial/final:** mejora disponible → compra validada → mejora aplicada y persistente. **Recompensa:** aumento de capacidades. **Penalización:** gasto de tuercas. **Interacción:** economía, estadísticas y guardado. **Casos límite:** evitar compras duplicadas, restaurar mejoras tras carga y aplicar los costos establecidos para cada mejora.

> **Navegación:** [[00 - Índice]] · ← [[01 - Jugabilidad]] · [[03 - Sistemas]] →
