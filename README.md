# stormy-sea-night

A single-file three.js scene: a 50 ft sloop under storm jib and deep-reefed main, working through ~15 m hurricane seas under a full moon and fast-moving cloud.

![Preview](preview.png)

## Run

Open `storm-yacht.html` in a current Chrome, Safari or Edge. It needs WebGL 2 and an internet connection, because three.js r170 loads from the jsDelivr CDN.

## Controls

- Drag / scroll: orbit and zoom
- `C`: cycle cameras (chase, on-deck, aerial, bow-on)
- `L`: toggle deck lights
- `Space`: pause
- `H`: hide the readout

## How it works

- Sea: eight Gerstner wave trains (dominant wavelength 140 m, period 9.5 s), with normals and foam computed per pixel.
- Boat: heave, pitch and roll are driven by the same wave table the surface is drawn with.
- Sky: procedural moon, stars and cloud; moonlight dims as cloud crosses the moon.
- Rain, spray, navigation and deck lights, bloom.
