# stormy-sea-night

A single-file three.js scene: a 50 ft sloop under storm jib and deep-reefed main, working through ~15 m hurricane seas under a full moon and fast-moving cloud.

![Preview](preview.png)

## Run

Live: https://jaredevans.github.io/stormy-sea-night/

Or open `index.html` locally in a current Chrome, Safari or Edge. It needs WebGL 2 and an internet connection, because three.js r170 loads from the jsDelivr CDN.

## Controls

- `←` / `→`: rudder. The sails set themselves to the new wind angle and swap sides when you tack or gybe.
- `↑` / `↓`: sheet in / ease. Sheeting in gives more drive and more heel; easing spills wind and stands the boat up.
- Drag / scroll: orbit and zoom
- `C`: cycle cameras (chase, on-deck, aerial, bow-on)
- `L`: toggle deck lights
- `Space`: pause
- `H`: hide the readout

## Staying upright

Left alone, the boat holds its starting course close to the wind and sails on. The danger is a breaking crest striking it beam-on, and it is worse with the sheets hard in: past about 69° of roll it capsizes, the screen says why and how long you stayed afloat, and the run restarts after 5 seconds.

- Keep the bow or the stern to the seas.
- Ease the sheets before turning across the waves.
- Pointing closer than about 22° to the wind stalls the boat "in irons".

## How it works

- Sea: eight Gerstner wave trains (dominant wavelength 140 m, period 9.5 s), with normals and foam computed per pixel.
- Boat: heave, pitch and roll are driven by the same wave table the surface is drawn with.
- Sailing: speed follows a simple polar by true wind angle and sheet trim; knockdowns come from breaking crests on the beam.
- Sky: procedural moon, stars and cloud; moonlight dims as cloud crosses the moon.
- Rain, spray, navigation and deck lights, bloom.
