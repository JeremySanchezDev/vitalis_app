# 06 · Accesibilidad

## Principio

Toda señal tiene al menos dos canales: **visual, táctil, sonoro/hablado**. Un perfil activa canales adicionales; no quita funcionalidad.

## Perfiles

| Perfil | Presentación en el reproductor |
|--------|-------------------------------|
| Estándar | Anillo, cuenta atrás, animación, señales sonoras |
| Sorda / hipoacusia | Cuenta atrás grande en pantalla; subtítulo de cada señal sonora; destello verde 2,4 s al terminar el descanso |
| Ciega / baja visión | Anillo reducido, tipografía mayor; vibración en inicio / T-3 / final; anuncio del siguiente ejercicio por lector de pantalla antes de empezar |
| Movilidad reducida | Rutinas de bajo impacto, áreas táctiles amplias |
| Apoyo cognitivo | Instrucciones cortas, una acción por tarjeta |
| Combinados | Se apilan (subtítulos + vibración a la vez) |

## Criterios de aceptación transversales

- **AC-01** Áreas táctiles ≥ 48 dp; micro 64 dp.
- **AC-02** Todo control tiene nombre accesible propio («+250 ml» no basta: «Añadir 250 mililitros de agua»).
- **AC-03** Cada tarjeta se lee como **un solo nodo** con su resumen completo.
- **AC-04** Controles de progreso ajustables con incremento (1 kg / 1 cm) para lectores de pantalla.
- **AC-05** Necesidades como casillas con texto y estado, nunca chips solo con icono.
- **AC-06** Elementos decorativos (anillo, orbe) ocultos al lector; la cifra/texto es la fuente.
- **AC-07** Estados dinámicos (transcripción, «generando», cambios de fase) anunciados como región viva asertiva.
- **AC-08** Dictado: vibración al abrir y cerrar; barras + texto para quien no oye el pitido.
- **AC-09** Foco de teclado visible (anillo de 2 px del acento); estados hover/pulsado tematizados.
- **AC-10** Contraste alto por defecto; respetar movimiento reducido.
- **AC-11** Toda función de voz tiene alternativa de texto y viceversa.
- **AC-12** Cada señal sonora tiene gemela en subtítulo; cada vibración tiene gemela visual.

## Excepción consciente

El destello verde del fin de descanso rompe la regla de Nocturne de «no inundar de color»: es la única señal no sonora del evento, así que prevalece. Debe limitarse a 2,4 s y evitar parpadeo rápido (riesgo fotosensible: ≤ 3 destellos/s).

## Pruebas de accesibilidad

Lector de pantalla del sistema en ambas plataformas, escalado de fuente máximo, modo sin sonido, vibración desactivada, teclado/mando externo, daltonismo, y el caso «ambas necesidades» (pendiente de probar en el prototipo).
