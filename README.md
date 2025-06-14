# AnatomyOfAnIonTrap
plans for a demonstrator

## Advanced ion trap quantum processors...
...have a lot of cool stuff packed into a rather tiny space. They are multi-layerd assemblies of metallic and insulating structures on the micron scale.

![image](https://github.com/user-attachments/assets/905b6b27-cd1d-4a96-94e6-0631858f96d2)

![image](https://github.com/user-attachments/assets/1edaa4ea-5e85-4fdb-bc39-e6a98a147d2c)

![image](https://github.com/user-attachments/assets/6642e2ec-d7ae-436d-896e-7306f81abc69)

technical/science details: https://arxiv.org/pdf/1908.00267

## Do such things exist out in the world

Surprisingly I struggled to find much in the way of similar 3d printed microchip devices

https://medium.com/@thorstenknoll/open-source-ic-cells-as-3d-prints-a-rough-how-to-guide-90a8bc8b3b57

## What to 3D print
There are options I think:

- a monolithic **semi-transparent block**, fairly accurately matching a real trap but scaled up and probably with some exaggerated feature sizes for visibility - durable
- **puzzle type assembly** that can be taken apart to explore the inside, and put back together - interactive
- **integrated LEDs** in a semi-hollow / cutaway, and a bank of buttons to light up certain features: trap RF, MW antenna, atomic oven, gradient coils, laser waveguide, readout detector, integrated electronics, even an ion on top maybe
- a fanned-open deconstructed set of layers (book-fold page-fan ...)

## Workflow

- Sussex team to convert real trap geometry files (.gds) over to blender format. 
- Send an early simple test over for 3D print test
- Revise the layout to add more interesting details and the active elements

## Layers

from the top down...

| Layer ID  | Component  | Real Material  | Print color  | Notes  |
| ----- | ----- | ----- | ----- | ----- |
| 0 | Ions ? | Ytterbium | white | Potential LED to show fluorescence |
| 1 | Electrode | gold | yellow | Potentially different classes: DC, RF in distinct colours|
| 1a | Electrode oxide | SiO2 | clear/translucent |  |
| 2 | Ground-plane | gold | orange | Has some small gaps for signal vias |
| 2a | Oxide vias | gold | orange | vertically connecting through from L1 to L3a |
| 3 | Main oxide | SiO2 | clear | many elements embedded within this layer |
| 3a | Signal routing | gold | orange | Has some small gaps for signal vias |
| 3b | Photon detector | MoSi | blue | ----- |
| 3c | Micro heater | platinum | red | Potentially LED to show heating |
| 4 | Substrate | silicon | translucent | Should be slightly opaque compared to oxide |
| 4a | Gradient coil | copper | green | Potentially chaser LEDs to show flow around ion sites |
| 5 | Laser waveguide | AlOx, SiN | clear ? | illuminated by LEDs at ends, grating fans under ion sites |
| 5a | Trench capacitors | poly-silicon | blue | maybe omit |
| 5b | Through Si Vias | poly-silicon | grey | maybe omit |

## Active LED bits

#### L0: ions
this would be a small number of individual [through-hole type RGB LEDs](https://uk.rs-online.com/web/p/leds/2545725) mounted at interesting locations requiring 'invisible'/discreet control wires back to appropriate PWM current drivers. Or maybe single pixel RGB things with built-in SPI contrlled drivers would be more practical (if a bit less invisible when not lit up)

#### L3c: oven micro-heater
this would be a small number of individual LEDs, just like above, or even simpler red-only would do for these.

#### L4a: current flow in 'gradient coils'
this would be a [chaser stip of some kind](https://uk.rs-online.com/web/p/led-strip-lights/1245482) inserted under or inside the copper tracks. The chaser strip is typically implemented as a shift register so an arduino or raspberry would generate the SPI signal needed.

#### L5: laser waveguide
this would be a light-pipe type of situation, potentially itself 3D-printed, or otherwise something [off-the-shelf](https://uk.rs-online.com/web/p/led-light-pipes/8796493)

