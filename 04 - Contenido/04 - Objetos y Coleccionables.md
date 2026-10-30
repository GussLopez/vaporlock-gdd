# Objetos y Coleccionables

## Descripción de la sección

Los objetos están orientados a ayudar al jugador a superar los niveles y mejorar sus capacidades. No se contemplan coleccionables destinados a completar álbumes, descubrir secretos o alcanzar un porcentaje de colección.

El sistema principal consiste en recuperar recursos de los enemigos derrotados y utilizarlos en máquinas situadas en puntos específicos de los niveles para adquirir armas y mejoras del personaje.

**Estado:** propuesta inicial. Los nombres, diseños y valores de balance son provisionales.

## Recurso: Tuercas

**Tipo:** Recurso de mejora y moneda de intercambio.

**Descripción:** Piezas mecánicas aprovechables que quedan del equipo de los enemigos derrotados. Se representan mediante tuercas para facilitar su reconocimiento.

**Función:** Permitir la compra de armas y mejoras, recompensando el combate y dando al jugador la opción de gastar sus recursos o ahorrar para una compra posterior.

**Cómo se obtiene:** Los enemigos sueltan tuercas al ser derrotados. La cantidad depende de su dificultad; los enemigos más peligrosos entregan una recompensa mayor.

**Cómo se utiliza:** Se recogen automáticamente al acercarse y se acumulan en un contador. Se gastan al confirmar una compra en la Estación de Ensamblaje.

**Cantidad máxima:** Sin límite de inventario previsto inicialmente. No ocupan espacios individuales.

**Valor:** Una tuerca equivale a una unidad del recurso. Las cantidades soltadas y los precios se definirán mediante pruebas.

**Rareza:** Común. No se proponen distintas rarezas ni monedas adicionales.

**Restricciones:** No se equipan ni se utilizan directamente. Solo se consumen al adquirir armas o mejoras.

**Interacciones:** Al recogerlas, se reproduce un sonido metálico y se actualiza el contador del HUD. Si una recompensa cae en un lugar inaccesible, debe trasladarse a una superficie segura cercana.

**Representación visual:** Tuerca hexagonal de aspecto metálico, con tonos de latón y un brillo breve que permita distinguirla del escenario. Diseño definitivo pendiente.

## Elemento interactivo: Estación de Ensamblaje

**Tipo:** Máquina fija de compra y mejora.

**Descripción:** Estación industrial que transforma las piezas recuperadas en armamento y componentes para el personaje.

**Función:** Ofrecer un momento de preparación entre combates y permitir decisiones de progresión.

**Cómo se obtiene:** No se recoge. Se encuentra en puntos predeterminados de los niveles, preferentemente en zonas seguras después de encuentros importantes.

**Cómo se utiliza:** El jugador se acerca e interactúa para abrir un menú con tres categorías: armas, mejoras de armas y mejoras del personaje. Cada opción muestra su efecto, precio y requisitos antes de confirmar la compra.

**Cantidad máxima:** Número de estaciones por nivel pendiente de definir según su duración y dificultad.

**Valor:** Acceso gratuito; cada compra tiene un coste en tuercas.

**Rareza:** No aplica.

**Restricciones:** Solo permite comprar opciones disponibles y con saldo suficiente. Una mejora que haya alcanzado su nivel máximo no puede comprarse nuevamente.

**Interacciones:** Descuenta el coste y entrega el arma o aplica la mejora al confirmar. Las compras pueden incluir aumento de daño, resistencia o eficiencia de habilidades; el catálogo definitivo queda pendiente.

**Representación visual:** Máquina con engranajes, tuberías, compartimento para piezas y panel de selección. Una señal luminosa indica que puede utilizarse.

## Reglas de progresión y balance

- Las compras deben facilitar el avance sin volver inútiles las habilidades iniciales.
- Antes de la primera estación, el recorrido principal debería proporcionar recursos suficientes para una compra básica.
- Si una habilidad es indispensable para superar un obstáculo obligatorio, su obtención debe estar garantizada.
- Queda por definir si las tuercas y las mejoras se conservan entre niveles y qué ocurre con ellas al morir.
- Los precios, recompensas y límites de mejora se ajustarán mediante pruebas de juego.