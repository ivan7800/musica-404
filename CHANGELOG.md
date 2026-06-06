# CHANGELOG — MUSICA 404

Todas las versiones significativas del proyecto, en orden cronológico.

---

## [2.0.0] — Fase 2: Samples + Steps Variables

### Añadido
- **8 pistas** (antes 6): nuevas pistas LEAD y SAMP
  - LEAD: sintetizador de melodía independiente (square + detune), diferente timbre al PAD
  - SAMP: pista libre de sample sin rol predefinido
- **Sistema de samples cargables por pista**
  - Drag & drop de archivos de audio (`.wav`, `.mp3`, `.ogg`) sobre la etiqueta de pista
  - Clic en la etiqueta para abrir el explorador de archivos
  - Indicador visual de sample cargado (nombre en ámbar)
  - Pitch shift por nota: la velocidad de reproducción ajusta la afinación (C3 como raíz)
  - Samples propagados automáticamente a todos los patrones del mismo proyecto
- **Steps variables por pista**: selector 8 / 16 / 32 pasos independiente por pista
  - El secuenciador adapta su ancho al número de pasos de cada pista
  - El ciclo del patrón sigue a la pista más larga
  - Celdas fuera del rango aparecen en gris transparente e inactivas
- **Toggle SYNTH / SMPL por pista**: alterna entre síntesis procedural y sample propio
- **Samples embebidos en JSON**: Export JSON incluye los samples en base64, Import JSON los restaura
- **Samples renderizados en WAV y Stems**: el renderizado offline usa el sample real si está disponible
- Nuevo MIDI map extendido a 3 octavas (C1–G4)
- Presets actualizados para usar las 8 pistas (LEAD con patrones melódicos en todos los estilos)
- Ambient preset con steps de 32 en PAD y LEAD para texturas largas
- Nota raíz C3 en samples para pitch shift coherente

### Cambiado
- Mixer expandido a 8 canales
- Selector de nota expandido a 26 notas (C1–G4)
- Grid del secuenciador dinámico según maxSteps del patrón activo
- SAMP en modo synth usa noise burst de placeholder hasta cargar sample

---

## [1.0.0] — Fase 1: Bug Fixes + Optimizaciones

### Corregido
- **Swing roto**: reescrito con tabla de offsets. Steps impares se retrasan, pares se acortan compensando — el tempo no se alarga
- **Swing ignorado en Export WAV/Stems**: el renderizador offline ahora usa la misma fórmula de swing que el motor en vivo
- **`paintTimeline` reconstruía el DOM 16 veces por segundo** durante playback: sustituido por `paintTimelineBar()` que solo hace toggle de clases CSS
- **Mixer destruía el foco del slider** en cada movimiento de `oninput`: sliders vinculados directamente al proyecto sin re-render del mixer
- **`save()` guardaba nombre vacío**: ahora solo sobreescribe `project.name` si el campo no está vacío
- **`noteToMidi` desincronizada**: mapa MIDI alineado con el array `NOTES` incluyendo D4
- **Fin de canción sin comportamiento**: para limpiamente al llegar al último bar activo
- **`clearPattern` no informaba del patrón**: ahora muestra la letra del patrón (A, B, C...)
- **FX siempre sonaba igual**: frecuencia del bandpass aleatorizada por disparo (600–3600 Hz)
- **Arranger solo avanzaba**: clic derecho retrocede, doble clic vacía la barra

### Añadido
- Botón **LOOP ON/OFF** para bucle del song arranger
- Labels de controles con unidades (Hz, bpm, %)
- Estado del `status` con colores: verde (ok) y rojo (error)
- Selector de nota visual en popup (reemplaza el ciclo ciego con clic derecho)
- Beats del header del secuenciador marcados en ámbar
- Retrocompatibilidad en `load()` e `importJson()`: rellena pistas faltantes sin romper proyectos antiguos

---

## [0.1.0] — Versión inicial

### Incluido
- Secuenciador de 16 steps × 6 pistas (KICK, SNARE, HAT, BASS, PAD, FX)
- 6 patrones (A–F)
- Song Arranger de 16 compases
- Síntesis procedural por pista con Web Audio API
- Filtro master lowpass, resonancia, drive (waveshaper)
- Swing básico
- Mixer con volumen, pan, mute y solo
- Mutate y Humanize
- Presets: TECHNO, AMBIENT, HORROR, DNB
- Export WAV, MIDI real `.mid`, Stems WAV, JSON
- Import JSON
- Guardado en localStorage
- Diseño responsive con estética rave/industrial
- Un solo archivo HTML, sin dependencias
