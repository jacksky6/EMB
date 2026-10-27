# AFC Configuration

[中文](README_CN.md)

These templates configure an EMB-C board for a two-, three-, four-, or five-lane EMU with AFC.

1. Select the directory matching the number of lanes.
2. Select `With-Front-Button-PCB` when using the EMU Front Button PCB, otherwise select `Without-Front-Button-PCB`.
3. Set the EMB-C CAN UUID in the selected `AFC_EMU_1.cfg`.
4. Copy `AFC_EMU_1.cfg` and `EMU_1.cfg` from that directory to the matching AFC configuration locations.
5. Restart Klipper after checking the AFC includes.

The selected directory already contains the final file names; no manual renaming is required. Back up an existing AFC configuration before replacing files.
