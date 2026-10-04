<!-- 他山协会 Logo -->
<p align="center">
  <a href="https://tashan.ac.cn" target="_blank" rel="noopener noreferrer">
    <img src="docs/assets/tashan.svg" alt="他山 Logo" width="280" />
  </a>
</p>

<p align="center">
  <strong>他山 PPT 制作 Skills</strong><br>
  <em>Tashan Presentation Craft Skills</em>
</p>

<p align="center">
  <a href="#项目简介">项目简介</a> •
  <a href="#快速开始">快速开始</a> •
  <a href="#三个组件的关系">组件关系</a> •
  <a href="#输入与交互流程">输入与交互流程</a> •
  <a href="#案例与反例">案例与反例</a> •
  <a href="#生态位置">生态位置</a> •
  <a href="README.en.md">English</a>
</p>

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

> 面向融资 BP、商业方案和技术演示的可复用 PPT 制作技能：从模糊需求开始，补齐输入、组织证据、选择版式、适配模板并完成可审阅交付。

---

## 项目简介

他山 PPT 制作 Skills 是他山智能体工作流中的演示稿方法层。它把“内容论证”“视觉排版”“模板适配”和“文件导出”分开，使不同项目可以使用自己的内容和模板，同时复用同一套高质量制作方法。

核心思想：

- **交互式输入**：用户可以只给一句话、几段文字、一个旧 PPT 或一张参考图，Skill 先识别已知信息和缺口，再提出少量关键问题。
- **内容与视觉分层**：内容母稿决定讲什么，视觉真源决定怎么排，原始素材决定哪些结论有证据。
- **投资人可读**：正文承担说明责任，痛点或判断先于数字，图表和图片围绕核心结论提供证据。
- **关系准确**：流程、系统架构、数据流和反馈图先定义节点与箭头语义，再选择视觉形式。
- **模板可替换**：通用方法不绑定红灰配色；用户提供模板时，额外加载相应模板适配器。

适用对象：

- 融资 BP 和路演材料；
- 产品和商业方案；
- AI4S、科研和技术平台介绍；
- 高信息密度、需要真实素材和证据边界的演示稿。

---

## 快速开始

### 前置条件

- 支持 Agent Skills 的 Codex、Cursor 或兼容运行环境；
- 一个可用的 PPT 创建 / 编辑 / 渲染工具；
- 内容材料、模板或视觉参考（可以是不完整的）；
- 本仓库本身不附带内部 BP 原件，也不包含具体项目的私有数据。

### 安装到本地 Skills 目录

以 Codex 为例：

```bash
git clone https://github.com/TashanGKD/tashan-ppt-skills.git
mkdir -p ~/.codex/skills
cp -R tashan-ppt-skills/skills/presentation-craft ~/.codex/skills/
cp -R tashan-ppt-skills/skills/artifact-template-bp ~/.codex/skills/
```

如果使用 Cursor 或其他运行时，将两个 skill 目录复制到该运行时的 skills 目录即可。

### 最简单的使用方式

```text
请调用 presentation-craft 帮我制作一份 PPT。
我先提供主题和现有材料，请先判断哪些信息已经足够，哪些信息还缺失；如果版式不明确，先给我 2–3 个聊天框低保真方案，不要直接制作正式 PPT。
```

### 使用器官芯片 BP 模板

```text
请调用 presentation-craft，并加载 artifact-template-bp。
我会提供内容母稿和一份授权使用的模板 PPT。请先区分内容母稿、视觉真源和素材来源，再开始制作。
```

---

## 三个组件的关系

```text
presentation-craft
├── 通用论证、文字、素材、绘图、版式和交互流程
├── 调用 presentations 完成实际 PPT 文件操作
└── 需要专用模板时加载对应模板适配器
        └── artifact-template-bp
```

| 组件 | 负责什么 | 什么时候使用 |
|---|---|---|
| `presentation-craft` | 通用 PPT 方法、交互式输入、论证、案例和反例 | 所有 PPT / BP 任务 |
| `artifact-template-bp` | 器官芯片 BP 的模板适配和模板边界 | 使用授权的器官芯片 / 类器官 BP 模板时 |
| `presentations` | PPT 读取、编辑、渲染和导出 | 运行环境提供的文件工具，不随本仓库复制 |

---

## 输入与交互流程

