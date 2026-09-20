# 05 · Modelo de datos (conceptual, agnóstico)

Un único perfil por dispositivo. Todo se guarda localmente.

```
Perfil (1) ──< Registro de agua
   │      ──< Plan de comidas (1 activo) ──< Comida
   │      ──< Sesión de entreno ──> Rutina ──< Paso
   └─ Preferencias (unidades, tema, adaptaciones)
```

| Entidad | Campos clave |
|---------|--------------|
| Perfil | pesoKg, alturaCm, objetivo (Perder peso · Ganar fuerza · Mantener movilidad), tasaProteína (1,2/1,6/2,0), preferenciaDieta |
| Preferencias | unidades (métrico/imperial), tema (oscuro/claro), necesidades[] (baja visión, hipoacusia, movilidad reducida, apoyo cognitivo), onboardingCompletado |
| PlanComidas | fecha, objetivoProteínaG, totalProteínaG, totalKcal, porqué, comidas[4] |
| Comida | hora, plato, ingredientes, proteínaG, kcal |
| RegistroAgua | fecha, ml, instante (total diario derivado) |
| Rutina | nombre, duraciónMin, material, impacto, porqué, pasos[] |
| Paso | tipo (trabajo/descanso), nombre, detalle, duraciónS, indicación |
| SesiónEntreno | rutinaId, fecha, completada, pasoActual |
| Mensaje (efímero) | autor, texto, tipo (texto/plan/agua/entreno), carga |

## Ciclo de vida

- La conversación es efímera: se descarta al cambiar de día.
- Plan y agua son diarios; el agua se reinicia cada día.
- Historial de sesiones alimenta el resumen semanal.
- **Exportar mis datos:** volcado legible de Perfil, Preferencias, planes, agua y sesiones (formato por decidir).
- **Borrado:** al desinstalar desaparece todo; se recomienda además una opción «Borrar mis datos» **(pendiente)**.

## Reglas de integridad

- Peso/altura con rangos plausibles y validación al editar **(supuesto)**.
- Agua ≤ 3.000 ml/día.
- El plan depende de (peso, tasa, preferencia): cambiar cualquiera lo invalida o pide regenerar.
- No se envía ningún dato personal fuera del dispositivo.
