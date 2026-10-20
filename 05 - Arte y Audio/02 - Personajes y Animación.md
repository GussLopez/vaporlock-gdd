# Personajes y Animación

## Descripción de la sección

Documenta cómo deben verse y comportarse visualmente los personajes.

## Requisitos por personaje

| Personaje          | Modelo/Sprite                                                                                         | Animaciones                                                                                        | VFX                                                                                            | Estado      |
| ------------------ | ----------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ----------- |
| Jack Veil          | Sprite 64x64 px (Abrigo industrial, prótesis mecánicas de cobre #8F5839 y bordes dorados #DFA961) | Caminar, Correr, Saltar, Caer, Interactuar, Ataque Espada 1-2, Disparo Arma, Esquiva, Daño, Muerte | Ráfagas de vapor blanco (#D3CCC5), chispas metálicas (#F8C670), destello ámbar (#FBCE63) | En progreso |
| Lucius Corr        | Sprite 64x64px (Traje corporativo, hombreras de latón pulido, bastón energético)                      | Caminar, Ataque Bastón, Rayo energético, Invocación Escudo, Daño, Muerte                           | Arcos eléctricos, destellos ámbar (#F59D22), aura/escudo rojo (#A2261D)                    | Pendiente   |
| Sentinela Alpha-34 | Sprite 68x68px (Humanoide cibernético pesado con garrote/porra neumática)                             | Patrulla, Ataque Garrote, Daño, Muerte                                                             | Chispas metálicas, resplandor rojo de alerta (#D65D31) en visera                             | En progreso |
| Cyborg Omega-06    | Sprite 48x48px (Humanoide cibernético pesado con garrote/porra neumática)                             | Retroceso, Disparo Distancia, Daño, Muerte                                                         | Proyectiles incandescentes (#F59D22), ráfagas de humo gris                                   | Pendiente   |
| Dron Epsilon-21    | Sprite 32x32px (Unidad voladora de rotación con escotilla inferior)                                   | Sprite 32x32px (Unidad voladora de rotación con escotilla inferior)                                | Sprite 32x32px (Unidad voladora de rotación con escotilla inferior)                            | Pendiente   |

## Animaciones

### Movimiento

- **Idle (Reposo):**
    
    - Jack Veil: Ciclo de respiración pesada de 4 a 6 frames. Muestra una postura erguida pero desgastada; las válvulas de sus prótesis sueltan pequeñas micro-bocanadas de vapor cada ciclo.
    
    - Enemigos terrestres: Postura de alerta defensiva, mirando hacia ambos lados.
    
    - Dron Epsilon-21: Flotación suave arriba y abajo (efecto bobbing) con la hélice en giro continuo.
    
- **Caminar:**
    
    - Jack Veil: 8 frames. Zancada firme a velocidad moderada. El peso metálico de las prótesis se nota en el impacto con el suelo; el abrigo se balancea ligeramente.
    
    - Sentinela / Cyborg: Marcha militar o patrullaje pesado y rítmico.
    
- **Correr:**
    
    - Jack Veil: 8 frames. Inclinación del torso hacia adelante a mayor velocidad. Escapes continuos de vapor a alta presión por los tobillos mecánicos al despegar los pies.
    
- **Saltar:**
    
    - Jack Veil: 3 a 4 frames.
        
        - Frame 1 (Pre-jump/Squat): Flexión de piernas mecánicas cargando presión.
        
        - Frame 2 (Ascenso): Propulsión vertical con una ráfaga fuerte de vapor expulsada hacia abajo.
        
        - Frame 3 (Cúspide): Suspensión en el punto más alto del salto.
        
- **Caer:**
    
    - Jack Veil: 2 a 3 frames. Caída libre con el abrigo ondeando hacia arriba y brazos preparados para amortiguar el impacto contra el suelo.

### Interacción

- **Accionar / Manipular:** 4 a 6 frames. Jack extiende su brazo mecánico para accionar palancas, abrir válvulas de vapor o presionar botones en consolas industriales.

- **Uso de la Máquina de Mejoras:** 6 frames. Conecta la interfaz de su brazo mecánico a la estación de trabajo para descargar mejoras o reparar sus sistemas.

- **Guardado / Checkpoint:** 6 frames. Clava o despliega la bandera de resistencia / activa la baliza de vapor.


### Combate

- **Ataque Cerca (Espada / Tajo):** Combo de 2 a 3 tajos rápidos (6 frames por ataque). Trazado de estela brillante en arco. El segundo impacto aprovecha la fuerza del brazo hidráulico para un tajo descendente pesado.

- **Ataque Distancia (Disparo):** 4 frames. Apunta rápidamente con la pistola/brazo cibernético. Presenta retroceso marcado del cuerpo y un destello incandescente en la boquilla.


### Daño

- **Hurt / Impacto Ligero:** 3 frames. Interrupción rápida de la acción. El personaje retrocede con una mueca de dolor mientras parpadea en rojo/blanco.

- **Impacto Pesado / Empuje:** 4 frames. Golpe que desplaza al personaje varios píxeles hacia atrás por ondas de choque o explosiones.

### Muerte / derrota

- **Muerte de Jack Veil:** 8  frames. Sus prótesis fallan soltando chispas intermitentes y fugas de vapor descontroladas; pierde el equilibrio, cae de rodillas y colapsa boca abajo en el suelo.

- **Muerte de Enemigos:** 5 a 8 frames. Desensamblaje mecánico, explosión de partes o colapso del sprite soltando piezas de hierro y cobre.

- **Derrota de Lucius Corr (Jefe):** 8 frames. El exoesqueleto/traje se sobrecalienta, los núcleos explotan progresivamente y Lucius cae apoyado en su bastón antes de colapsar definitivamente.

## Convenciones

Define nombres de archivos, tamaños, esqueletos, rigging, frames o formatos cuando sea necesario.

Para asegurar que todo el equipo de arte y programación trabaje de forma integrada, se establecen las siguientes reglas de exportación e implementación:
#### 1. Formatos y Exportación

- **Formato final de asset:** Archivos .png transparentes organizados en hojas de sprites (spritesheets) o carpetas de fotogramas clave.    
- **Archivos fuente:** Archivo Máster .aseprite o .psd organizado por capas nombradas (p. ej., Body, Arm_Prosthetic, VFX_Steam, Shadow).


#### 2. Nomenclatura de Archivos

Se utilizará la convención Snake_Case en inglés para compatibilidad con motores de juego (Unity / Unreal / Godot):

> **Navegación:** [[00 - Índice]] · ← [[01 - Dirección de Arte]] · [[03 - Entornos]] →
