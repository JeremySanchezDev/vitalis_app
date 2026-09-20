# 07 · Sistema de diseño — Nocturne

Interfaz oscura, compacta y tranquila. Referencia: `_ds/nocturne-…/readme.md` y `styles.css` del proyecto de diseño.

## Fundamentos

- **Fondo** `--color-bg` #161826; **texto** #e9e9ed; **acento único** #9184d9 (violeta). Sin negro ni blanco puros.
- **Rampas tonales** 100–900 (neutral y acento) en OKLCH: 700–900 rellenos suaves/bordes, 500 base, 100–300 texto sobre tintes.
- **Tipografía** Inter (títulos y cuerpo), peso máximo 500–600; jerarquía por tamaño y espacio.
- **Densidad** 0,70×; **radio** 8 px (tarjetas); píldoras/chips redondeados.
- **Iconos** Phosphor.
- **Elevación** `--shadow-sm/md/lg`; sin sombras apiladas.
- **Layout** asimétrico, alineado a la izquierda; botones **contorneados** (borde de acento sobre transparente), no rellenos.
- **Imágenes** dentro de `.lighten` (mezcla `lighten`), preferir fotos sobre fondo oscuro.

## Tema claro

Se reasignan los tokens invirtiendo el uso de las rampas (fondo #f3f5fe, superficie #fffffe, texto #161826, acento #5d5294), sin tocar estilos individuales.

## Colores funcionales de Vitalis

- Verde `#3ddc97` para fase de trabajo y destello de fin de descanso; tinta `#12211a` sobre verde.

## Componentes

Botones (`primary`, `secondary`, `ghost`, `icon`, `block`), etiquetas, campos, radios, control segmentado, tarjetas, navegación, tabla, diálogo. Estados: hover y pulsado con la rampa de acento; foco `:focus-visible` con contorno de 2 px; deshabilitado al 45 %.

## Componentes propios de Vitalis

- **Orbe del asistente** — esfera 3D animada (WebGL en el prototipo) con estados `idle`, `listening`, `speaking`, nivel de energía y tres tonos configurables. Ritmos: respira / rebota / ondea. Decorativo; siempre acompañado de texto.
- **Barra inferior** de 4 pestañas (Inicio, Dieta, Entreno, Perfil), pestaña activa marcada.
- **Tarjeta de respuesta** del asistente con acciones.
- **Anillo/barra de progreso** decorativos con cifra como fuente accesible.
- **Píldoras** de acción rápida (40 dp+), chips de elección (52 dp).

## Reglas

Do: baja saturación fuera del acento; espaciado compacto; acciones contorneadas.
Don't: inundar de acento (excepto destello verde), negro/blanco puros, títulos en negrita pesada.

## Recursos por producir

Bucles de animación por ejercicio grabados sobre negro (tratamiento `.lighten`); textos externalizados y traducidos.
