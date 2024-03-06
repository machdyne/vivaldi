# Vivaldi Motherboard

Vivaldi is a host board that when paired with a [Sechzig](https://github.com/machdyne/sechzig) compute module can function as a personal server, network gateway or firewall.

![Vivaldi](https://github.com/machdyne/vivaldi/blob/4c827327fc69c10ec3e9044bc0cccf6bd3b227a4/vivaldi.png)

This repo will contain schematics, PCB layouts, pinouts and documentation.

Find more information on the [Vivaldi product page](https://machdyne.com/product/vivaldi-motherboard/).

## Using Vivaldi

Vivaldi requires a Sechzig module to function. **When inserting a Sechzig module, make sure that pin 2 on Vivaldi and pin 2 on the module are both on the same side.**

## Firmware

Mozart has a JTAG and USB CDC interface that are both accessible on the USB-C port. These interfaces are provided by a [fork of pico-dirtyJtag](https://github.com/machdyne/vivaldi/tree/main/firmware). You can update the RP2040 firmware by holding down the BOOT button and then applying power.

To build the firmware from source:

```
$ cd firmware/pico-dirtyJtag
$ mkdir build
$ cmake .. -DPICO_DEFAULT_BOOT_STAGE2_FILE=$PICO_SDK_PATH/src/rp2_common/boot_stage2/boot2_generic_03h.S
$ make
```

## Pinouts

### LVDS Port

Vivaldi has an experimental SATA-style LVDS port. SATA is not supported.

| Pin | Signal |
| --- | ------ |
| 1 | GND |
| 2 | DS2\_P |
| 3 | DS2\_N |
| 4 | GND |
| 5 | DS1\_P |
| 6 | DS1\_N |
| 7 | GND |

## License

The contents of this repo are released under the [Lone Dynamics Open License](LICENSE.md) with the following exceptions:

- The KiCad design files contain parts of the [kicad-pmod](https://github.com/mithro/kicad-pmod) library which is released under the [Apache License, Version 2.0](https://www.apache.org/licenses/LICENSE-2.0.html).

- The KiCad design files may contain symbols and footprints released under other licenses; please contact us if we've failed to give proper attribution.

Note: You can use these designs for commercial purposes but we ask that instead of producing exact clones, that you either replace our trademarks and logos with your own or add your own next to ours.
