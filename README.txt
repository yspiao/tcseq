TRANSIENT CLASSIFIER // DOS SEQUENCER
==================================

What this is
------------
A single-file web app that:
- Loads up to 200 audio files
- Decodes them via Web Audio (decodeAudioData)
- Runs a fast transient + band-energy analysis (no FFT) to classify rough type:
  KICK / SNARE / HAT / CLAP / BASS / PERC / FX
- Generates a motif-centered (anchor + controlled variation) step pattern
- Plays it with per-type accents so it feels intentional, not random

How to run (recommended)
------------------------
macOS / Linux:
  cd ./dos_transient_sequencer
  python3 -m http.server 8000
  open http://localhost:8000/index.html

Windows:
  cd .\dos_transient_sequencer
  py -m http.server 8000
  open http://localhost:8000/index.html

Notes
-----
- Browsers often block audio until a user gesture.
  If it’s silent, press PLAY once to unlock AudioContext.
- If something fails, press EXPORT LOG and send the log text to debug quickly.

Controls
--------
- Click cell: toggle hit (empty <-> hit)
- Right-click cell: cycle empty -> ghost -> hit -> accent
- Arrow keys: move cursor
- Space: toggle hit
- A: accent
- G: ghost
- M: mute row
- Tab: next sample
- 1..6: force category for selected sample
- Enter: preview selected sample

License
-------
You can use/modify this freely in your own projects. (No external dependencies.)
