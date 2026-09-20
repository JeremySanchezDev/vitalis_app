# 03 · Pantallas y flujos

## Mapa de navegación

```
Onboarding (3 pasos, una vez) ──► Inicio
Barra inferior: Inicio · Dieta · Entreno · Perfil
Inicio  ── respuestas del asistente ──► Dieta / Reproductor
Entreno ── rutina ──► Reproductor (capa completa, sin barra de navegación)
Perfil  ── edita medidas, unidades, tema, adaptaciones, privacidad
```

El reproductor es una **capa**, no una pestaña: mientras se entrena no hay navegación que distraiga ni destino por error.

## Estado compartido

Una única fuente de estado alimenta todas las pantallas: peso, altura, unidades, objetivo, tasa de proteína, preferencia dietética, plan, agua, necesidades, tema, paso/tiempo del entreno, conversación.

## Onboarding (3 pasos)

- Paso 2 de 3 documentado: «Cuéntale a Vitalis sobre tu cuerpo».
- Elementos: conmutador de unidades, peso, altura (con acciones de ajuste 1 kg / 1 cm para lector de pantalla), tarjeta de IMC + banda, objetivo, necesidades (casillas con texto), Continuar.
- Los pasos 1 y 3 **(pendiente de diseño)**; se sugiere: bienvenida/privacidad y confirmación de adaptaciones.

## Inicio — asistente

- Cabecera «Vitalis», estado del asistente, etiqueta «IA local».
- Vacío: «Pídeme tu plan, el agua o el entreno» + tres sugerencias.
- Mensajes usuario/asistente; el asistente responde con tarjeta de plan, agua o entreno.
- Estados: reposo, escuchando (barras + transcripción), pensando (texto + paso), respondido.
- Entrada: campo de texto + micro (64 dp).
- Orbe animado decorativo (`idle` / `listening` / `speaking`, nivel de energía).

## Dieta

- Proteína del día (g), fórmula, selector de objetivo (Mantener 1,2 / Fuerza 1,6 / Recomposición 2,0 g/kg), preferencia.
- Generación: barra + texto con pasos («leyendo perfil», «repartiendo gramos», «eligiendo platos», «comprobando kcal»).
- Resultado: cuatro comidas, totales de proteína y kcal, «Por qué este plan», Regenerar, Usar en el día.
- Bloque Hidratación con +250/+500 ml.

## Entreno

- Rutina recomendada («Fuerza sentada · 18 min», 5 ejercicios, silla + banda, bajo impacto) con nota de adaptación y «Empezar entrenamiento».
- Otras rutinas (Movilidad de hombro 9′, Core en silla 12′, Cardio bajo impacto 15′, Estiramiento largo 20′).
- Semana: L–D con nivel de actividad; «3 de 5 sesiones hechas. El jueves está pendiente.»

## Reproductor

- Cabecera: contador «n de N · nombre de rutina», perfil activo, Salir.
- Cuerpo: fase (Trabajo/Descanso), nombre, detalle, cuenta atrás en segundos, barra de progreso por pasos, espacio de animación, subtítulo (perfil sordo), línea de vibración (perfil ciego).
- Controles: anterior, pausa/reanudar, siguiente.
- Secuencia de ejemplo: Sentadilla en silla 30 s → descanso 15 s → Remo con banda 40 s → descanso 20 s → Flexión en pared 30 s.
- Fin de descanso con perfil sordo: fondo verde pulsante 2,4 s.

## Perfil

Peso, altura, IMC (+ impacto en proteína), unidades, tema, objetivo, adaptaciones (con nota de que se editan sin repetir onboarding), privacidad, exportar datos.

## Variantes de tarjetas del panel (estudio de jerarquía)

Tres órdenes explorados para los mismos cuatro datos: **2a** hidratación primero, **2b** entrenamiento primero, **2c** resumen de tres fichas + una acción. La pantalla vigente es Inicio conversacional; estas variantes quedan como alternativas de investigación.
