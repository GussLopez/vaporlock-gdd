# Economía y Recursos

## Descripción de la sección

La economía de **Vaporlock** organiza los recursos que Jack Veil obtiene, consume y conserva durante su recorrido por Metronia. Su propósito es apoyar el combate y la exploración sin convertir la recolección en una obligación que interrumpa el ritmo del videojuego.

Las **tuercas** funcionan como recurso de intercambio en la máquina de mejoras. La **salud**, la **energía de combate**, la **munición**, los **consumibles** y las **oportunidades** determinan cuánto puede resistir o actuar el jugador y qué consecuencias tiene cometer errores. No se contempla un sistema de experiencia o niveles de personaje.

Los recursos se obtienen y consumen mediante reglas consistentes, y las mejoras permanentes conservan sus efectos a lo largo de la partida.

## Recursos

| Recurso | Obtención | Uso | Límite | Pérdida |
|---|---|---|---|---|
| **Tuercas** | Recompensas soltadas por determinados enemigos; recuperación de la bolsa tras morir. | Comprar las dos mejoras de la máquina. | Según el límite de recursos del personaje. | Se descuentan al comprar; pueden caer en una bolsa recuperable al morir. |
| **Salud** | Salud inicial o reaparición; recuperación mediante botiquín. | Resistir daño de enemigos, trampas y peligros. | **80 HP base**. | Disminuye por daño; llegar a cero provoca la muerte. |
| **Energía de combate** | Se acumula al conectar determinados ataques físicos. | Ejecutar el ataque especial RayPunch. | Según el medidor máximo de energía. | Se consume al utilizar el ataque especial. |
| **Munición del blaster** | Mediante el blaster y su sistema de recarga. | Realizar disparos a distancia. | Capacidad de cargador y reserva por confirmar. | Disminuye al disparar; el arma utiliza recarga. |
| **Botiquín** | Recolección en puntos del escenario. | Recuperar puntos de salud. | Cantidad transportable por definir. | Se consume al utilizarse. |
| **Inyección de adrenalina** | Recolección en puntos del escenario. | Aumentar temporalmente velocidad y salto. | Cantidad transportable por definir; efecto de **5 segundos**. | Se consume al utilizarse; el efecto termina al agotarse su duración. |
| **Inyección de carbón activado** | Recolección en puntos del escenario. | Otorgar salud adicional temporal equivalente al **20% de la salud máxima base**. | Cantidad transportable por definir; una aplicación proporciona **16 HP adicionales** con 80 HP de salud base. | Se consume al utilizarse; la bonificación se agota con el daño o desaparece al morir. |
| **Oportunidades** | Se asignan al iniciar o recuperar una partida; cantidad inicial por definir. | Permitir reaparecer en un checkpoint tras una derrota. | Cantidad inicial y máxima por definir. | Se pierde **una oportunidad por muerte**. |

## Fuentes y sumideros

**Fuentes:** Son las acciones o situaciones mediante las que el jugador obtiene recursos.

- **Derrotar enemigos:** algunos enemigos dejan caer tuercas, que pueden recogerse y acumularse.
- **Recuperar una bolsa de tuercas:** Jack recupera los recursos perdidos al regresar al lugar donde murió.
- **Conectar ataques físicos:** determinados impactos permiten recargar la energía usada por RayPunch.
- **Recoger objetos:** los botiquines y las dos inyecciones se encuentran en puntos de recolección del escenario.
- **Obtener el blaster:** al derrotar al primer enemigo del Nivel 2, este suelta la pistola. Es un desbloqueo permanente de equipo, no una compra con tuercas.
- **Restaurar la salud:** el botiquín permite recuperar salud perdida, dentro del límite correspondiente.

**Sumideros:** Son las acciones o acontecimientos que consumen o reducen recursos.

- **Comprar mejoras:** la máquina descuenta tuercas al adquirir la actualización de prótesis de combate o el incremento ilegal de blaster.
- **Recibir daño:** los ataques enemigos y peligros reducen la salud o consumen primero los puntos adicionales del carbón activado.
- **Usar RayPunch:** gasta energía de combate.
- **Disparar el blaster:** consume munición al disparar.
- **Utilizar consumibles:** el botiquín y las inyecciones se retiran de la cantidad disponible después de usarse.
- **Morir:** termina los efectos temporales, descuenta una oportunidad y activa las reglas de pérdida o recuperación de tuercas.

## Reglas

