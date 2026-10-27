# AFC Configuration

[中文](README_CN.md)

These templates configure an EMB-C board for a two-, four-, or five-lane EMU with AFC.

1. Select the directory matching the number of lanes.
2. Select the `AFC_EMU_1_*` file matching the Front Button PCB hardware.
3. Set the EMB-C CAN UUID in the selected `AFC_EMU_1_*.cfg`.
4. Copy it as `AFC_EMU_1.cfg` and copy the matching `EMU_1.cfg` to AFC's `mcu/` directory.
5. Restart Klipper after checking the AFC includes.

Back up an existing AFC configuration before replacing files.
