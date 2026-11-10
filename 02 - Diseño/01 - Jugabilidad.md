# Jugabilidad

## Descripción de la sección

La jugabilidad de **Vaporlock** se centra en guiar a Jack Veil a través de escenarios de plataformas 2D de estética steampunk futurista, combinando desplazamiento, combate, obstáculos industriales y recursos que facilitan su avance. La experiencia está organizada en tres niveles: **Tejados de Metronia**, **Distrito Industrial** y **El Obelisco**.

La aventura comienza con una breve presentación de Jack Veil y continúa directamente en los Tejados de Metronia. Jack es un protagonista silencioso y los objetivos se comunican mediante el entorno y la interfaz.

## Bucle principal de juego

El bucle combina exploración, peligro, resolución y progresión. Jack identifica la ruta, supera obstáculos, combate, obtiene recursos y utiliza las recompensas para continuar hacia el siguiente desafío.

**Bucle principal:**

```text
Explorar escenario → Identificar obstáculo o enemigo → Moverse y combatir
→ Recoger recursos / activar mecanismos → Alcanzar punto de control
→ Superar objetivo de salida → Desbloquear siguiente etapa → Explorar
```

**Flujo general de la partida:**

```text
Ejecutar Vaporlock → Menú principal
├── Nueva partida → Presentación inicial de Jack
└── Continuar partida → Cargar datos JSON y ubicación guardada
          ↓
Nivel 1: Tejados de Metronia → Nivel 2: Distrito Industrial
          ↓                         ↓
   Plataformas, combate       Blaster + estación de mejoras
   y puerta industrial        + elevador + 3 tanques
          └──────────────┬──────────┘
                         ↓
                Nivel 3: El Obelisco
                   Jefe Lucius Corr
                         ↓
                Victoria → Créditos
```

**Si Jack muere:** aparece una pantalla de derrota y se descuenta una oportunidad. Si aún dispone de oportunidades, reaparece en el último checkpoint válido; si se agotan, accede al estado de Game Over y puede regresar al menú principal. La cantidad inicial de oportunidades se establece en el balance de la partida.

## Acciones principales del jugador

| Acción | Propósito | Resultado esperado |
|---|---|---|
| Caminar y correr según el desplazamiento disponible | Avanzar por pasillos y plataformas | Cambiar de posición y alcanzar nuevas zonas. |
| Saltar | Cruzar huecos y superar diferencias de altura | Acceder a superficies seguras o evitar peligros. |
| Ejecutar dash | Esquivar o atravesar secciones breves con rapidez | Desplazamiento corto sujeto a enfriamiento. |
| Trepar cadenas | Superar desniveles industriales | Acceder a otra parte del escenario. |
| Golpear con el brazo mecánico | Eliminar amenazas cercanas | Infligir daño y encadenar ataques. |
| Utilizar RayPunch | Consumir energía para un ataque especial | Infligir un ataque potente cuando hay energía suficiente. |
| Disparar con el blaster | Enfrentar amenazas a distancia | Dañar enemigos y objetivos destructibles tras obtener el arma. |
| Interactuar | Usar puertas, terminales o la máquina de mejoras | Activar mecanismos o abrir interfaces. |
| Recoger tuercas / recursos | Reunir materiales durante el recorrido | Acumular recursos para las dos mejoras. |
| Usar consumibles | Recuperar vida o obtener ventajas temporales | Curación, impulso breve de movilidad o salud adicional. |
| Activar checkpoints | Registrar un punto seguro de regreso | Establecer lugar de reaparición y posible guardado. |

## Experiencia segundo a segundo

¿Qué hace el jugador durante los primeros momentos?

1. Identifica a Jack, el HUD, la dirección del trayecto y las plataformas iniciales.
2. Prueba movimiento, salto y golpes con el brazo mecánico, su único armamento al comenzar.
3. Observa enemigos y peligros, ajustando el ritmo de desplazamiento y el momento de ataque.
4. Recibe respuestas inmediatas: animación, sonido, variación de salud/energía y reacción del enemigo.
5. Reconoce señales visuales de interacción y avanza hacia los objetivos del escenario.

