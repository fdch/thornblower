# thornblower

A Pure Data performance patch that works with the PS4 controller. It was used to perform with the Sonic Arts Ensemble at Ohio State University, in network with [Andreas Weixler](http://avant.mur.at/) and [Se-Lien Chuang](http://avant.mur.at/chuang/index.html)'s [iScore](http://avant.mur.at/research/iScore/index.html)

## Usage

```
git clone https://github.com/fdch/thornblower
cd thornblower
pd main.pd
```

## Dependencies

You need the following Pure Data libraries available via `deken`:
- hidio: for the `[hidio]` object to get the PS4 controller data
- else: for `[else/pan4~]` object
- fd_lib: for the following objects (macos only, but you can replace them with abstractions): 
    - iterate.pd_darwin
    - lorenz.pd_darwin
    - minimax.pd_darwin
    - mtwister.pd_darwin
    - counter.pd_darwin
    - crand.pd_darwin

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

### gr || granular synthesis

This instrument consists of a Granular Synthesis patch that uses table lookup oscillators instead of buffers.

- onoff: `PS` (center button)
- wavetable and envelope shape (combined): `square` (random)
- trigger + duration: `L2`
- trigger + rate: `R2`

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

## Spatialization

At all times you can trigger a 4 channel spatialization that affects all instruments.

- Left-side
    - onoff: `Left Analog (press)`
    - position: `Left Analog`
- Right-side 
    - onoff: `Right Analog (press)`
    - position: `Right Analog`

## Network

Since the patch was used with [Andreas Weixler](http://avant.mur.at/) and [Se-Lien Chuang](http://avant.mur.at/chuang/index.html)'s live notation software [iScore](http://avant.mur.at/research/iScore/index.html) written in Max/MSP, a network is established between Pure Data and a custom-hacked version of iScore (with kind permission of the authors :). To get iScore, visit [this website](http://avant.mur.at/research/iScore/index.html)

The purpose of this hack is to replace the iScore's page-turning gesture tracking with a button click on the controller (the `share` button). This reduced greatly the computation need of iScore and allows both patches to run simultaneously on the same computer. Furthermore, by accessing the score number within Pure Data one can make presets for the instruments according to which score is playing. However, this turned out to be more limiting than enabling for performance and the preset system remained unused.



