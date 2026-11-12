# stormy-sea-night

A single-file three.js scene: a 50 ft sloop under storm jib and deep-reefed main, working through seas and wind modelled on Hurricane Ivan (2004) under a full moon and fast-moving cloud. You steer it from the helm.

![View from the helm](captain-view.png)

![Chase view](preview.png)

## Run

Live: https://jaredevans.github.io/stormy-sea-night/

Or open `index.html` locally in a current Chrome, Safari or Edge. It needs WebGL 2 and an internet connection, because three.js r170 loads from the jsDelivr CDN.

## Controls

- `←` / `→`: rudder. The sails set themselves to the new wind angle and swap sides when you tack or gybe.
- `↑` / `↓`: sheet in / ease. Sheeting in gives more drive and more heel; easing spills wind and stands the boat up.
- `C`: cycle cameras (captain's eyes, just astern, chase, aerial, bow-on)
- Drag / scroll: orbit and zoom in the three outside views
- `L`: toggle deck lights
- `Space`: pause
- `H`: hide the readout

## Staying upright

Left alone, the boat holds its starting course close to the wind and sails on. Past about 69° of roll it capsizes: the screen says why and how long you stayed afloat, and the run restarts after 5 seconds. Two things put it over:

- A breaking crest striking it across the beam (roughly 50–130° off the wind), worse with the sheets hard in.
- Running downwind too fast: it surfs, broaches beam-on and is rolled.

To stay up:

- Keep the bow or the stern to the seas.
- Ease the sheets before turning across the waves, and when running downwind.
- Pointing closer than about 22° to the wind stalls the boat "in irons".

## Conditions

The sea and wind follow what was measured when Hurricane Ivan crossed Naval Research Laboratory wave gauges in the Gulf of Mexico on 15 September 2004 (Wang et al., *Science*, 2005).

| | Ivan, measured | This scene |
|---|---|---|
| Significant wave height | 17.9 m | 17.9 m |
| Largest waves | 27.7 m | top 1% average about 27 m |
| Wind | about 200 km/h (108 kt) | 109 kt, gusting higher |

Two deliberate departures: the full moon still breaks through the cloud, where a real eyewall sky would be solid overcast, and the boat keeps its storm sails, which no sail would survive in that wind.

## How it works

- Sea: twelve Gerstner wave trains, including cross seas up to 60° off the wind, with normals and foam computed per pixel. Five trains of similar size near the dominant wavelength drift in and out of step, so the biggest waves arrive unpredictably.
- Boat: heave, pitch and roll are driven by the same wave table the surface is drawn with.
- Sailing: speed follows a simple polar by true wind angle and sheet trim; knockdowns come from breaking crests on the beam.
- Sky: procedural moon, stars and cloud; moonlight dims as cloud crosses the moon.
- Rain, spray, navigation and deck lights, bloom.