La presentación previa al juego introduce al protagonista antes de que el jugador tome el control de Jack.

## Experiencia minuto a minuto

¿Qué actividades se repiten durante una sesión?

- **Nivel 1:** recorrer azoteas, superar huecos y plataformas, enfrentar Sentinelas, recolectar materiales y cumplir el combate que desbloquea la puerta industrial. Los checkpoints registran puntos de reaparición.
- **Nivel 2:** derrotar al primer enemigo para obtener el blaster; acceder a la máquina de mejoras, usar cadenas y elevador, combatir variantes más exigentes y destruir los **tres tanques de gas** que bloquean la puerta del Obelisco.
- **Nivel 3:** superar defensas del Obelisco y enfrentar a Lucius Corr.

El jugador alterna continuamente entre desplazamiento, observación, combate, recolección e interacción. El ritmo de cada tramo se ajusta para mantener una progresión accesible.

## Experiencia a largo plazo

La motivación para continuar proviene de conocer las nuevas áreas de Metronia, dominar ataques y desplazamientos, conseguir el blaster, elegir cuándo adquirir las dos mejoras disponibles y alcanzar la confrontación final con Lucius Corr. El jugador gana herramientas y conocimientos en vez de depender de una gran cantidad de sistemas secundarios.

La progresión narrativa se presenta principalmente mediante escenarios, objetivos, sucesos visuales y confrontaciones: Jack sigue siendo un protagonista silencioso.

## Condición de victoria

- **Nivel 1:** derrotar a los enemigos requeridos para abrir la puerta industrial y atravesar la salida hacia el Distrito Industrial.
- **Nivel 2:** destruir los **tres tanques** vinculados a la puerta del Obelisco y salir de la fábrica. La obtención del blaster al comienzo forma parte de la progresión del nivel.
- **Nivel 3:** superar el recorrido, derrotar a Lucius Corr y activar la secuencia de victoria y créditos.
- **Juego completo:** registrar el cierre de la historia y las estadísticas finales en el sistema de guardado.

## Condición de derrota

Jack es derrotado si su salud llega a cero o entra en una zona letal. La pantalla de derrota descuenta una oportunidad. Si aún dispone de oportunidades, reaparece en el último checkpoint válido; de lo contrario, se activa Game Over y regresa al menú principal. Una muerte descuenta exactamente una oportunidad.

## Ritmo

| Momento | Experiencia | Función jugable |
|---|---|---|
| Exploración | Tramos de plataformas y reconocimiento de rutas | Orientar al jugador. |
| Acción | Combates breves y ataques encadenados | Mantener tensión y practicar mecánicas. |
| Descanso | Espacios seguros, checkpoints y estación | Permitir lectura del entorno y decisiones. |
| Desafío | Enemigos más exigentes, trampas, elevador y objetivos destructibles | Poner a prueba lo aprendido. |
| Recompensa | Materiales, blaster, nuevas zonas y mejoras | Mostrar progreso tangible. |
| Historia | Nuevos distritos, sabotaje de fábrica y enfrentamiento final | Dar contexto al avance mediante escenarios y eventos. |

## Principios de interacción

1. Toda plataforma, obstáculo y amenaza debe comunicar su función por apariencia, animación y reacción.
2. Los golpes, disparos, daño recibido y objetos recogidos generan respuesta visual y, cuando exista, sonora.
3. Las puertas bloqueadas indican su requisito; la industrial depende de enemigos específicos y la del Obelisco de tres tanques.
4. Las interacciones usan un mismo criterio de proximidad y el botón de interacción definido.
5. Los ataques bloqueados por energía, munición o falta de blaster deben informar por qué no se ejecutan.
6. Los consumibles temporales muestran su activación y fin; el refuerzo de carbón desaparece al consumirse o morir.
7. Los checkpoints y oportunidades deben presentar información visible y no borrar mejoras permanentes por error.
8. La presentación inicial es breve y conduce directamente a la experiencia de plataformas y combate.

> **Navegación:** [[00 - Índice]] · ← [[04 - Pilares de Diseño]] · [[02 - Mecánicas]] →
