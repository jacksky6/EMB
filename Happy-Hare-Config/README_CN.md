# EMB-C 二/四/五通道 Happy Hare 配置

[English](README.md)

本目录适用于一块 EMB-C 主板驱动 2、4 或 5 个 EMU 通道。

## 文件

- `For-2-Lanes`：使用 EMB-C 的前两组接口，适用于 2 个 gate，含两种 Front Button PCB 配置。
- `For-4-Lanes`：适用于 4 个 gate，含两种 Front Button PCB 配置。
- `For-5-Lanes`：适用于 5 个 gate，含两种 Front Button PCB 配置。

先按实际通道数选择目录，再按是否使用 Front Button PCB 选择同后缀的一对文件。将所选 `mmu_hardware_unit0_*.cfg` 改名为 `mmu_hardware_unit0.cfg` 后复制到 Klipper 配置目录；在 `printer.cfg` 中 include 所选 `emb_*.cfg`，且该 include 必须位于 Happy Hare 生成配置之前。两种版本不可同时加载。

## LED 版本

- `mmu_hardware_unit0_with_Front_Button_PCB.cfg`：使用 EMU Front Button PCB。每路 GRBW 链为 5 颗，出口 LED 使用 `1-4`，入口 LED 使用 `5`。
- `mmu_hardware_unit0_no_Front_Button_PCB.cfg`：不使用 Front Button PCB。每路 GRBW 链为 2 颗，出口 LED 使用 `1`，入口 LED 使用 `2`。

`with_Front_Button_PCB` 版本的 GRBW 链长度、LED 映射和 eject button 均匹配 Front Button PCB；其 eject button 引脚使用 `^!`。`no_Front_Button_PCB` 版本使用普通微动开关，eject button 引脚保持 `^`。

编辑所选 `emb_*.cfg` 的 `canbus_uuid`，填入本机 EMB-C 的 CAN UUID。温湿度计部分依赖 [TCA9548A-klipper-addon](https://github.com/jacksky6/TCA9548A-klipper-addon)；未安装或不使用时，注释其中的 `[tca9548a mux1]` 和全部 `temperature_sensor` 段。

## Happy Hare 配置器选择

首次生成或需要彻底重建 HH 配置时运行 `./install.sh -i`，选择 `2) Replace`。

- MMU：`EMU v1.0`
- Gate 数量：选择与目录相同的 `2`、`4` 或 `5`
- MCU topology / Board type：`Shared / externally configured MCU`
- 启用 LED，并保留 EMU 的同步缓冲器（PSF）配置；最终 LED 链长度和分段由所选硬件配置文件决定。
- 不启用 `Has environment sensors?`。
- 不启用 `Enable managed fan(s)?`。
- 不启用 `Enable controller fan?`。
- 不启用 `Has enclosure heater(s)?`。
- 不启用 `Has eject buttons?`。

温湿度计、风扇和 eject 按钮均由所选 `emb_*.cfg` 提供；若在 HH 配置器中启用它们，HH 会额外生成同类段，造成配置重复或引脚冲突。第 5 路所用的 AHT 通道、风扇与 eject button 仅存在于五通道版本。

以后仅更新 Happy Hare 时可使用 `1) Merge/Refresh`。`emb_*.cfg` 不受 HH 管理，不会被 Refresh 修改；如 Refresh 重写了 `mmu_hardware_unit0.cfg`，再用对应通道数目录、相同 Front Button PCB 版本的硬件配置作为基准核对引脚。

4 通道配置的 TMC2209 UART 地址均为 `0`。5 通道配置中，第 4 路和第 5 路共用 `PC0`：第 4 路为地址 `0`，第 5 路为地址 `1`，不可互换。