**1. Moneda y compras.** Las tuercas son la unidad de intercambio. La máquina de mejoras ofrece únicamente dos compras permanentes, de un nivel cada una: **Actualización a prótesis de combate** (velocidad ×1.3, capacidad de salto ×1.3 y daño físico ×1.5) e **Incremento ilegal de blaster** (daño del blaster ×2). No pueden volver a comprarse una vez adquiridas. Cada compra exige su costo en tuercas y no puede realizarse si los recursos son insuficientes. La mejora del blaster requiere haber obtenido el arma.

**2. Salud.** La salud máxima base de Jack es de **80 HP**. El daño reduce la salud actual; al llegar a cero se produce la muerte. El botiquín recupera salud sin exceder el máximo normal. La cantidad recuperada corresponde al valor de curación del botiquín.

**3. Carbón activado.** La inyección concede una reserva temporal equivalente al **20% de la salud máxima base**. Con 80 HP base, Jack puede alcanzar **96 HP**, de los cuales **16 HP corresponden a la bonificación**. El daño consume primero esta reserva; al agotarse, la salud vuelve a funcionar con el máximo normal de 80 HP. Si el daño supera la reserva restante, el excedente afecta a la salud normal. El beneficio desaparece al morir y no se restaura automáticamente mediante botiquines. El refuerzo no se multiplica al utilizar varias inyecciones simultáneamente.

**4. Adrenalina.** Aumenta temporalmente la velocidad y la capacidad de salto durante **5 segundos**. El incremento se aplica sobre los valores de movimiento y salto vigentes. Su efecto no es una mejora permanente y debe terminar al finalizar el tiempo o cuando la muerte interrumpe la partida. Una segunda aplicación no acumula el aumento mientras el efecto está activo.

**5. Energía de combate.** Se obtiene mediante determinados impactos físicos y se utiliza para RayPunch. Si la energía es insuficiente, el ataque no puede ejecutarse. La cantidad disponible y el costo de RayPunch se reflejan en el medidor de energía.

**6. Munición.** El blaster queda disponible permanentemente después de recogerlo al comienzo del Nivel 2. Sus disparos consumen munición y el arma utiliza un sistema de cargadores y recarga. La mejora de daño ×2 no debe alterar por sí sola la cantidad de munición.

**7. Recolección y pérdida de tuercas.** Los recursos recolectados incrementan el saldo del jugador. Al morir, las tuercas no gastadas quedan en una bolsa recuperable en el lugar de la derrota. El jugador puede volver al punto para recogerlas mientras continúe la partida.

**8. Oportunidades y reaparición.** Cada muerte descuenta una oportunidad. Mientras queden oportunidades, Jack reaparece en el último checkpoint activado; al agotarlas, se dirige al menú principal.

**9. Persistencia.** El guardado de partida debe conservar el nivel, el checkpoint, las oportunidades, las tuercas, el blaster obtenido y las mejoras permanentes. El guardado también registra la munición y los consumibles conservados. Los efectos temporales de adrenalina y carbón activado no deben conservarse después de la muerte. El progreso se registra mediante datos JSON.

**10. Límites y acumulación.** No existe intercambio de recursos entre jugadores. Las cantidades acumuladas se sujetan a los límites de cada recurso y a las reglas de inventario y munición.

## Balance

**¿Qué comportamiento queremos incentivar?**

Se busca recompensar la exploración, el combate bien ejecutado y el uso inteligente de los recursos. Derrotar enemigos debe ofrecer una ventaja útil mediante las tuercas, mientras que administrar la salud, la energía y la munición favorece decisiones cuidadosas. Las dos mejoras deben representar elecciones significativas: una beneficia la movilidad y el combate físico; la otra fortalece el ataque a distancia. Los consumibles sirven como apoyo en momentos difíciles sin sustituir las habilidades del jugador.

La cantidad de tuercas que se obtiene durante los niveles y los costos de ambas mejoras deben permitir que el jugador comprenda sus posibilidades de compra sin necesitar sesiones largas de recolección, especialmente porque cada nivel presenta un recorrido breve.

**¿Qué comportamiento queremos evitar?**

No se pretende obligar al jugador a repetir enfrentamientos únicamente para reunir recursos, acumular grandes cantidades de objetos ni depender de una mejora específica para poder terminar el videojuego. También deben evitarse compras duplicadas, bonificaciones permanentes obtenidas por error, pérdida injustificada de recursos al reaparecer y situaciones en que el jugador se quede bloqueado por falta de munición o consumibles.

El balance distribuye tuercas, consumibles y munición de modo que las mejoras sean alcanzables sin obligar a repetir enfrentamientos. La disponibilidad de recursos y la dificultad de los enemigos mantienen una progresión gradual.

---

**Navegación:** [[00 - Índice]] · ← [[05 - Progresión]] · [[07 - Reglas y Estados del Juego]] →
