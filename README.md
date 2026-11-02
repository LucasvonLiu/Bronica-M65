# Bronica & M65 相机转接环开源项目 (Bronica-M65 Adapters)

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Format: 3DM / STL / STEP / 3MF](https://img.shields.io/badge/CAD-Rhino%20%7C%20STL%20%7C%20STEP-green.svg)](#文件架构说明)
[![MakerWorld](https://img.shields.io/badge/MakerWorld-Model%20Page-orange.svg)](https://makerworld.com/zh/models/3532041-bronicas-m65#profileId-4038566)

本项目为 **Bronica（勃朗尼卡 / 碧浪之家，如 Bronica S / S2 / S2A / EC 等中画幅相机系统）** 与 **M65 螺口对焦筒 / 镜头卡口** 的互转与改装适配套件。包含完整的工业建模源文件（Rhino `.3dm`）、可直接 3D 打印的网格模型（`.stl`）、切片工程（`.3mf` / `.gcode.3mf`）及参考工业图纸（`.step`）。

---

## 📖 项目简介 (Project Overview)

Bronica S 系列中画幅相机拥有经典的卡口系统（机身内外双卡口与内调焦螺纹），在现代胶片摄影与改装玩法中，常需要将其与通用性极高的 **M65 调焦筒（M65-M65 Helicoid）** 或其他镜头系统（如 Kiev 88B、⌀62.5mm 筒身镜头等）相互配合使用。

本项目提供了以下几个维度的转接方案：
1. **M65 转接至 Bronica 机身**：在 Bronica 相机机身上安装通用 M65 调焦筒或镜头。
2. **Bronica 镜头转接至 M65**：将 Bronica 原厂镜头转接到 M65 调焦组件上，可用于微单转接、移轴调焦或微距翻拍。
3. **Kiev 88B 卡口转 Bronica**：基辅 88（Kiev 88 / Salut）系列镜头转接至 Bronica 系统。
4. **⌀62.5mm 镜头筒转 M65**：将外径 62.5mm 的镜头筒身适配并锁紧在 M65 调焦螺口上。

---

## 📂 仓库结构与文件清单 (Directory Structure)

```text
Bronica-M65/
├── 01-工作文件/                      # Rhino 3D (Rhinoceros) 建模源工程文件与文档
│   ├── 1-M65-Bronica（Body）.3dm     # M65 转 Bronica 机身卡口源文件
│   ├── 2-Kiev88B.3dm                 # Kiev 88B 卡口测绘与转接源文件
│   ├── 3-⌀62.5（Lens）-M65.3dm       # ⌀62.5mm 镜筒转 M65 源文件
│   ├── 4-Bronica（Lens）-M65.3dm     # Bronica 镜头转 M65 源文件
│   ├── BronicaS-M65.3dm              # Bronica S 专用转接源文件
│   ├── BronicaS-M65.docx             # 拓竹 MakerWorld 与 GitHub 发布说明文档
│   └── BronicaS-M65.pdf              # 导出的 PDF 说明文档
│
├── 02-打印文件/                      # 3D 打印网格与工程模型 (STL & 3MF)
│   ├── M65-bronica-1.stl ~ 5.stl     # M65 转 Bronica 机身迭代件（推荐使用 v5 版本）
│   ├── Bronica-M65-1.stl ~ 2.stl     # Bronica 镜头转 M65 打印件
│   ├── Bronica-M65-1.3mf             # 打印工程文件
│   ├── kiev88-bronica-1.stl ~ 3.stl  # Kiev 88B 转 Bronica 打印件（推荐使用 v3 版本）
│   └── Z62.5-M65-1.stl ~ 4.stl       # ⌀62.5 镜头转 M65 打印件（推荐使用 v4 版本）
│
├── 03-参考文件/                      # 工业标准与第三方测绘参考图纸
│   ├── m65-hpf.step                  # M65 调焦螺纹基准模型 (STEP)
│   ├── Nikon_F_Mount - Kiev_88.step  # 尼康 F 口与 Kiev 88 卡口参考模型 (STEP)
│   └── k-z.3dm                       # 卡口及法兰基准参考
│
├── Bronica-M65-1.gcode.3mf           # Bambu Studio / OrcaSlicer 预切片打印配置
├── M65-bronica-5.gcode.3mf           # M65-bronica-5 切片打印配置 (PLA Black, 0.4 喷嘴)
├── .gitignore                        # Git 忽略文件（过滤临时锁文件与缓存）
├── LICENSE                           # MIT 开源授权协议
└── README.md                         # 项目说明文档
```

> **提示**：打印文件中的数字后缀（如 `1` ~ `5`）代表设计迭代版本，推荐优先选择**最大序号**的最新优化版本进行打印。

---

## 🖨️ 3D 打印与制造建议 (3D Printing Guidelines)

为确保卡口机械强度、法兰焦距精度以及光学消光性能，建议遵循以下参数设置：

| 参数项 | 推荐设置 | 说明 |
| :--- | :--- | :--- |
| **推荐材质** | **PLA-CF (碳纤PLA)** / **PETG** / **ABS / ASA** | 优先推荐 **PLA-CF** 或 **哑光黑 PETG**，具有极高的刚性、尺寸稳定性和天然消光质感 |
| **颜色** | **纯黑（消光黑 / Matte Black）** | 严禁使用半透明或高反光浅色耗材，避免内部杂光反射 |
| **喷嘴孔径** | `0.4 mm` (或 `0.2 mm`) | 0.4mm 兼顾打印速度与螺纹细节 |
| **层高 (Layer Height)** | `0.12 mm` - `0.16 mm` | 保证卡口法兰斜面与螺纹旋转顺滑无阶梯感 |
| **壁厚 (Wall Loops)** | `≥ 4 层` (推荐 5~6 层) | 增强结构受力时的机械抗扭刚度，避免锁紧断裂 |
| **填充率 (Infill)** | `35% ~ 50%` (Gyroid 或 Grid) | 建议适度增加填充以提高质量惯性与抗变形能力 |
| **支撑设置** | 根据悬空卡爪微调 (Tree Support) | 尽量避免支撑接触卡口接合面与螺纹面 |

### 📷 光学消光与防漏光处理
1. **内壁消光**：打印完成后，建议在转接环内壁喷涂**光学超黑消光漆**（如 Musou Black）或粘贴**超薄植绒消光胶带**，彻底消除中画幅反光镜箱和后组杂光。
2. **配合间隙**：由于各品牌 3D 打印机与耗材缩水率存在微小公差（通常在 `±0.05mm~0.1mm`），首次装配前可用细砂纸（1000 目+）轻微打磨卡爪过渡边缘，确保转动阻尼舒适且锁紧到位。

---

## 🛠️ 使用与二次开发 (Customization)

所有 CAD 原始模型均以 Rhino 3D 原生格式（`.3dm`）提供于 `01-工作文件` 目录中，支持在 **Rhinoceros 7 / 8** 中直接打开编辑；标准工业交换格式模型位于 `03-参考文件`（`.step`），可导入 **Fusion 360**、**SolidWorks**、**FreeCAD** 等主流 CAD 软件。

---

## 📄 开源协议 (License)

本项目采用 [MIT License](LICENSE) 授权开源。您可以自由修改、再分发、商业或非商业使用，但请保留原作者署名与开源协议声明。

---

*Designed & Shared by [LucasvonLiu (LIU Zhongze)](https://github.com/LucasvonLiu)*
