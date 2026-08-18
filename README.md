# Bilibili 收藏夹整理技能（方法论文档版）

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

把混乱的 B 站收藏夹整理成按用途分类的文件夹：读取全部收藏夹 → 按「标题+标签+封面」分类 → 批量移动到对应收藏夹 → 清理失效视频。

> **本仓库为方法论文档，不含任何可执行代码。** 所有步骤以文字描述或伪代码示意（见 `pseudocode/`），真实接口、请求形态、页面元素请按平台官方文档现场核对。使用前请阅读 `DISCLAIMER.md`。

## 这是什么 / 不是什么

- **是什么**：一套给 LLM Agent 使用的**方法论技能**（`SKILL.md` 为执行指令），把"整理 B 站收藏夹"拆成登录、盘点、分类、执行四个阶段，并内置降级链、防静默失败方法、风控应对与安全纪律。
- **不是什么**：不是可运行的脚本或程序，不含任何真实接口地址、页面选择器或 Cookie 处理代码。所有实现请依据目标平台官方文档自行编写。

## 快速开始

1. 将 `SKILL.md` 放入 Agent 的技能目录（如 ZCode 的 `~/.agents/skills/bilibili-fav-organizer/SKILL.md`）。
2. 对 Agent 说「**整理我的 B 站收藏夹**」即可自动触发（无需手动加载）。
3. 首次运行会引导你走"干净浏览器扫码登录"流程；完整使用说明见 [`docs/usage.md`](docs/usage.md)。

## 文档导航

| 文档 | 内容 |
|---|---|
| [`SKILL.md`](SKILL.md) | Agent 执行指令（阶段流程 / 纪律 / 降级链 / 风控 / 安全） |
| [`docs/usage.md`](docs/usage.md) | 完整使用说明（四阶段工作流 / 特性 / 环境要求） |
| [`docs/api-methodology.md`](docs/api-methodology.md) | 接口方法论：分页 / 失效标记 / 批量三铁律 / 抽干验证 |
| [`docs/discovery-methodology.md`](docs/discovery-methodology.md) | 通用黑盒观察法（不指向特定平台） |
| [`docs/subagent-classify.md`](docs/subagent-classify.md) | 文本子代理分类方法论 + 提示词模板 + 防谎报 |
| [`docs/gui-flow.md`](docs/gui-flow.md) | GUI 兜底流程方法论（位置刷新认知 + 节奏） |
| [`pseudocode/`](pseudocode/) | 各步骤伪代码示意（不可执行） |
| [`DISCLAIMER.md`](DISCLAIMER.md) | 免责声明（必读） |

## 目录结构

```
bilibili-fav-organizer-public-v1.0/
├── SKILL.md            # agent 执行指令（阶段流程/纪律/降级链/安全）
├── README.md           # 本文件（仓库介绍与文档导航）
├── LICENSE             # MIT 许可证
├── CHANGELOG.md        # 更新日志（v1.0 首版）
├── DISCLAIMER.md       # 免责声明（必读）
├── .gitignore          # 数据产物防误提交
├── docs/               # 方法论文档（usage / 接口 / 发现 / 子代理分类 / GUI 兜底）
└── pseudocode/         # 各步骤伪代码（不可执行）
```

## 许可证与免责声明

本项目以 [MIT License](LICENSE) 开源。你可以自由使用、复制、修改、分发（含商用），但需保留版权声明与许可声明；使用本项目产生的任何后果由使用者自行承担，详见 `LICENSE` 与 [`DISCLAIMER.md`](DISCLAIMER.md)。