# Progresión

## Descripción de la sección

La progresión de **Vaporlock** describe cómo evoluciona la experiencia del jugador a lo largo de sus tres niveles. El avance combina el aprendizaje de mecánicas, la obtención de nuevas herramientas, las mejoras de Jack Veil y el cumplimiento de objetivos que permiten acceder a nuevas áreas de Metronia.

El jugador comienza utilizando el brazo mecánico como arma principal y aprende a desplazarse, saltar y combatir. En el Distrito Industrial obtiene el blaster, accede a una máquina de mejoras y enfrenta desafíos que requieren combinar movilidad, combate e interacción con mecanismos. Finalmente, deberá aplicar lo aprendido para superar El Obelisco y derrotar a Lucius Corr.

La progresión se basa en el dominio de las habilidades y los recursos disponibles, **sin un sistema de niveles de experiencia del personaje**. Los checkpoints, las oportunidades y el guardado JSON facilitan la continuidad de la aventura.

## Progresión general

La aventura está organizada en seis etapas:

1. **Inicio:** Desde el menú principal, el jugador elige iniciar una nueva partida o continuar una partida guardada. Una breve presentación introduce a Jack Veil. La partida comienza en los Tejados de Metronia.
2. **Introducción de sistemas:** En el Nivel 1, el jugador conoce el movimiento horizontal, salto, dash, combate con el brazo mecánico y recolección de tuercas. Supera plataformas y enemigos; la salida industrial se habilita al cumplir la condición de eliminación de enemigos establecida en el escenario.
3. **Desarrollo:** Al comenzar el Nivel 2, el primer enemigo derrotado deja caer el blaster, como parte de la progresión. Se introducen el combate a distancia, cadenas trepables, elevadores, objetos destructibles y la máquina de mejoras. Jack debe destruir los tres tanques industriales para abrir la salida.
4. **Dominio:** El jugador combina los ataques físicos y disparos con dash, saltos, escalada, consumibles y, si fueron adquiridas, mejoras permanentes. Debe gestionar salud y recursos mientras supera desafíos más exigentes.
5. **Clímax:** En el Nivel 3, El Obelisco, el jugador enfrenta el tramo final y combate contra Lucius Corr. El jefe utiliza refuerzos mecánicos y presenta momentos de vulnerabilidad que el jugador debe aprovechar para derrotarlo.
6. **Final:** Tras derrotar a Lucius Corr, se registra el progreso y las estadísticas finales, y se presenta la pantalla de victoria y créditos.

**Flujo de progresión:**

`Menú principal → Presentación de Jack → Nivel 1: Tejados de Metronia → Nivel 2: Distrito Industrial → Nivel 3: El Obelisco → Derrota de Lucius Corr → Victoria y créditos`

## Progresión del jugador

El aprendizaje del jugador ocurre principalmente por la práctica y la incorporación gradual de desafíos:

1. **Desplazamiento y orientación:** Aprender a moverse, detenerse, saltar y calcular distancias entre plataformas.
2. **Combate físico:** Comprender el alcance del brazo mecánico, encadenar golpes y utilizar ataques especiales cuando sus condiciones lo permitan.
3. **Supervivencia y evasión:** Reconocer ataques enemigos, utilizar el dash, controlar la salud y evitar caídas o zonas peligrosas.
4. **Objetivos del escenario:** Identificar qué enemigos, puertas o mecanismos condicionan el avance del nivel.
5. **Combate a distancia:** Recoger el blaster al principio del Nivel 2 y aprender a utilizarlo junto con el brazo mecánico.
6. **Interacciones industriales:** Utilizar cadenas, elevadores y mecanismos; destruir los tanques necesarios para desbloquear la salida del Distrito Industrial.
7. **Gestión de recursos:** Recolectar tuercas, utilizar consumibles y decidir cuándo adquirir alguna de las dos mejoras disponibles.
8. **Dominio combinado:** Alternar movilidad, ataques físicos y disparos para afrontar enemigos más resistentes y, finalmente, el combate contra Lucius Corr.

Los controles de movimientos y ataques especiales presentes desde el inicio no necesitan convertirse en desbloqueos artificiales: su **aprendizaje** puede ser progresivo aunque la acción ya esté disponible.

## Progresión del personaje

A diferencia del aprendizaje del jugador, la progresión de Jack corresponde a los cambios efectivos en su equipo, sus atributos y los recursos que conserva.

- **Vida:** Jack dispone de una salud máxima base de 80 puntos. Los botiquines recuperan salud, y la inyección de carbón activado concede temporalmente un 20% de salud adicional. No existe una mejora permanente de salud máxima.
- **Daño:** El brazo mecánico es el arma inicial. La mejora **Actualización a prótesis de combate** aumenta su daño físico en un 50% (×1.5). La mejora **Incremento ilegal de blaster** duplica el daño del arma (×2).
- **Habilidades:** Jack utiliza movimiento, salto, dash, combos y ataques especiales; en el Distrito Industrial también aprovecha las cadenas y mecanismos del entorno. La mejora de prótesis incrementa un 30% su velocidad y capacidad de salto (×1.3 cada una).
- **Equipo:** El brazo mecánico está disponible desde el inicio. El blaster se obtiene al derrotar al primer enemigo del Nivel 2 y permanece como herramienta habitual durante el resto del juego.
- **Recursos:** Jack recolecta tuercas que puede gastar en la máquina de mejoras. El funcionamiento definitivo de la pérdida y recuperación de tuercas tras morir debe coordinarse con el sistema de checkpoints.
- **Consumibles:** El botiquín recupera salud; la adrenalina aumenta temporalmente velocidad y salto durante cinco segundos; el carbón activado añade una reserva temporal del 20% de salud que se consume al recibir daño o se pierde al morir.
- **Conocimiento:** El jugador aprende los patrones de los enemigos, las rutas y las condiciones de salida. Este progreso es de dominio del jugador y no se representa mediante puntos de experiencia.

