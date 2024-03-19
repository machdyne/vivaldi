# Vivaldi Motherboard

Vivaldi is a host board that when paired with a [Sechzig](https://github.com/machdyne/sechzig) compute module can function as a personal server, network gateway or firewall.

![Vivaldi](https://github.com/machdyne/vivaldi/blob/4c827327fc69c10ec3e9044bc0cccf6bd3b227a4/vivaldi.png)

This repo contains schematics, PCB layouts, pinouts and documentation.

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

## Funding

This project was partially funded through the NGI0 Entrust Fund, a fund established by NLnet with financial support from the European Commission's Next Generation Internet programme.

## License

This project is released under the [CERN-OHL-P](LICENSE.txt) license.

Note: You can use these designs for commercial purposes but we ask that instead of producing exact clones, that you either replace our trademarks and logos with your own or add your own next to ours.
