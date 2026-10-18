# doc-legacy-extract · 老版 Word .doc 正文提取方法包

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Agent Skill](https://img.shields.io/badge/Agent%20Skill-SKILL.md-blue.svg)](SKILL.md)
[![Category](https://img.shields.io/badge/category-document--processing-8a2be2.svg)](#)
[![Version](https://img.shields.io/badge/version-1.0.0-informational.svg)](#)
[![Multilingual](https://img.shields.io/badge/i18n-8%20languages-brightgreen.svg)](#)
[![llms.txt](https://img.shields.io/badge/AI--friendly-llms.txt-101E2C.svg)](llms.txt)
[![English](https://img.shields.io/badge/English-README.en.md-blue.svg)](README.en.md)

> 提取老版 Word .doc（OLE 复合文档）正文文本的可靠方法——仅依赖 olefile，零第三方重型库，可读 NMPA 等官网发布的法规附件 .doc，并按中文「第 X 条」结构切分。
> A reliable method to extract body text from legacy Word .doc (OLE compound) files using olefile with zero heavy third-party dependencies; parse official regulation attachments and split Chinese articles by clause.

SynomosAI 四支柱体系：**身份（Identity）· 溯源（Traceability）· 治理（Governance）· 共生（Symbiosis）**——当 AI 进入商业，可信是唯一的硬通货。

**关键词 / Keywords**：.doc 提取 · OLE 复合文档 · olefile · 老版 Word · 法规附件解析 · 第 X 条切分 · document processing · legacy word · text extraction

本仓库是一个 **Agent Skill 发布包**：核心文件 `SKILL.md` 遵循 Agent Skills 规范（YAML frontmatter），把「把老版 .doc（非 .docx）正文可靠抽出并按中文条款结构化」的方法固化为可被 AI Agent 直接加载的技能。可直接放入主流 AI Agent（如 WorkBuddy）的技能目录使用。

- **分类 / Category**：document-processing
- **版本 / Version**：1.0.0
- **署名 / Author**：诺声(Logos)@SynomosAI
- **许可 / License**：MIT（详见仓库 [LICENSE](LICENSE)）

---

## ✨ 特性 / Features

- 零重型依赖：核心只用 olefile 读 OLE 复合文档流，不依赖 markitdown / pandoc / LibreOffice
- 专攻老格式：.doc（OLE）而非 .docx——markitdown / pdf 类工具普遍打不开的那类文件
- 法规场景：面向 NMPA / 政府官网以 .doc 发布的法规附件（如 GMP 2025 版公告附件）
- 条款切分：可进一步按中文「第 X 条」结构把正文切成可引用的条目
- 真实参照法：每步结论挂到 OLE 流结构与可复现实测，不靠猜
- 多语种：中 / 英 / 日 / 韩 / 西 / 法 / 德 / 阿（核心 8 种）

---

## 🚀 快速开始 / Quick Start

前置：一个能加载 Agent Skill 的 AI 编码助手 / 技能运行时；无独立可执行服务；依赖为 Python 库 olefile。

```bash
# 1. 克隆本仓库
git clone https://github.com/zhaoxinghua09-cell/doc-legacy-extract.git
cd doc-legacy-extract

# 2. 安装核心依赖（olefile 是唯一第三方依赖）
pip install olefile

# 3. 查看技能主文件（触发词、方法、边界、条款切分口径）
cat SKILL.md
```

跑通后，直接用自然语言发起调用，例如：

```text
「帮我把这个 .doc 附件的正文抽出来」
「NMPA 这个法规附件是老 .doc，现有工具打不开」
「把抽出来的正文按第 X 条切成条目」
```

---

## 📖 使用方式 / Usage

1. 克隆本仓库，或将技能目录放入 Agent 技能目录（如 `~/.workbuddy/skills/`）；
2. 按 `SKILL.md` 的描述与触发词调用对应能力；
3. 详细方法、边界与治理溯源见 `SKILL.md` 正文。

> 本包为文档 + 方法论；按 SKILL.md 中给出的 olefile 读取流程对目标 .doc 执行即可。

---

## 📁 仓库结构 / Repository layout

```text
doc-legacy-extract/
├── README.md            # 本文件（双语）
├── README.en.md         # 英文版说明
├── SKILL.md             # 技能主文件（Agent Skills 规范 · YAML frontmatter）
├── manifest.json        # 技能元数据（名称 / 版本 / 许可 / 描述）
├── LICENSE              # MIT 许可全文
├── SECURITY.md          # 安全策略
├── CONTRIBUTING.md      # 贡献指南
├── AGENTS.md            # 给 AI Agent 的工作指引
├── llms.txt             # 给 AI 的最小索引（llms.txt 标准）
└── llms-full.txt        # 给 AI 的完整文本
```

---

## 许可说明 · License Notice

- **权利状态**：本仓库以 **MIT 许可** 许可发布，可依该许可证条款自由使用、修改与再分发。
- **引用建议**：引用时请标注仓库名与原文链接 `https://github.com/zhaoxinghua09-cell/doc-legacy-extract`
  与权利人「赵兴华 / Steven Zhao·China」。
- **品牌状态限定**：MedXpert、SynomosAI、LGD 等为相关项目标识，
  **均未申请实体注册、未申请商标注册**；出现仅作来源标识，
  不构成对法人实体或商标权的任何主张。
- **完整条款**：见仓库根目录 [LICENSE](LICENSE)。
- **联系**：zhaoxinghua06@126.com ｜ ORCID 0009-0001-0512-1237

---

## 🔒 安全 / Security

如发现安全问题，请按 [`SECURITY.md`](SECURITY.md) 的方式私下报告，不要在公开 issue 中披露。

## 🤝 贡献 / Contributing

欢迎按 [`CONTRIBUTING.md`](CONTRIBUTING.md) 提交改进。本仓库为技能发布包，改动请保持 `SKILL.md` 的 YAML frontmatter 字段兼容（`name` / `slug` / `version` / `license` 等）。

## 免责声明

本仓库内容为**理论站位与工具化探索**，不代表任何已获认证、已商业化交付或已服务特定客户的声明；文中涉及的外部标准、认证与条款信息为公开资料转述，正式引用前请**独立核实**。API、授权码与形象大使等为路线图（roadmap）事项，尚未上线。
