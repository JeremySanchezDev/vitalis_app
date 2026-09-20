# 09 · Calidad, pruebas y roadmap

## Estrategia de pruebas

| Nivel | Qué cubre |
|-------|-----------|
| Unitarias (dominio) | IMC por rangos y bordes (18,5 / 25 / 30); proteína por tasa; reparto 30/35/20/15 y kcal; conversión de unidades; tope de agua; clasificador de intenciones; cronómetro con reloj simulado (pausa, salto, fin) |
| Estado | Cambio de peso → recalcula proteína/plan/respuesta; perfiles acumulables |
| UI | Flujos: onboarding→Inicio; Inicio→plan→Dieta; Entreno→reproductor→salir |
| Accesibilidad | Criterios AC-01…AC-12 con lector de pantalla, fuente máxima, sin sonido, sin vibración |
| Privacidad | Verificar ausencia de tráfico de red en flujos de usuario |
| Rendimiento | Tiempo de generación de plan, consumo en reproductor, arranque en frío |
| Regresión visual | Temas oscuro/claro, combinaciones de perfiles |
| Usabilidad | Sesiones con usuarios reales de cada perfil, incluido «ambas necesidades» |

## Definición de hecho (por historia)

Requisito referenciado · pruebas pasan · criterios de accesibilidad verificados · funciona offline · textos externalizados · revisado en ambos temas.

## Roadmap propuesto

1. **Fase 0 — Decisiones:** cerrar ADR-01…05, prototipos técnicos de IA local y voz.
2. **Fase 1 — Núcleo:** dominio (IMC, proteína, plan, agua, cronómetro), almacén, temas, navegación.
3. **Fase 2 — Pantallas:** onboarding, Perfil, Dieta, Entreno con datos de ejemplo.
4. **Fase 3 — Reproductor adaptativo:** perfiles, subtítulos, háptico, anuncios, destello.
5. **Fase 4 — Asistente:** voz, texto, tarjetas, motor de IA local, orbe.
6. **Fase 5 — Pulido:** exportación, animaciones reales, rendimiento, pruebas con usuarios.
7. **Post-v1:** sustituir comida, alergias, historial semanal, varios perfiles.

## Riesgos de producto

- Que la IA local sea insuficiente en dispositivos modestos → mantener rutas por reglas como respaldo.
- Percepción de consejo médico → avisos claros de carácter orientativo.
- Fatiga sensorial de señales combinadas → probar con usuarios.

## Preguntas abiertas

¿Plataformas iniciales? ¿Idiomas además de español? ¿Contenido de rutinas: quién lo produce y valida? ¿Requisitos legales/regulatorios de datos de salud por mercado? ¿Pasos 1 y 3 del onboarding?
