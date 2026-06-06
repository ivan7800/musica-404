# 🎛️ MUSICA 404

> Secuenciador musical web por bloques inspirado en **Music 2000 (PSX)**, trackers clásicos y estética rave/industrial.  
> Un solo archivo HTML. Sin instalación. Sin dependencias. Abre y suena.

---

## ✨ Características

### Motor de audio
- **8 pistas independientes**: KICK · SNARE · HAT · BASS · LEAD · PAD · FX · SAMP
- **Síntesis procedural** por pista: osciladores, wavetable, ruido filtrado
- **Sistema de samples propio**: carga tus `.wav`, `.mp3` u `.ogg` por drag & drop o explorador
- Pitch de samples ajustado por nota (C3 como raíz)
- Filtro master lowpass con resonancia y drive (waveshaper)
- Swing real: redistribuye el tiempo sin alterar el tempo

### Secuenciador
- **Steps variables por pista**: 8, 16 o 32 pasos — cada pista independiente
- El ciclo del patrón se ajusta a la pista más larga
- 6 patrones (A–F) con cambio en caliente durante playback
- Modo SYNTH / SMPL por pista con toggle
- Selector visual de nota (popup) para pistas melódicas
- Acento por doble clic (velocidad alta/baja)
- Probabilidad por celda (Humanize)

### Song Arranger
- 16 compases configurables
- Clic izquierdo: avanza patrón (A→F→vacío)
- Clic derecho: retrocede
- Doble clic: vacía el compás
- Secciones automáticas: INTRO / BUILD / DROP / BREAK / OUTRO
- Modo LOOP para canción completa

### Mixer
- Volumen y pan por pista (sin re-render en cada movimiento)
- Mute y Solo por pista
- Actualización en tiempo real sin interrumpir el audio

### Presets incluidos
| Preset | BPM | Estilo |
|--------|-----|--------|
| TECHNO | 128 | Dark techno con kick en cuatro y bassline |
| AMBIENT | 92 | PSX ambient con pads largos de 32 steps |
| HORROR | 76 | Textura industrial con resonancia alta |
| DNB | 172 | Drum & bass con patrones roto-breaks |

### Exportación
| Formato | Descripción |
|---------|-------------|
| **WAV** | Canción completa renderizada offline con swing |
| **STEMS** | Un WAV por pista para mezclar en DAW |
| **MIDI** | Archivo `.mid` estándar con todos los eventos |
| **JSON** | Proyecto completo con samples embebidos en base64 |

### Herramientas creativas
- **MUTATE**: altera aleatoriamente celdas, velocidades y notas
- **HUMANIZE**: variaciones de velocidad y probabilidad por celda
- **LIMPIAR PATRÓN**: resetea el patrón activo

---

## 🚀 Uso rápido

```
1. Abre index.html en cualquier navegador moderno
2. Pulsa PLAY
3. Elige un preset o arrastra tu propio sample sobre una pista
4. Edita celdas en vivo
5. Monta la canción en el Song Arranger
6. Exporta WAV, MIDI o JSON
```

### Controles del secuenciador

| Acción | Resultado |
|--------|-----------|
| Clic en celda | Activar / desactivar |
| Doble clic | Toggle acento (vel alta/baja) |
| Clic derecho (pistas melódicas) | Selector visual de nota |
| Arrastrar audio a la pista | Cargar sample |
| Clic en etiqueta de pista | Abrir explorador de archivos |
| Botones 8 / 16 / 32 | Longitud de steps de la pista |
| SYNTH / SMPL | Alternar motor de sonido |

---

## 🌐 GitHub Pages

1. Sube el repositorio a GitHub
2. Ve a **Settings → Pages**
3. Source: `Deploy from a branch` → `main` → `/ (root)`
4. La app estará en `https://tu-usuario.github.io/musica-404`

---

## 📁 Estructura del repositorio

```
musica-404/
├── index.html      ← aplicación completa (un solo archivo)
├── README.md       ← este archivo
├── CHANGELOG.md    ← historial de versiones
└── LICENSE         ← MIT
```

---

## 🔧 Compatibilidad

- Chrome 90+ ✅
- Firefox 88+ ✅
- Edge 90+ ✅
- Safari 15+ ✅ (puede pedir interacción antes de iniciar audio)
- Sin servidor necesario — funciona desde `file://`

---

## 📜 Licencia

MIT — libre para usar, modificar y distribuir.  
Ver `LICENSE` para los detalles completos.

---

## 🙏 Inspiración

- **Music 2000 / MTV Music Generator** (Codemasters, PSX, 1999)
- **FastTracker II** y la cultura tracker
- La escena rave e industrial de los 90
