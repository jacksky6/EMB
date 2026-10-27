# Happy Hare Configuration

[中文](README_CN.md)

These templates configure an EMB-C board for a two-, four-, or five-gate EMU with Happy Hare.

1. Select the directory matching the number of gates.
2. Select the matching `with_Front_Button_PCB` or `no_Front_Button_PCB` pair.
3. Rename the selected `mmu_hardware_unit0_*.cfg` to `mmu_hardware_unit0.cfg` and place it in the Klipper configuration directory.
4. Include the selected `emb_*.cfg` from `printer.cfg` before the Happy Hare generated configuration, then set its `canbus_uuid`.
5. Configure Happy Hare for EMU with a shared/external MCU.

See [README_CN.md](README_CN.md) for the complete Chinese instructions.