Las **únicas mejoras permanentes** son la actualización de prótesis de combate y el incremento ilegal de blaster, cada una con un solo nivel. Sus costos son los indicados en la estación de mejoras.

## Desbloqueos

| Desbloqueo | Requisito | Efecto |
|---|---|---|
| Acceso al Distrito Industrial | Completar las condiciones de combate y alcanzar la puerta del Nivel 1. | Permite iniciar el Nivel 2. |
| Blaster / pistola | Derrotar al primer enemigo del Nivel 2 y recoger el arma que deja caer. | Habilita el combate a distancia permanentemente. |
| Máquina de mejoras | Llegar a la estación e interactuar con ella. | Permite consultar y adquirir las dos mejoras disponibles. |
| Actualización a prótesis de combate | Disponer de las tuercas necesarias y no haber comprado la mejora. | Velocidad ×1.3, capacidad de salto ×1.3 y daño físico ×1.5. |
| Incremento ilegal de blaster | Tener el blaster, reunir las tuercas necesarias y no haber comprado la mejora. | Daño del blaster ×2. |
| Acceso a El Obelisco | Destruir los tres tanques industriales del Nivel 2 y alcanzar la salida. | Permite iniciar el Nivel 3. |
| Victoria y créditos | Superar El Obelisco y derrotar a Lucius Corr. | Completa la historia principal y muestra el final. |

## Curva de dificultad

La dificultad aumenta por la combinación de enemigos, peligros del escenario y cantidad de mecánicas que el jugador debe utilizar, en lugar de depender únicamente del incremento de daño enemigo.

| Etapa | Dificultad esperada | Desafío principal |
|---|---|---|
| Nivel 1 — Tejados de Metronia | Fácil | Aprender movimiento, salto, dash y combate físico; superar plataformas y enemigos básicos. |
| Inicio del Nivel 2 — Distrito Industrial | Intermedia inicial | Obtener el blaster y comprender la combinación de ataques físicos y disparos. |
| Resto del Nivel 2 | Intermedia | Utilizar cadenas y elevadores, administrar recursos, enfrentar variantes de enemigos y destruir los tres tanques. |
| Nivel 3 — El Obelisco | Alta | Aplicar todas las habilidades aprendidas, superar obstáculos y enfrentar a Lucius Corr y sus refuerzos. |

Los segmentos iniciales deben ofrecer desafíos que permitan reconocer las acciones disponibles. Posteriormente, se incrementan la variedad de enemigos, la exigencia del movimiento y la necesidad de alternar herramientas. El enfrentamiento final debe comprobar el dominio de las mecánicas sin introducir controles fundamentales completamente nuevos.

Los **checkpoints y oportunidades** regulan la penalización por derrota. Al perder una oportunidad, Jack reaparece en el último checkpoint válido mientras disponga de oportunidades restantes.

## Curva de aprendizaje

Cada nuevo desafío debe apoyarse en conocimientos adquiridos previamente:

| Primero debe dominarse… | Antes de introducir… |
|---|---|
| Movimiento horizontal y salto | Plataformas separadas, elevadas o con riesgo de caída. |
| Ataques con el brazo mecánico | Enfrentamientos con varios enemigos y combinaciones de ataques. |
| Evasión y lectura de ataques | Enemigos más resistentes o ataques de mayor alcance. |
| Combate físico y recolección de recursos | Obtención del blaster y acceso a la máquina de mejoras. |
| Disparo y cambio entre estrategias de combate | Enfrentamientos que combinan enemigos cercanos y distantes. |
| Interacción con mecanismos | Elevadores, cadenas y objetivos destructibles del Distrito Industrial. |
| Administración de salud, consumibles y mejoras | Tramos de mayor presión y enfrentamiento final contra Lucius Corr. |

La progresión debe comunicar de forma clara los nuevos recursos y objetivos. El blaster requiere una señal visual al caer del primer enemigo; las estaciones y mecanismos deben indicar cuándo pueden utilizarse; las puertas deben reflejar si sus condiciones de apertura están completas.

El aprendizaje se considera exitoso cuando el jugador puede reconocer los peligros, seleccionar una herramienta apropiada y comprender por qué avanzó o fue derrotado. La dificultad debe fomentar la práctica sin obligarlo a descubrir reglas ocultas.

---

> **Navegación:** [[00 - Índice]] · ← [[04 - Controles]] · [[06 - Economía y Recursos]] →
