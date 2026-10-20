# Entornos

## Descripción de la sección

Define la estética y necesidades visuales de escenarios, fondos, objetos y elementos ambientales.

## Zonas

| Zona                                   | Estilo                                                                                                                                      | Elementos                                                                                                                                                             | Función                                                                                                                                                          |
| -------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Tejados de Metronea (Nivel 1)          | Industrial urbano vertical, opresivo y expuesto a la intemperie. Mezcla de ladrillo, chimeneas de vapor y estructuras metálicas de soporte. | Antenas de transmisión, chimeneas humeantes, tuberías de cobre , passarelas de metal oscuro , claraboyas de vidrio, letreros incandescentes y banderas de checkpoint. | Nivel introductorio. Enseña mecánicas de salto, precisión en plataformas, uso del impulso/esquiva y combate básico contra enemigos aéreos y patrullas de tejado. |
| Distrito Industrial (Nivel 2)          | Industrial pesado, opresivo y desgastado en ladrillo visto y cobre.                                                                         | uberías de cobre , chimeneas lanzando humo, calderas incandescente, engranajes gigantescos, vigas de hierro  y banderas de resistencia.                               | Introducción al juego; enseña las mecánicas de movimiento, plataformas y combate básico.                                                                         |
| El Obelisco / Torre Oligarca (Nivel 3) | Monolítico, militarizado, opulento y dominado por acero pulido.                                                                             | Paredes de metal oscuro, escudos energéticos rojos, estatuas de Lucius Corr, pantallas de vigilancia y ascensores industriales.                                       | Clímax y combate final contra Lucius Corr; pone a prueba todas las habilidades del jugador.                                                                      |
## Modularidad

¿Qué elementos pueden reutilizarse?
Para optimizar el rendimiento y acelerar el desarrollo del juego, se utilizará un sistema de azulejos (Tilesets) modulares de $32 \times 32\text{ px}$ (ensamblados en bloques de $48 \times 48\text{ px}$):
## Iluminación

Describe iluminación global, fuentes de luz y cambios durante el juego.

*Elementos reutilizables entre niveles:*

- **Estructuras base:** Bloques de plataforma de suelo, techos, esquinas y paredes con borde de colisión.

- **Mecanismos e Interacción:** Tuberías rectas y en codo, válvulas, palancas de encendido, faroles industriales y cajas de madera/metal destructibles.

- **Fondos (Parallax):** Siluetas de edificios lejanos, capas de niebla y tuberías de fondo desaturadas.

- **Puntos de guardado:** Estaciones de banderas / checkpoints.
## Iluminación

Describe iluminación global, fuentes de luz y cambios durante el juego.

- **Iluminación Global:**
    
    - **Nivel 1:** Tonalidad cálida y penumbrosa (Chiaroscuro industrial). Domina el contraste entre esquinas en Sombra profunda y luces ambientales ámbar.
    
    - **Nivel 2:** Tonos fríos y desaturados intermitentes por cortocircuitos en las instalaciones destruidas.
    
    - **Nivel 3:** Iluminación corporativa de alto contraste con resplandores rojos y dorados.
    
- **Fuentes de Luz Dinámicas:**
    
    - Focos y faroles en Luz ámbar  para guiar la atención del jugador hacia el camino correcto (signposting).
    
    - Fuego de calderas y núcleos energéticos en Luz intensa.
    
    - Indicadores de peligro y proyectiles enemigos en Resalte rojo.
## Efectos visuales

- **Clima / Atmósfera:**
    
    - Polución flotante y partículas de hollín suspendidas en el aire.
    
    - Niebla densa en la parte inferior de la pantalla para delimitar zonas de caída mortal.
    
- **Humo y Vapor:**
    
    - Fugas continuas de Vapor expulsadas a presión por tubos dañados.
    
    - Columnas de humo negro ascendente desde las chimeneas de la fábrica.
    
- **Fuego y Calderas:**
    
    - Partículas de brasas y chispas flotantes cerca de los hornos de carbón.
    
- **Energía:**
    
    - Arcos eléctricos intermitentes en cables expuestos y campos de fuerza rojos  en zonas restringidas.
    
    - Destellos de energía cian en las estaciones de mejora de los Tecnócratas.
    
- **Impactos:**
    
    - Chispas doradas con Reflejo metálico  al golpear estructuras de metal o enemigos.
    
    - Escombros pequeños de ladrillo  al romper cobertura o golpear muros.

## Recursos requeridos

- **Tilesets / Texturas:**
    
    - Tileset_Industrial_District_32x32.png (Paredes de ladrillo, suelos metálicos, vigas y tubos).
    
    - Tileset_Background_Parallax.png (Capa distante de fábricas y siluetas urbanas).
    
- **Sprites de Props e Interacción:**
    
    - Válvulas de vapor, palancas, consolas de control, contenedores y cajas destructibles.
    
    - Bandera de Checkpoint y Máquina de Mejoras de Jack.
    
- **Efectos de Partículas (VFX Spritesheets):**
    
    - Animación de fuga de vapor en bucle (Steam_Leak_Loop.png).
    
    - Chispas de impacto metálico (Metal_Sparks_FX.png).
    
    - Explosión pequeña y humo (Explosion_Small_FX.png).


## Recursos requeridos

Lista los modelos, sprites, texturas, materiales y efectos necesarios.


> **Navegación:** [[00 - Índice]] · ← [[02 - Personajes y Animación]] · [[04 - Interfaz Visual]] →