用户不需要先准备完整项目包。可以从一句模糊需求开始。

```text
粗略请求
  ↓
识别已知输入、缺失输入和版本冲突
  ↓
每轮询问少量阻塞问题
  ↓
版式不明确时给出最多 3 个低保真方案
  ↓
用户选择方向
  ↓
正式制作 PPTX、PDF、PNG 和备注
  ↓
渲染检查与用户审阅
```

制作前通常需要逐步确认：

1. 目标读者和使用场景；
2. 内容母稿或核心文字；
3. PPT 模板及其用途；
4. 页面范围和页面清单；
5. 原始素材、数据和来源；
6. 已有能力、建设中能力和未来规划边界；
7. 交付格式、可编辑性、备注和版本状态。

详细输入说明见 [`preflight-inputs.md`](skills/presentation-craft/references/preflight-inputs.md)。

---

## 案例与反例

案例库覆盖：

- 封面；
- 市场变化；
- 结构性痛点；
- 定义页；
- 流程页；
- 系统架构；
- 干湿闭环；
- 技术能力矩阵；
- 核心壁垒；
- 团队页；
- 路线图；
- 融资页；
- 生态伙伴页；
- 高信息密度页面。

推荐先读：

- [`investor-readable-deck.md`](skills/presentation-craft/references/investor-readable-deck.md)
- [`visual-casebook.md`](skills/presentation-craft/references/visual-casebook.md)
- [`cases.md`](skills/presentation-craft/references/cases.md)

反例重点包括：孤立放大数字、机械三栏、没有语义的箭头、把 AI 放在流程末端、把规划写成现状、用复杂 Logo 网络暗示未经证明的合作关系。

---

## 目录结构

```text
.
├── README.md
├── README.en.md
├── LICENSE
├── CONTRIBUTING.md
├── CHANGELOG.md
├── docs/
│   └── assets/
│       └── tashan.svg
└── skills/
    ├── presentation-craft/
    │   ├── SKILL.md
    │   ├── agents/
    │   ├── references/
    │   └── assets/
    └── artifact-template-bp/
        ├── SKILL.md
        ├── agents/
        ├── references/
        └── assets/
```

---

## 关键文档

| 文档 | 路径 | 用途 |
|---|---|---|
| 通用入口 | `skills/presentation-craft/SKILL.md` | 通用 PPT 制作入口 |
| 输入清单 | `skills/presentation-craft/references/preflight-inputs.md` | 开始制作前识别缺失输入 |
| 投资人可读规则 | `skills/presentation-craft/references/investor-readable-deck.md` | 文案、数字和阅读层级 |
| 版式案例库 | `skills/presentation-craft/references/visual-casebook.md` | 好坏案例和反例 |
| 模板适配器 | `skills/artifact-template-bp/SKILL.md` | 器官芯片 BP 模板适配 |
| 模板门禁 | `skills/artifact-template-bp/references/bp-production-checklist.md` | 版本、素材、渲染和交付检查 |

---

## 生态位置

本仓库属于“人—智能体混合数字世界”项目中的方法与工具层。

```text
他山数字世界
├── 通用 Skill 体系
│   ├── tashan-cursor-skills
│   ├── tashan-research-skills
│   └── tashan-ppt-skills  ← 本仓库
├── 具体应用与工作台
└── 领域项目与行业工作流
```

相关仓库：

| 仓库 | 定位 | 链接 |
|---|---|---|
| `tashan-cursor-skills` | 他山通用 Cursor Skill 体系 | [GitHub](https://github.com/TashanGKD/tashan-cursor-skills) |
| `tashan-research-skills` | 他山科研工作流 Skills | [GitHub](https://github.com/TashanGKD/tashan-research-skills) |
| `tashan-ppt-skills` | PPT / BP 制作 Skills | 当前仓库 |

---

## 环境变量

本仓库不要求环境变量，也不保存 API Key、GitHub Token 或项目数据。

实际 PPT 制作所需的工具、字体和运行环境由使用者所在平台提供。

---

## 贡献

欢迎贡献通用的 PPT 论证、版式、素材组织和案例改进。请先阅读 [`CONTRIBUTING.md`](CONTRIBUTING.md)。

---

## 更新日志

版本变更见 [`CHANGELOG.md`](CHANGELOG.md)。

---

## 许可证

MIT License. See [`LICENSE`](LICENSE) for details.
