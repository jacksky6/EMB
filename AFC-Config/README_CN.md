# AFC 配置

[English](README.md)

这些模板用于将 EMB-C 主板配置为 AFC 的二、四或五通道 EMU。

1. 选择与实际通道数对应的目录。
2. 选择与 Front Button PCB 硬件对应的 `AFC_EMU_1_*` 文件。
3. 在所选 `AFC_EMU_1_*.cfg` 中填写 EMB-C 的 CAN UUID。
4. 将其作为 `AFC_EMU_1.cfg` 复制，并将对应的 `EMU_1.cfg` 复制到 AFC 的 `mcu/` 目录。
5. 检查 AFC include 后重启 Klipper。

替换已有 AFC 配置前请先备份。
