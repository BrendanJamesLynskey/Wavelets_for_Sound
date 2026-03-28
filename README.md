# Wavelets for Sound — Kronland-Martinet, Grossmann & Morlet

An interactive, animated guide to the pioneering work of Richard Kronland-Martinet, Alex Grossmann, and Jean Morlet — the Marseille group who first applied wavelet transforms to audio signals.

**[→ View the Live Guide](https://brendanjameslynskey.github.io/Wavelets_for_Sound/)**

---

## What's Inside

Eight chapters walk through the history, mathematics, and audio applications of wavelet transforms, with real-time interactive visualisations and audio playback throughout.

### 1 · Origins — From Seismology to Song
An illustrated timeline from Gabor's 1946 atoms through Morlet's seismic wavelets, Grossmann's mathematical formalisation, to Kronland-Martinet's first real-time implementation on the SYTER audio processor in 1985.

### 2 · The Continuous Wavelet Transform
Interactive comparison of CWT vs STFT on a chirp signal. See how the wavelet's adaptive time-frequency resolution outperforms the fixed-window spectrogram. Full equation derivations: the CWT integral, admissibility condition, and reconstruction formula.

### 3 · The Morlet Wavelet
Explore the Morlet wavelet interactively — adjust ω₀ and scale, see the time-domain waveform and frequency-domain bandpass shape update in real time. Listen to the wavelet as a sound.

### 4 · Sound Analysis — Seeing Music
Build CWT scalograms row-by-row for piano, chirp, vibrato, percussive, and two-note signals. Instantaneous frequency extraction via ridge following — watch the white ridge line track vibrato in real time. Adjustable vibrato rate and depth with audio playback.

### 5 · Wavelet Synthesis
Additive resynthesis from wavelet-extracted partials. Adjust the number of harmonics and decay rate, compare original vs resynthesised sound.

### 6 · Detection of Abrupt Changes
Transient detection in clicks, note onsets, and speech boundaries. Wavelet analysis reveals sharp events as vertical streaks across all scales.

### 7 · Sound Transformations
Kronland-Martinet's four landmark transformations:
- **Time-stretching** without pitch change (interactive stretch factor + audio)
- **Pitch-shifting** without time change
- **Time-varying wavelet filtering** (low-pass, high-pass, band-pass, notch — with audio A/B)
- **Cross-synthesis** (magnitude from one sound, phase from another)

### 8 · Legacy and Continuing Impact
The Marseille group's ongoing influence, from PRISM laboratory to modern signal processing. Full bibliography of key publications.

---

## Technical Details

* **Zero dependencies.** No npm, no bundler, no external libraries. All rendering uses the HTML Canvas API. Audio uses the Web Audio API.
* **All maths computed in real-time.** CWT scalograms, Morlet wavelets, ridge extraction, and spectral analysis are calculated on the fly in the browser.
* **Audio playback.** Every signal can be listened to via the Web Audio API — synthesised on demand, not pre-recorded.
* **Responsive.** Canvases scale with DPR for sharp rendering on Retina/HiDPI displays.
* **Single file.** Everything lives in `index.html`.

### What's computed where

| Visualisation | Algorithm | Notes |
|---|---|---|
| CWT scalogram | Morlet inner product at 40–50 scales | Brute-force, fast enough for N ≤ 512 |
| STFT spectrogram | Windowed DFT with Hann window | Adjustable window size |
| Ridge extraction | Argmax across scales at each time | Instantaneous frequency estimate |
| Additive resynthesis | Oscillator bank with extracted envelopes | Variable partial count |
| Wavelet filtering | Zero-out coefficients by scale | Four filter types |
| Audio synthesis | Web Audio API buffer playback | All sounds generated algorithmically |

---

## Key References

1. Grossmann, A. & Morlet, J. (1984). *Decomposition of Hardy Functions into Square Integrable Wavelets of Constant Shape.* SIAM J. Math. Anal. 15, 723–736.
2. Goupillaud, P., Grossmann, A. & Morlet, J. (1984). *Cycle-Octave and Related Transforms in Seismic Signal Analysis.* Geoexploration, 23, 85–102.
3. Kronland-Martinet, R., Morlet, J. & Grossmann, A. (1987). *Analysis of Sound Patterns through Wavelet Transforms.* Int. J. Pattern Recogn. Artif. Intell., 1(2), 273–302.
4. Grossmann, A., Holschneider, M., Kronland-Martinet, R. & Morlet, J. (1987). *Detection of Abrupt Changes in Sound Signals with the Help of Wavelet Transforms.* Advances in Electronics and Electron Physics, Suppl. 19.
5. Kronland-Martinet, R. (1988). *The Use of the Wavelet Transform for the Analysis, Synthesis and Processing of Speech and Music Sounds.* Computer Music Journal, MIT Press, 12(4), 11–20.
6. Grossmann, A., Kronland-Martinet, R. & Morlet, J. (1989). *Reading and Understanding Continuous Wavelet Transforms.* In Combes, Grossmann & Tchamitchian (Eds.), Wavelets, Springer.
7. Kronland-Martinet, R. & Grossmann, A. (1990). *Application of Time-Frequency and Time-Scale Methods to the Analysis, Synthesis and Transformation of Natural Sounds.* In Roads, De Poli & Picciali (Eds.), Representations of Musical Signals, MIT Press.

---

## License

MIT — use it however you like. Attribution appreciated but not required.
