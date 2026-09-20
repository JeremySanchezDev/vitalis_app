# 02 · Requisitos

## Funcionales

### Onboarding
- **RF-01** Tres pasos, mostrados una sola vez; al terminar se entra a Inicio.
- **RF-02** Captura de peso y altura con conmutador de unidades métrico (kg/cm) e imperial (lb/ft·in).
- **RF-03** El IMC se calcula y se muestra en vivo con su banda (ver [04](04-reglas-negocio.md)).
- **RF-04** Selección de objetivo: Perder peso, Ganar fuerza, Mantener movilidad.
- **RF-05** Selección múltiple de necesidades de accesibilidad.
- **RF-06** Aviso visible de que los datos no salen del teléfono.

### Inicio (asistente)
- **RF-10** Entrada por voz y por texto sobre el mismo estado: el micro rellena el mismo campo, editable antes de enviar.
- **RF-11** Transcripción en vivo mientras se dicta (sirve también de subtítulo).
- **RF-12** Intenciones: plan de comidas, agua, entreno; cualquier otra → pide precisión con tres ejemplos.
- **RF-13** Respuestas como tarjetas con acciones («Usar este plan», «Otro», «+250 ml», «Empezar entrenamiento»).
- **RF-14** Sugerencias visibles con la conversación vacía.
- **RF-15** Estado «pensando/generando» con texto por pasos.
- **RF-16** La conversación arranca vacía cada día.

### Dieta
- **RF-20** Proteína objetivo = peso × g/kg según objetivo (Mantener/Fuerza/Recomposición).
- **RF-21** Preferencia dietética: Mixta, Vegetariana, Sin lactosa (solo cambia el catálogo de platos).
- **RF-22** Plan de cuatro comidas con hora, plato, ingredientes, proteína y kcal.
- **RF-23** Explicación «Por qué este plan».
- **RF-24** Regenerar y «Usar en el día».
- **RF-25** Solo se pasan al modelo peso, g/kg y preferencia.

### Hidratación
- **RF-30** Meta diaria 2,5 L **(supuesto)**; registro rápido +250 ml y +500 ml; tope de registro 3 L.
- **RF-31** Frase de estado («5 vasos más»).

### Entreno
- **RF-40** Rutina recomendada del día con etiquetas (duración, ejercicios, material, impacto) y nota de adaptación.
- **RF-41** Índice de otras rutinas, cada una con su «por qué».
- **RF-42** Resumen semanal (sesiones hechas, pendientes).
- **RF-43** Reproductor a pantalla completa (capa, no pestaña): fases trabajo/descanso, cuenta atrás, paso anterior/siguiente, pausa/reanudar, salir.
- **RF-44** Animación de técnica en bucle por ejercicio (espacio reservado).
- **RF-45** Al terminar un descanso hay señal no sonora obligatoria.

### Perfil
- **RF-50** Editar peso, altura, unidades, tema, objetivo y adaptaciones sin repetir onboarding.
- **RF-51** Mostrar cómo el peso afecta a la proteína.
- **RF-52** Sección de privacidad y **exportar mis datos**.

### Adaptaciones (efecto en el reproductor)
- **RF-60** Sorda/hipoacusia: subtítulos de toda señal sonora, cuenta atrás en pantalla, destello verde de 2,4 s al fin de descanso.
- **RF-61** Ciega/baja visión: anillo reducido, tipografía mayor, vibración (inicio / T-3 / final), anuncio del siguiente ejercicio por lector de pantalla.
- **RF-62** Las adaptaciones se acumulan.

## No funcionales

- **RNF-01 Privacidad:** sin red para funciones de usuario; sin cuenta, sincronización ni analítica.
- **RNF-02 Accesibilidad:** ver [06](06-accesibilidad.md); áreas táctiles ≥ 48 dp (micro 64 dp).
- **RNF-03 Contraste:** alto contraste por defecto; acento ≥ 3:1 (solo iconos/texto grande/cromo); texto de párrafo con paso profundo de rampa.
- **RNF-04 Rendimiento:** IA y cálculos en el dispositivo con retroalimentación inmediata; animaciones ligeras.
- **RNF-05 Movimiento reducido:** respetar la preferencia del sistema (el orbe baja su ritmo).
- **RNF-06 Robustez del cronómetro:** el tiempo se calcula por reloj real (marca de inicio de fase), no por conteo de ticks, para sobrevivir a pausas del proceso.
- **RNF-07 Temas:** oscuro y claro sin cambiar la jerarquía.
- **RNF-08 Idioma:** español; textos externalizados para traducción futura.
- **RNF-09 Offline total.**
- **RNF-10 Borrado:** al desinstalar no queda dato alguno fuera del dispositivo.
