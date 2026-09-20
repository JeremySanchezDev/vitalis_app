# 04 · Reglas de negocio

## IMC

`IMC = peso_kg / (altura_m)²`

| Rango | Banda |
|-------|-------|
| < 18,5 | Bajo peso |
| 18,5 – < 25 | Rango saludable |
| 25 – < 30 | Sobrepeso |
| ≥ 30 | Obesidad |

Se lee siempre como resultado del par peso/altura. Orientativo, no diagnóstico. Almacenamiento interno en métrico; la conversión imperial es solo de presentación.

## Proteína objetivo

`objetivo_g = round(peso_kg × tasa)`

| Objetivo | Tasa g/kg |
|----------|-----------|
| Mantener | 1,2 |
| Fuerza | 1,6 |
| Recomposición | 2,0 |

## Plan de comidas

- Cuatro comidas a las 08:00, 13:00, 16:30, 20:00.
- Reparto de proteína: **30 / 35 / 20 / 15 %** del objetivo (cada comida redondeada).
- Energía estimada: `kcal = round(prot_g × 4 / 0.32 / 10) × 10` (32 % de las kcal viene de proteína).
- Totales = suma de comidas (pueden diferir ±1 g del objetivo por redondeo).
- La **preferencia** (Mixta, Vegetariana, Sin lactosa) solo cambia el catálogo de platos, nunca el objetivo. Catálogo de ejemplo con platos e ingredientes en el prototipo (p. ej. Mixta: tortilla con avena, pollo con arroz y judías, yogur griego con nueces, merluza con patata).
- Entrada al modelo: **solo** peso, g/kg y preferencia.
- Texto accesible por fila: «Comida N a las HH:MM: plato, X gramos de proteína, Y kilocalorías».
- Pendiente: sustitución de una comida; alergias.

## Hidratación

- Meta 2,5 L (supuesto); incrementos 250/500 ml; tope 3.000 ml.
- Progreso = min(1, agua/2500). Frase: vasos restantes (vaso = 250 ml).

## Entrenamiento

- Rutina = lista de pasos `{tipo: trabajo|descanso, nombre, detalle, duración_s, indicación}`.
- Cada rutina explica su «por qué».
- Cronómetro: cada fase guarda su instante de inicio; `restante = duración − (ahora − inicio)`. Pausa/reanudar reajusta el inicio. Al llegar a 0 avanza automáticamente; tras el último paso, fin.
- Fin de descanso automático + perfil sordo → destello verde 2,4 s.
- Vibración (perfil ciego): inicio de fase, T-3 s, final.
- Saltar paso: reinicia la duración del paso destino y cancela destellos.

## Asistente

Clasificación por palabras clave (sin distinguir mayúsculas):

| Palabras | Acción |
|----------|--------|
| proteína, comida, dieta, plan | Genera el plan de cuatro comidas |
| agua, hidratación, beber | Registra vasos y devuelve lo que falta |
| entreno, rutina, ejercicio | Rutina de hoy con acceso al reproductor |
| otro | Pide precisión con tres ejemplos; no inventa |

## Adaptaciones

Las necesidades se suman. Cambian presentación (subtítulos, vibración, tamaños, anuncios), nunca las rutinas disponibles.
