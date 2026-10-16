# Enemigos y NPC

## Descripción de la sección

Documenta las entidades controladas por el juego y su comportamiento.

## Plantilla de enemigo

### Lucius Corr

**Rol de combate:** Jefe de Vaporis Industries 

**Comportamiento:** Lucius Corr es un jefe que evita el combate directo y utiliza su tecnología para defenderse. Durante el enfrentamiento, se desplaza lentamente por el escenario mientras invoca robots que atacan al jugador. Su estrategia consiste en mantener la distancia y utilizar a sus máquinas para impedir que el jugador se acerque. Cuando sus robots son destruidos, Lucius queda vulnerable durante un breve periodo antes de invocar nuevos enemigos.

**Vida:** 2 puntos de vida.

**Daño:** 2 puntos de daño (infligidos por los robots que invoca).

**Defensas:** Ninguna.

**Velocidad:** Lenta.

**Rango de detección:** Alto.

**Ataques:** 
- Invocación de robots: Invoca robots de Vaporis Industries que persiguen y atacan al jugador.
- Refuerzos mecánicos: Cuando los robots son destruidos, Lucius invoca nuevos enemigos después de un breve intervalo.

**Debilidades:** Aunque no tiene debilidades especiales, Lucius queda vulnerable cuando sus robots son destruidos, permitiendo que el jugador se acerque y lo ataque directamente.

**Recompensa:** Derrotar a Lucius Corr y liberar a la ciudad del control de Vaporis Industries, completando la historia principal del videojuego.

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

**Nombre:** Doctor

**Función:** Informar al jugador de la historia

**Ubicación:** Hospital

**Interacción:** Dialogo con el jugador principal

**Diálogos:** 

**Condiciones:** Ninguna

**Recompensas / información:** 



> **Navegación:** [[00 - Índice]] · ← [[02 - Niveles]] · [[04 - Objetos y Coleccionables]] →
