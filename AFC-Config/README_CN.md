# AFC 配置

[English](README.md)

这些模板用于将 EMB-C 主板配置为 AFC 的二、四或五通道 EMU。

1. 选择与实际通道数对应的目录。
2. 使用 EMU Front Button PCB 时选择 `With-Front-Button-PCB`，普通微动开关时选择 `Without-Front-Button-PCB`。
3. 在所选 `AFC_EMU_1.cfg` 中填入 EMB-C 的 CAN UUID。
4. 将该目录内的 `AFC_EMU_1.cfg` 和 `EMU_1.cfg` 复制到 AFC 对应的配置位置。
5. 检查 AFC include 后重启 Klipper。

所选目录中的文件已经是最终文件名，无需手动改名。替换已有 AFC 配置前请先备份。
