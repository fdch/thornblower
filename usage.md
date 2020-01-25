## Instruments

### fm || frequency modulation

This instrument is built upon the basic Frequency Modulation technique.

- onoff: `option`
- carrier frequency: `L1` (random)
- modulator frequency: `R1` (random)
- modulator amplitude: `R2`
- envelope shape: `square`
- envelope tempo: `triangle` (random)
- trigger rate: `L2`


### lor || lorenz noise

This is a noise that comes out of the computation of the Lorenz System of equations at different speeds.

- onoff: `circle`
- bandpass filter (vcf): `Left Analog`
- speed || pitch-like change: `R2` (NOTe: Very fast speeds result in computation overload. This is intentional. Be conscious and careful at higher speeds)

### im || impulse

This is a chaotic-like variant of the Frequency Modulator that consists of two generators.

- onoff: `PAD`
- generator A: `Left Analog`
- generator B: `Right Analog`

---

The following is just optional:

---

### gr || granular synthesis

This instrument consists of a Granular Synthesis patch that uses table lookup oscillators instead of buffers.

- onoff: `PS` (center button)
- wavetable and envelope shape (combined): `square` (random)
- trigger + duration: `L2`
- trigger + rate: `R2`


## Spatialization

At all times you can trigger a 4 channel spatialization that affects all instruments.

- Left-side
    - onoff: `Left Analog (press)`
    - position: `Left Analog`
- Right-side 
    - onoff: `Right Analog (press)`
    - position: `Right Analog`
