# ADAU1979 FPGA 板 PCB 工程

ADAU1979 FPGA 板的 Altium Designer 硬件设计工程，含原理图、PCB、封装库、
版本快照与 DRC 检查输出。

## 目录结构

| 路径 | 内容 |
| --- | --- |
| `adau1979-fpga.PcbDoc` | PCB 线路板设计 |
| `adau1979_fpga.SchDoc` | 电路原理图 |
| `adau1979-fpga.PrjPcb` | Altium Designer 工程文件（集成以上两者） |
| `adau1979-fpga.OutJob` | 输出任务配置（Gerber / NC Drill / 装配图等） |
| `adau1979-fpga.PrjPcbStructure` | 工程结构定义 |
| `adau1979-fpga.pdf` / `.xlsx` | 原理图与 BOM 导出件 |
| `Libraries/` | 封装库与原理图符号库（含清单） |
| `History/` | Altium 自动版本快照（`~(N).PcbDoc.Zip` 等） |
| `Project Logs for adau1979-fpga/` | ECO 变更记录日志 |
| `Project Outputs for adau1979-fpga/` | DRC 设计规则检查报告 |

## 封装库

`Libraries/` 下按来源分四组：

| 子目录 | 说明 |
| --- | --- |
| `PcbLib/` | 本工程核心封装：`24位ad小板子`、`ADAU1979_Core`、`FPGA_Baseboard`、`OPA192`、`REF2030`、`FerriteBead` |
| `SchLib/` | 与上述封装对应的原理图符号 |
| `DSP_PcbLib/` | 从 DSP 大板工程导入的封装库（46 项：运放、电源、TVS、连接器、磁性器件等） |
| `DSP_SchLib/` | 与之对应的原理图符号库 |

完整清单见 `Libraries/README_库清单.md` 与 `Libraries/ALL_IMPORTED_LIBRARIES.md`。

## 版本历史

`History/` 保存 Altium Designer 每次保存时的自动快照，按 `~(N)` 编号递增，
可用于追溯设计演进过程。该目录体积较大（约 427MB），随工程保存持续增长。

## 相关仓库

| 仓库 | 内容 |
| --- | --- |
| `adau1979-fpga` | 24 位 AD PCB 工程总集：底板、DSP 大板与本工程，含对比分析文档 |
| `adau1979-single-ad-test` | 单颗 ADAU1979 完整测试工程（PL 采集 IP + Vitis 板端软件） |
| `ADAU1979_PL` | ADAU1979 PL 侧工程（Verilog、Block Design、IP 与约束） |
| `ad7606_ps` | AD7606 + Zynq PS 数据采集工程（Vivado / Vitis / 上位机） |
