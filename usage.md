## Instruments

### fm || frequency modulation

This instrument is built upon the basic Frequency Modulation technique.

- onoff: `option`
- carrier frequency: `L1` (random)
- modulator frequency: `R1` (random)
- modulator amplitude: `R2`
- trigger rate: `L2`
- envelope shape: `square`
- envelope tempi: `triangle` (random)


### lor || lorenz noise

This is a noise that comes out of the computation of two Lorenz System of equations, one for each channel.

- onoff: `circle`
- speed || pitch-like change: `L2 R2` (NOTE: Very fast speeds result in computation overload. This is intentional. Be conscious and careful at higher speeds)

### im || impulse

This is a chaotic-like variant of the Frequency Modulator that consists of two generators, one for each channel.

- onoff: `PAD`
- generator 1: `Left Analog`
- generator 2: `Right Analog`
- envelope shape: `square`

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


---

See [README.md](README.md) and [download.md](download.md) for instructions.