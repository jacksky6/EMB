# Happy Hare Configuration

[中文](README_CN.md)

These templates configure an EMB-C board for a two-, four-, or five-gate EMU with Happy Hare.

1. Select the directory matching the number of gates.
2. Select `With-Front-Button-PCB` when using the EMU Front Button PCB, otherwise select `Without-Front-Button-PCB`.
3. Copy the selected `mmu_hardware_unit0.cfg` to the Klipper configuration directory.
4. Set the EMB-C CAN UUID in the selected `emb.cfg`, then include it from `printer.cfg` before the Happy Hare generated configuration.
5. Configure Happy Hare for EMU with a shared/external MCU.

The selected directory already contains the final file names; no manual renaming is required. Only load one Front Button PCB variant.

See [README_CN.md](README_CN.md) for the complete Chinese instructions.
