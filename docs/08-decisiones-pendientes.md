# 08 · Arquitectura agnóstica y decisiones pendientes

## Capas lógicas (sin tecnología)

1. **Presentación** — pantallas, navegación, componentes accesibles, temas.
2. **Estado de aplicación** — una fuente de verdad por pantalla derivada del estado compartido + canal de eventos de un solo disparo (vibración, avisos, anuncios).
3. **Dominio** — IMC, proteína, plan, agua, cronómetro, clasificador de intenciones (lógica pura, sin E/S).
4. **Servicios de dispositivo** — reconocimiento de voz, síntesis/anuncios, vibración, reloj, almacenamiento local, exportación de archivos.
5. **Motor de IA local** — generación del plan y respuestas del asistente, aislado tras una interfaz.

Regla: el dominio no depende de la UI ni de servicios; los servicios se inyectan detrás de interfaces para poder simularlos en pruebas.

## Contratos que deben existir (independientes de tecnología)

- `Almacén`: leer/escribir/borrar/exportar perfil, preferencias, planes, agua, sesiones.
- `Voz`: iniciar/detener dictado, emitir transcripción parcial y final.
- `Háptico`: patrones inicio / T-3 / final / confirmación.
- `Anunciador`: mensajes al lector de pantalla con prioridad.
- `MotorIA`: `generarPlan(peso, tasa, preferencia)` y `responder(texto)`; sin red.
- `Reloj`: instante actual (inyectable).

## Decisiones tecnológicas por tomar (ADRs)

| ID | Decisión | Opciones a evaluar | Criterios |
|----|----------|--------------------|-----------|
| ADR-01 | Plataformas objetivo | Solo Android · Android+iOS | Público, presupuesto |
| ADR-02 | Enfoque de desarrollo | Nativo · Multiplataforma | Accesibilidad nativa, rendimiento, equipo |
| ADR-03 | Modelo de IA local | Modelo pequeño en dispositivo · Reglas/plantillas + modelo opcional | Tamaño, latencia, batería, calidad en español |
| ADR-04 | Reconocimiento de voz | Servicio del sistema (offline) · Motor propio | Privacidad, idioma, offline |
| ADR-05 | Almacenamiento local | BD embebida · Archivos | Consultas, exportación, migraciones |
| ADR-06 | Animaciones de técnica | Formato vectorial animado · Vídeo corto | Peso, tratamiento `.lighten`, accesibilidad |
| ADR-07 | Orbe | Render por GPU · Animación precalculada | Compatibilidad, batería, movimiento reducido |
| ADR-08 | Formato de exportación | JSON · CSV · ambos | Portabilidad legible |
| ADR-09 | Distribución/actualizaciones | Tiendas · otras | Alcance |
| ADR-10 | Localización | Recursos por idioma | Español primero |

Nota: el prototipo sugiere Compose + StateFlow/SharedFlow + Lottie + WebGL; es un punto de partida, no un compromiso.

## Riesgos técnicos a resolver antes de decidir

- Calidad y peso de un modelo de IA en gama media/baja.
- Dictado offline en español con transcripción parcial.
- Cronómetro fiable con pantalla apagada/proceso suspendido.
- Vibración diferenciada en dispositivos con háptica limitada.
- Coste energético del orbe y animaciones.
