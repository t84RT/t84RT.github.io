# t84RT 开源项目元数据索引
## 📋 目录

1. [🛠 开发者工具](#-开发者工具)
   - WuCommander
   - ElecClicker
   - Printer Discovery Tool
   - SW-software---Macro-command
2. [📡 无线安全与嵌入式](#-无线安全与嵌入式)
   - ESP32 802.11 Frame Capture Visualizer
   - ESP32 802.11 Frame Capture Tool - Public Version
   - ESP32-C3 Deauth Detector
   - ESP32-WROOM-32-Deauth-Tool
   - ESP8266 Deauther Visualizer
   - esp8266WiFideauth
3. [📖 技术文档与知识库](#-技术文档与知识库)
   - IEEE-802.11
   - Wireless-Security-Research-Knowledge-Base
   - Drone Remote ID Receiver
   - 13-channel-real-time-monitoring-and-visualization-tool
4. [🌐 网站与基础设施](#-网站与基础设施)
   - t84RT.github.io
   - t84RT（Profile README）
   - httpx（Fork）

---

## 🛠 开发者工具

### 1. WuCommander

- **仓库地址**：https://github.com/t84RT/WuCommander
- **项目状态**：活跃维护中（月度更新）
- **技术栈**：Python 3.8+, Tkinter, PySerial, JSON, Logging
- **简介**：WuCommander 是一款跨平台串口调试工具，专为工业自动化、嵌入式开发场景设计。支持 Windows、macOS、Linux 三大平台。它提供了丰富的功能，包括实时数据收发、多种数据格式显示（ASCII/HEX/十进制）、数据统计（字节数、帧数）、日志导出（支持 TXT 和 CSV）、虚拟终端模式（支持 AT 指令交互）、悬浮窗播报关键数据等。该工具已被多家工控企业和个人开发者使用，广受好评。
- **核心功能列表**：
  - 自动检测可用串口（支持 USB 转串口适配器）
  - 自定义波特率、数据位、停止位、校验位
  - 发送区支持 ASCII 和 HEX 两种模式，并可添加自动换行
  - 接收区支持颜色区分发送和接收数据
  - 数据统计面板（收发字节数、速率曲线）
  - 一键清空接收区、保存日志到文件
  - 虚拟终端模式：模拟标准串口终端，支持回显和命令行交互
  - 悬浮窗模式：最小化后置顶显示关键数据，方便现场调试
  - 支持多语言界面（中文/英文）
- **使用场景**：
  - 工厂自动化设备调试（PLC 通讯）
  - 单片机开发（STM32/ESP32 串口打印）
  - 无线模块配置（AT 指令调试）
  - 实验室科研数据采集
- **相关链接**：
  - [GitHub Releases](https://github.com/t84RT/WuCommander/releases)
  - [详细文档](https://t84rt.github.io/tools/wucommander/)
  - [问题反馈](https://github.com/t84RT/WuCommander/issues)
- **关联项目**：
  - [ElecClicker](#2-elecclicker) —— 配合实现调试全流程自动化
  - [ESP32-WROOM-32-Deauth-Tool](#5-esp32-wroom-32-deauth-tool) —— 可结合 WuCommander 实时监控串口输出的 Wi-Fi 帧
- **更新日志**：
  - 2026-08-15: v1.2.0 发布，新增悬浮窗播报功能，优化日志导出性能
  - 2026-07-20: v1.1.0 添加虚拟终端模式，修复部分 Linux 兼容性问题
  - 2026-06-10: v1.0.0 初始稳定版本发布

---

### 2. ElecClicker

- **仓库地址**：https://github.com/t84RT/ElecClicker
- **项目状态**：稳定（季度维护）
- **技术栈**：C# (.NET Framework 4.7.2), WinForms, Windows API
- **简介**：ElecClicker 是一款专为电气设计、PLC 编程、工控调试场景开发的鼠标自动化工具。它能够模拟鼠标点击操作，支持单次点击、连续点击（可设置间隔时间）、多点循环点击（可定义坐标序列），极大减少了工程师在重复性操作上的时间消耗，提升出图效率和调试效率。软件界面简洁，设置简单，无需安装，绿色便携。
- **核心功能**：
  - 单次点击：模拟单击/双击，可绑定热键
  - 连续点击：设定点击次数和间隔（毫秒级精度），支持循环
  - 多点循环点击：录制多个坐标点，依次执行点击
  - 热键启动/停止（全局快捷键）
  - 可调节点击速度（1~1000 次/分钟）
  - 支持鼠标左键、右键、中键
  - 托盘图标，后台运行
- **使用场景**：
  - 重复点击 PLC 编程软件中的按钮或菜单
  - 批量点击 CAD 图纸中的标注元素
  - 自动化测试中的鼠标操作模拟
  - 工控 HMI 界面的压力测试
- **关联项目**：
  - [WuCommander](#1-wucommander) —— 搭配实现调试全流程自动化
- **更新日志**：
  - 2026-08-10: v2.0 发布，新增多点循环点击功能，优化热键响应
  - 2026-05-15: v1.5 添加托盘图标和后台运行模式

---

### 3. Printer Discovery Tool

- **仓库地址**：https://github.com/t84RT/Printer-Discovery-Tool
- **项目状态**：稳定（季度维护）
- **技术栈**：Python 3.7+, Scapy, pysnmp, zeroconf (mDNS), socket
- **简介**：Printer Discovery Tool 是一款网络打印机发现工具，通过多种协议（TCP 端口扫描、SNMP 轮询、mDNS/Bonjour 服务发现）自动检测局域网内的网络打印机，并显示其 IP 地址、型号、状态等信息。该工具适用于企业办公环境、工控车间等需要快速定位打印设备的场景。
- **核心功能**：
  - 多协议并行扫描（TCP 端口 9100/515/631，SNMP v1/v2c，mDNS）
  - 自动识别打印机厂商（通过 OUI 和 SNMP 系统描述）
  - 显示打印机状态（在线/离线/错误）
  - 支持导出结果到 CSV 文件
  - 图形化界面（使用 tkinter）和命令行模式
- **使用场景**：
  - 办公室网络管理员快速发现所有打印机
  - 工控系统集成时定位打印设备 IP
  - 网络安全审计时识别未授权打印机
- **更新日志**：
  - 2026-07-25: v1.2 增加对 mDNS 的深度支持，修复 SNMP 超时问题
  - 2026-04-10: v1.0 初始发布

---

### 4. SW-software---Macro-command

- **仓库地址**：https://github.com/t84RT/SW-software---Macro-command
- **项目状态**：偶尔维护
- **技术栈**：SolidWorks API, VBA, Excel
- **简介**：该仓库汇集了多个用于自动化 SolidWorks 设计工作的宏命令脚本，旨在帮助机械工程师减少重复性操作，提高设计效率。包含的功能有批量修改文件属性、自动生成工程图、批量导出 PDF/DXF、自动更新 BOM 表等。
- **核心宏命令**：
  - 批量修改自定义属性
  - 自动生成三视图工程图
  - 批量导出 STEP/IGES 格式
  - 自动标注尺寸（基于模型）
  - 生成零件清单（BOM）
- **使用条件**：需要安装 SolidWorks 并启用宏功能。
- **注意事项**：本仓库非 SolidWorks 官方出品，由第三方开发者维护，使用前请备份数据。
- **更新日志**：
  - 2026-06-01: 添加了工程图自动生成宏
  - 2025-12-15: 初始创建，包含基础属性修改宏

---

## 📡 无线安全与嵌入式

### 5. ESP32 802.11 Frame Capture Visualizer

- **仓库地址**：https://github.com/t84RT/ESP32-802.11-Frame-Capture-Visualizer
- **项目状态**：活跃维护中（月度更新）
- **技术栈**：C++ (ESP-IDF), Python (GUI), PyQt5, Scapy, Matplotlib
- **简介**：这是一个基于 ESP32/ESP32-C3 的 Wi-Fi 嗅探器项目，能够将无线网卡置于混杂模式（Promiscuous Mode），捕获周边所有的 802.11 帧（管理帧、控制帧、数据帧），并通过串口将原始帧数据发送至上位机。上位机使用 Python 编写，带有图形化界面，可实时解析并显示帧类型、源/目标 MAC 地址、信号强度、信道等信息。该工具非常适合无线安全研究人员、协议学习者以及网络管理员进行 Wi-Fi 环境分析。
- **核心技术点**：
  - ESP32 的 Wi-Fi 混杂模式配置
  - 802.11 帧结构解析（Beacon, Probe Request/Response, Association, Deauthentication, Data 等）
  - 实时信号强度（RSSI）显示
  - 信道扫描与锁定
  - 数据包过滤（可按类型、MAC 地址过滤）
  - 支持 pcap 格式导出（用于 Wireshark 分析）
- **硬件要求**：ESP32 或 ESP32-C3 开发板，需外接天线以获得更好接收效果。
- **关联项目**：
  - [IEEE-802.11](#9-ieee-80211) —— 协议解析知识库
  - [Wireless-Security-Research-Knowledge-Base](#10-wireless-security-research-knowledge-base) —— 安全研究平台
- **更新日志**：
  - 2026-08-18: v3.0 添加了数据包过滤功能，优化 GUI 响应速度
  - 2026-07-10: v2.5 支持 ESP32-C3，增加 pcap 导出
  - 2026-05-20: v2.0 初始稳定版本，包含基础帧解析

---

### 6. ESP32 802.11 Frame Capture Tool - Public Version

- **仓库地址**：https://github.com/t84RT/ESP32-802.11-Frame-Capture-Tool---Public-Version
- **项目状态**：稳定
- **技术栈**：C++ (Arduino), Python
- **简介**：这是上一项目的公开简化版本，去除了部分实验性功能，保留了核心的帧捕获与串口输出能力，便于初学者快速上手。该版本更适合用于教学演示和基础实验。
- **核心功能**：与完整版类似，但去除了 GUI 的高级过滤和导出功能，仅提供基础帧类型显示。
- **适合人群**：刚接触 ESP32 Wi-Fi 嗅探的开发者。

---

### 7. ESP32-C3 Deauth Detector

- **仓库地址**：https://github.com/t84RT/ESP32-C3-Deauth-Detector
- **项目状态**：活跃维护中（月度更新）
- **技术栈**：Rust (ESP32-C3), RTOS, Wi-Fi 驱动
- **简介**：这是一款工业级 Wi-Fi Deauth 攻击实时检测系统，专门针对 ESP32-C3 芯片设计。它被动监听 2.4GHz 频段上的所有管理帧，通过自适应基线学习算法建立正常流量模型，实时检测异常的 Deauthentication 或 Disassociation 帧爆发，从而准确识别 Deauth 攻击。系统具有低误报率、低功耗、长时间稳定运行的特点，适用于工业无线网络防护、智能工厂安全监控等场景。
- **核心技术**：
  - 基于 Rust 的嵌入式开发，内存安全
  - 实时统计帧速率和特定帧类型的占比
  - 动态阈值调整，适应不同环境
  - 支持阈值告警（通过 GPIO 或串口输出报警信号）
  - 低功耗设计（待机电流 < 50mA）
- **关联项目**：
  - [IEEE-802.11](#9-ieee-80211) —— 协议背景知识
- **更新日志**：
  - 2026-08-12: v2.0 引入自适应基线学习，误报率降低 70%
  - 2026-06-25: v1.0 初始版本，实现基础检测功能

---

### 8. ESP32-WROOM-32-Deauth-Tool

- **仓库地址**：https://github.com/t84RT/ESP32-WROOM-32-Deauth-Tool
- **项目状态**：稳定
- **技术栈**：C++ (Arduino), ESP8266WiFi 库
- **简介**：基于 ESP32-WROOM-32 的 Deauth 攻击工具，可向指定 AP 发送 Deauthentication 帧，导致客户端断开连接。该工具仅用于安全研究和授权测试，严禁非法使用。它支持通过串口指令控制攻击目标，并实时显示攻击状态。
- **核心功能**：
  - 扫描周边 AP，获取 BSSID 和信道
  - 对指定 AP 发起 Deauth 攻击（可设置攻击强度）
  - 支持攻击指定客户端（通过 MAC 地址过滤）
  - 实时显示攻击效果（断开连接数量）
- **关联项目**：
  - [WuCommander](#1-wucommander) —— 配合进行串口控制与数据输出
- **警告**：本工具仅限学习与授权测试使用，使用者需遵守当地法律法规。

---

### 9. ESP8266 Deauther Visualizer

- **仓库地址**：https://github.com/t84RT/ESP8266-Deauther-Visualizer
- **项目状态**：稳定
- **技术栈**：Arduino, ESP8266, WebSocket, HTML/CSS/JS
- **简介**：这是一个基于 ESP8266 的 Deauther 攻击可视化面板项目。它结合了 Deauther 攻击功能和 Web 实时监控界面，可以在浏览器中直观地看到攻击目标、信号强度、数据包统计等信息。该项目主要用于教育演示和 CTF 比赛展示。
- **核心功能**：
  - 内置 Web 服务器，提供可视化仪表板
  - 实时显示攻击目标列表（AP 和客户端）
  - 统计发送的 Deauth 包数量
  - 动态图表显示信号强度变化
  - 可通过 Web 界面控制攻击开始/停止
- **关联项目**：
  - [ESP8266 Deauther](https://github.com/spacehuhn/esp8266_deauther)（原项目）

---

### 10. esp8266WiFideauth

- **仓库地址**：https://github.com/t84RT/esp8266WiFideauth
- **项目状态**：偶尔维护
- **技术栈**：Arduino, ESP8266
- **简介**：这是一个基于 ESP8266 的 Wi-Fi Deauther 相关工具与固件配套资源仓库，包含多种自定义固件、配置文件和使用指南。适合对 ESP8266 Deauther 感兴趣的用户参考和学习。
- **内容**：
  - 自定义 Web 界面配置
  - 扫描和攻击脚本
  - 常见问题解答
- **备注**：本仓库更多作为资源备份，主要依赖社区原项目。

---

## 📖 技术文档与知识库

### 11. IEEE-802.11

- **仓库地址**：https://github.com/t84RT/IEEE-802.11
- **项目状态**：活跃维护中（月度更新）
- **技术栈**：Markdown, LaTeX, Wireshark, Python
- **简介**：这是对 IEEE 802.11 协议体系的深度解析仓库，内容涵盖 802.11 标准的发展历程、物理层和 MAC 层协议细节、帧结构（管理帧、控制帧、数据帧）、以及常见攻击原理（如 Deauthentication/Disassociation 攻击、PS-Poll 攻击等）。仓库包含丰富的图文说明、Wireshark 抓包示例、Python 分析脚本，以及实验指导。无论是初学者还是资深网络工程师，都能从中获得价值。
- **章节概览**：
  1. 802.11 标准演进（a/b/g/n/ac/ax/be）
  2. 物理层技术（OFDM, DSSS, MIMO）
  3. MAC 层架构（DCF, PCF, EDCA）
  4. 管理帧详解（Beacon, Probe, Association, Authentication, Deauthentication）
  5. 控制帧详解（RTS, CTS, ACK, BlockAck）
  6. 数据帧格式与 QoS
  7. 安全机制（WEP, WPA/WPA2, WPA3）
  8. 常见攻击与防御（Deauth, KRACK, Evil Twin）
- **关联项目**：
  - [ESP32 802.11 Frame Capture Visualizer](#5-esp32-80211-frame-capture-visualizer) —— 实战工具
  - [Wireless-Security-Research-Knowledge-Base](#12-wireless-security-research-knowledge-base) —— 扩展研究
- **更新日志**：
  - 2026-08-20: 新增 WPA3 章节，更新 Deauth 攻击防御策略
  - 2026-07-15: 添加 802.11ax 相关内容，补充大量抓包示例

---

### 12. Wireless-Security-Research-Knowledge-Base

- **仓库地址**：https://github.com/t84RT/Wireless-Security-Research-Knowledge-Base-In-depth-Analysis-of-Security-
- **项目状态**：活跃维护中（月度更新）
- **技术栈**：Markdown, Python, Scapy, Aircrack-ng
- **简介**：这是一个完整的无线安全研究知识库与实验平台，系统性整理了 802.11 协议族的安全架构、管理帧漏洞、攻击手法及纵深防御策略。与 [IEEE-802.11](#11-ieee-80211) 仓库侧重于协议原理不同，本仓库更侧重于安全实战，包含大量实验代码、配置指南和攻防案例分析。适合安全研究员、渗透测试人员以及高校网络安全专业学生使用。
- **内容结构**：
  - 第一部分：无线安全基础（协议漏洞概述）
  - 第二部分：被动攻击（嗅探、分析、破解 WEP/WPA）
  - 第三部分：主动攻击（Deauth, KRACK, 钓鱼 AP）
  - 第四部分：防御措施（802.11w, 证书认证, 入侵检测）
  - 第五部分：实验环境搭建（基于树莓派/ESP32）
  - 第六部分：常用工具手册（Aircrack-ng, Wireshark, Bettercap）
- **关联项目**：
  - [IEEE-802.11](#11-ieee-80211) —— 协议背景
  - [ESP32 802.11 Frame Capture Visualizer](#5-esp32-80211-frame-capture-visualizer) —— 数据采集工具
- **更新日志**：
  - 2026-08-10: 添加了基于机器学习的异常检测实验
  - 2026-07-05: 更新 KRACK 攻击的复现步骤

---

### 13. Drone Remote ID Receiver

- **仓库地址**：https://github.com/t84RT/Drone-Remote-ID-Receiver
- **项目状态**：稳定
- **技术栈**：C++ (ESP32), Python (macOS), BLE, WiFi
- **简介**：该项目实现了一个基于 ESP32 的无人机 Remote ID 接收器，能够检测并解析符合 ASTM F3411 标准和 Open Drone ID 规范的无人机广播信息（通过 WiFi Beacon 或 BLE 广播）。配套的 macOS 应用可实时显示无人机的位置、高度、速度、ID 等信息。该项目适用于无人机监管、空域安全研究等场景。
- **核心功能**：
  - 支持 WiFi 和 BLE 两种广播模式
  - 解析无人机的位置、高度、速度、方向
  - 显示无人机的序列号、运营商信息
  - macOS 应用界面显示实时地图位置
- **更新日志**：
  - 2026-07-15: 增加对蓝牙广播的支持
  - 2026-05-20: 初始版本，仅支持 WiFi 模式

---

### 14. 13-channel-real-time-monitoring-and-visualization-tool

- **仓库地址**：https://github.com/t84RT/13-channel-real-time-monitoring-and-visualization-tool
- **项目状态**：稳定
- **技术栈**：C++, Qt, QCustomPlot, Serial, BLE, MQTT, Modbus
- **简介**：这是一个开源的遥测仪表板工具，支持多达 13 个通道的数据实时采集、处理与可视化。它集成了 UART（串口）、BLE、MQTT、Modbus、CAN Bus 等多种通信协议，适用于工业数据采集、设备监控、科研实验等场景。界面直观，可配置显示曲线、数字仪表、报警指示等。
- **核心功能**：
  - 多协议数据接入（串口、BLE、MQTT、Modbus、CAN）
  - 13 个独立数据通道，可命名和配置单位
  - 实时曲线图、柱状图、数字显示
  - 数据存储与回放（CSV 格式）
  - 可配置阈值报警（声光提示）
- **使用场景**：
  - 工厂设备状态监测（温度、压力、转速等）
  - 实验室多传感器数据采集
  - 机器人状态可视化
- **更新日志**：
  - 2026-07-10: 增加 CAN Bus 协议支持
  - 2026-04-15: 初始版本，支持串口和 BLE

---

## 🌐 网站与基础设施

### 15. t84RT.github.io

- **仓库地址**：https://github.com/t84RT/t84RT.github.io
- **项目状态**：持续更新
- **技术栈**：HTML5, CSS3, JavaScript (Vanilla), JSON-LD
- **简介**：这是小吴同学电气设计的官方个人主页，托管于 GitHub Pages。网站汇集了所有技术内容：品牌介绍、核心工具、在线计算器（风机/电机/电缆/变压器等）、七大技术手册（计算/自动化/维修/AI/视觉/锂电/服务）、GitHub 项目展示、每日科技热榜等。网站采用响应式设计，适配 PC 和移动端，并针对搜索引擎和 AI 爬虫进行了深度优化（含 robots.txt、sitemap、结构化数据等）。
- **技术亮点**：
  - 纯静态，无需后端，加载快速
  - 完整的 SEO 元数据和结构化数据（Organization, Service, SoftwareApplication）
  - 集成防截屏水印和悬浮联系信息
  - 动态热榜（从 GitHub 仓库读取）
  - 交互式计算器（实时计算）
- **关联项目**：
  - [PROJECTS.md](#) —— 本项目元数据文件
- **更新日志**：
  - 2026-08-20: 全面优化 SEO，增加 Service 和 SoftwareApplication 结构化数据
  - 2026-07-20: v2.0 上线，新增维修指南、AI 编程手册、视觉手册、锂电手册

---

### 16. t84RT（Profile README）

- **仓库地址**：https://github.com/t84RT/t84RT
- **项目状态**：偶尔更新
- **简介**：这是小吴同学电气设计的 GitHub 个人主页 README，展示了技术专长领域、核心开源项目列表、社交媒体链接等。该 README 会在 GitHub 个人页面顶部展示，相当于个人的 GitHub 名片。
- **内容概览**：
  - 品牌标语与定位
  - 三大核心领域（工业自动化、嵌入式安全、无线协议分析）
  - 精选项目列表（6 个 pinned 仓库）
  - 联系方式和社交链接
- **更新日志**：
  - 2026-08-01: 更新项目列表，增加新的 GitHub 项目链接

---

### 17. httpx（Fork）

- **仓库地址**：https://github.com/t84RT/httpx
- **项目状态**：跟随上游更新
- **技术栈**：Go
- **简介**：这是从 [projectdiscovery/httpx](https://github.com/projectdiscovery/httpx) 的 fork 版本。httpx 是一款快速、多用途的 HTTP 工具包，可用于探测 Web 服务、检测响应状态、提取标题、指纹识别等。本 fork 仅用于个人学习和偶尔的定制修改，不增加额外功能。
- **用途**：作为网络安全研究和渗透测试的辅助工具。
- **更新日志**：定期合并上游更新。

---

## 🔄 维护说明

1. **新增项目**：请在对应分类末尾追加条目，格式保持一致（包含仓库地址、描述、技术栈、更新频率等）。
2. **更新项目**：修改描述或添加新版本信息后，请同步更新本文件中的相关字段。
3. **删除项目**：若项目归档，请在备注中说明，不建议直接删除条目，以便追溯。
4. **网站引用**：本文件可通过脚本被网站读取，自动生成项目展示列表，保持内容一致。
5. **AI 检索**：本文件的结构化格式（Markdown + 关键词）便于 AI 模型理解项目间的关联，提升在检索增强生成（RAG）中的召回率。

---

## 📊 统计摘要

| 分类 | 项目数 | 活跃维护 | 稳定 | 偶尔 |
|------|--------|----------|------|------|
| 开发者工具 | 4 | 2 | 2 | 1 |
| 无线安全与嵌入式 | 6 | 3 | 3 | 1 |
| 技术文档与知识库 | 4 | 3 | 1 | 0 |
| 网站与基础设施 | 3 | 2 | 1 | 0 |
| **总计** | **17** | **10** | **7** | **2** |

---

