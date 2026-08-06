# 高质量数据集建设指引 — 知识库与 Skill

本仓库收录《高质量数据集建设指引》的原文、结构化知识库及对应的 agent skill。

## 文档信息

- **书名**：《高质量数据集建设指引》
- **编制**：国家数据局指导，中国信息通信研究院、国家数据发展研究院、中国电子技术标准化研究院、国家信息中心、国家发展和改革委员会创新驱动发展中心、中国电子信息产业发展研究院联合编制
- **版本**：2025 年发布（55 页）
- **原文**：[source/高质量数据集建设指引.pdf](source/高质量数据集建设指引.pdf)

## 内容结构

全书共 6 大部分：

| 章 | 主题 | 关键框架 |
|----|------|----------|
| ch01 | 建设背景 | 数据飞轮、四要素、三分类维度 |
| ch02 | 应用需求 | 三层应用需求框架（基础认知/场景理解/行动规划） |
| ch03 | 建设现状 | 全球双线格局、五大挑战 |
| ch04 | 建设方法与实践 | 场景/数据驱动模式、六环节闭环、五大核心技术、三维质量评价 |
| ch05 | 建设运营体系 | 体系规划、工程建设、运营四目标 |
| ch06 | 推进思路 | 体系化布局、设施化推进、生态化赋能 |

## 作为 Agent Skill 使用

本仓库根目录即是一个可直接安装的 skill（`book-to-skill` 格式）：

- `SKILL.md` — 主技能文件（核心框架 + 章节/主题索引）
- `chapters/` — 6 章深度摘要
- `glossary.md` — 术语表
- `patterns.md` — 建设模式与方法（When/How/Trade-offs）
- `cheatsheet.md` — 决策速查表 + 十大反模式

### 安装方法

将本仓库 clone（或复制）到 agent 的技能目录，例如：

```bash
# GitHub Copilot CLI / Amp / Claude Code 等兼容位置
git clone https://github.com/MickeyWalker/High-Quality-Dataset-Construction.git ~/.agents/skills/high-quality-datasets
```

或复制已有安装：

```bash
cp -r ~/.agents/skills/high-quality-datasets/. <目标技能目录>/
```

### 使用示例

- 无参数调用 → 加载核心框架
- `high-quality-datasets` + 主题（如「价值对齐」「场景驱动模式」）→ 定位并读取相关章节
- `high-quality-datasets ch04` → 加载第四章（建设方法）
- 「what chapters do you have?」→ 查看章节索引

## 生成说明

本知识库由 [book-to-skill](https://github.com/virgiliojr94/book-to-skill) 流程从原文 PDF 生成：

1. 提取全文（中文 PDF 需用 pypdf，`pdftotext` 对中文编码不兼容会丢字）
2. 分析章节结构与核心框架
3. 生成 SKILL.md + 章节摘要 + 术语表 + 模式库 + 速查表
4. 通过生成技能安全扫描

> **注意**：提取方式为文本层提取，原 PDF 中插图（第 1/2/4 页等）不包含文本，具体图表数据以原文 PDF 为准。
