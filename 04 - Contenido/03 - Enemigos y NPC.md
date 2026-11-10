# Enemigos y NPC

## Descripción de la sección

Documenta las entidades controladas por el juego y su comportamiento.

## Plantilla de enemigo

### Sentinela Beta-32

**Rol de combate:** Enemigo básico de vigilancia y combate cuerpo a cuerpo.

**Comportamiento:** Recorre o vigila un tramo del escenario y se aproxima a Jack cuando entra en su rango de detección. Busca atacarlo a corta distancia. Es una amenaza de baja dificultad y sirve para enseñar los fundamentos del combate.

**Vida:** Por definir mediante pruebas de balance; resistencia baja.

**Daño:** Por definir.

**Defensas:** Sin protección especial establecida.

**Velocidad:** Moderada.

**Rango de detección:** Corto o medio.

**Ataques:** Golpe cuerpo a cuerpo cuando el jugador se encuentra cerca.

**Debilidades:** Debe acercarse para atacar y no dispone de ataques a distancia.

**Recompensa:** Liberar el paso hacia la siguiente zona; no se ha definido recompensa material.

**Estados de IA:** Inactivo/Patrulla → Detección/Persecución → Ataque → Retorno a patrulla o Derrota.

### Sentinela Alpha-34

**Rol de combate:** Enemigo básico de vigilancia y combate cuerpo a cuerpo.

**Comportamiento:** Recorre o vigila un tramo del escenario y se aproxima a Jack cuando entra en su rango de detección. Busca atacarlo a corta distancia. Es una amenaza de baja dificultad y sirve para enseñar los fundamentos del combate.

**Vida:** Por definir mediante pruebas de balance; resistencia baja.

**Daño:** Por definir.

**Defensas:** Sin protección especial establecida.

**Velocidad:** Moderada.

**Rango de detección:** Corto o medio.

**Ataques:** Golpe cuerpo a cuerpo cuando el jugador se encuentra cerca.

**Debilidades:** Debe acercarse para atacar y no dispone de ataques a distancia.

**Recompensa:** Liberar el paso hacia la siguiente zona; no se ha definido recompensa material.

**Estados de IA:** Inactivo/Patrulla → Detección/Persecución → Ataque → Retorno a patrulla o Derrota.

### Cyborg Omega-06

**Rol de combate:** Enemigo de ataque a distancia.

**Comportamiento:** Detecta a Jack desde una distancia mayor que el enemigo básico y dispara proyectiles hacia su posición. Obliga al jugador a acercarse, esquivar o utilizar su propio blaster.

**Vida:** Por definir.

**Daño:** Por definir.

**Defensas:** Por definir; no se contempla una defensa especial de forma predeterminada.

**Velocidad:** Lenta o moderada, sujeta a balance.

**Rango de detección:** Medio o alto.

**Ataques:** Disparo de proyectil a distancia.

**Debilidades:** Puede ser alcanzado al acortar la distancia o durante el intervalo entre disparos.

**Recompensa:** Despejar las zonas vigiladas; sin recompensa material establecida.

**Estados de IA:** Inactivo/Patrulla → Detección → Ataque a distancia → Espera entre disparos → Derrota.

### Dron Epsilon-21

**Rol de combate:** Enemigo aéreo de bombardeo, de aparición poco frecuente.

**Comportamiento:** Se mantiene sobre el área de juego y arroja bombas hacia las plataformas o la zona ocupada por Jack. Su principal función es añadir presión al movimiento sin aparecer con tanta frecuencia como los enemigos terrestres.

**Vida:** Por definir.

**Daño:** Por definir.

**Defensas:** Por definir.

**Velocidad:** Por definir.

**Rango de detección:** Medio o alto.

**Ataques**: Lanzamiento de bombas o granadas.

**Debilidades:** Sus ataques deben ser anticipables visualmente para que Jack pueda esquivarlos.

**Recompensa:** Reducir el peligro de la zona; no se ha definido botín.

**Estados de IA:** Patrulla aérea → Detección → Preparación del lanzamiento → Bombardeo → Espera → Derrota.

### Lucius Corr

**Rol de combate:** Jefe final y líder de Vaporis Industries.

**Comportamiento:** Evita el combate directo y utiliza robots para protegerse. Se desplaza lentamente mientras invoca refuerzos que atacan a Jack. Cuando sus robots son destruidos, queda vulnerable durante un breve intervalo; después puede volver a invocarlos.

**Vida:** 2 puntos de vida.

**Daño:** 2 puntos de daño atribuidos a sus robots, de acuerdo con la especificación actual; debe comprobarse durante el balance.

**Defensas:** Ninguna defensa propia; depende de la protección de sus robots.

**Velocidad:** Lenta.

**Rango de detección:** Alto.

**Ataques:** Invocación de robots y nuevos refuerzos después de un intervalo de espera.

**Debilidades:** Queda vulnerable cuando ya no tiene robots activos protegiéndolo.

**Recompensa:** Concluir el enfrentamiento final y la historia principal.

**Estados de IA:**

| Estado                  | Descripción                                                                              |
| ----------------------- | ---------------------------------------------------------------------------------------- |
| Inactivo (Idle)         | Lucius permanece en espera hasta detectar al jugador o comenzar el enfrentamiento.       |
| Invocación (Summon)     | Invoca robots para defenderse y atacar al jugador.                                       |
| Evasión (Evade)         | Se desplaza lentamente para mantener la distancia con el jugador.                        |
| Espera (Cooldown)       | Espera un intervalo antes de poder invocar nuevos robots.                                |
| Vulnerable (Vulnerable) | Al quedarse sin robots, puede recibir daño directamente del jugador.                     |
| Derrotado (Death)       | Al perder sus 2 puntos de vida, termina el combate y se activa la secuencia de victoria. |
## Plantilla de NPC

Doctor
Nombre: Doctor.

Función: Informar al jugador sobre el estado físico de Jack Veil y su recuperación tras recibir prótesis mecánicas.

Ubicación: Hospital, en la cinemática introductoria.

Interacción: Narrativa automática; comunica información a Jack, pero este no responde verbalmente.

Diálogos (propuesta editable): «Logramos salvarte. Tus prótesis mecánicas te permitirán volver a moverte, pero tendrás que acostumbrarte a ellas».

Condiciones: Aparece al comenzar una nueva partida.

Recompensas / información: Presentación de las circunstancias del protagonista y justificación narrativa de sus prótesis.
Tecnócrata
Nombre: Tecnócrata.

Función: Orientar a Jack y establecer el objetivo inicial de llegar a las instalaciones de Vaporis Industries.

Ubicación: Hospital, en la cinemática introductoria.

Interacción: Narrativa automática; habla con Jack sin que el protagonista tenga diálogos.

Diálogos (propuesta editable): «Los accesos principales están vigilados. Si cruzas los tejados de Metronia, podrás llegar al Distrito Industrial».

Condiciones: Aparece durante la cinemática de inicio de la partida.

Recompensas / información: Orientación sobre la ruta al Nivel 1 y el objetivo de infiltración.
Consideraciones generales
- Jack Veil es un protagonista silencioso en todos los niveles.
- Los NPC aliados se limitan por ahora a la introducción; no se han definido misiones secundarias otorgadas mediante conversación.
- No se ha establecido un sistema de botín para derrotar enemigos.
- Los valores de vida, daño y tiempos de ataque pendientes deben definirse a partir de pruebas de juego.




> **Navegación:** [[00 - Índice]] · ← [[02 - Niveles]] · [[04 - Objetos y Coleccionables]] →
