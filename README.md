# thornblower

![ps4-guide](https://raw.githubusercontent.com/fdch/thornblower/master/img/ps4-guide.jpg)

A Pure Data performance patch that works with the PS4 controller. It was first used to perform with the Sonic Arts Ensemble at Ohio State University, in network with [Andreas Weixler](http://avant.mur.at/) and [Se-Lien Chuang](http://avant.mur.at/chuang/index.html)'s [iScore](http://avant.mur.at/research/iScore/index.html)

It was then used in multiple performances, such as:

- [https://www.facebook.com/lacupulagaleria/videos/553716875479273](https://www.facebook.com/lacupulagaleria/videos/553716875479273)
- [https://www.facebook.com/lacupulagaleria/videos/2462355797355865](https://www.facebook.com/lacupulagaleria/videos/2462355797355865)

## Acknowledgements

- Miller Puckette and the Pure Data community
- Alexandre Torres Porres for the `else` library
- Benitoite for giving `hidio` a revival
- Brian Thomas and Joaco Cámara for lending me their PS4 Controllers :)


## Usage

```
git clone https://github.com/fdch/thornblower
cd thornblower
pd main.pd
```

## Dependencies

You need the following Pure Data libraries available via `deken` (`Help>Find Externals`):
- hidio: for the `[hidio]` object to get the PS4 controller data. This can be searched with `deken` or in Benitoite's [github repo](https://github.com/Benitoite/hidio). Alternatively, you can install danomatika's [joyosc](https://github.com/danomatika/joyosc) and reassign some receives... 
- `fd_lib`: availble via `deken`, or [here](https://github.com/fdch/fd_lib)

optional: 
- else: for `[else/pan4~]` object (only used in 4-channel mode)

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

