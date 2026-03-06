# GoodJob.Guide 职场信息 Skills

## 项目简介

本项目是一个基于 [GoodJob.Guide](https://goodjob.guide/) 社区数据的 AI Agent 知识库。包含 **5,442 篇**职场相关帖子及 **62,447 条**评论，涵盖公司评价、求职经验、职场讨论等内容。

通过本 Skills 知识库，AI Agent 能够帮助求职者：

- 🔍 **查询公司信息** — 了解目标公司的真实工作环境、加班情况、薪资待遇
- ⚠️ **识别公司黑料** — 拖欠工资、职场PUA、恶意辞退等风险提示
- 💡 **获取求职建议** — 面试经验、简历技巧、薪资谈判等实用信息
- 📊 **了解行业现状** — 各行业薪资水平、岗位需求、发展趋势

## 安装使用

### 1. 安装 Skill

```bash
npx skills add GoodJobGuide/skills

# 更新
npx skills update GoodJobGuide/skills

# 删除
npx skills remove GoodJobGuide/skills

# 查看
npx skills list
```

### 2. 开始使用

安装完成后，直接提问即可：

```
> 众阳健康这个公司怎么样？
> 济南有哪些公司拖欠工资？
> 给我一些 Java 面试的建议
```

Agent 会自动检索 `skills/references/` 中的相关帖子，结合评论区信息给出综合回答。

## 数据概览

| 指标             | 数量               |
| ---------------- | ------------------ |
| 帖子总数         | 5,442              |
| 评论总数         | 62,447             |
| 有公司名称的帖子 | 3,725              |
| 求职讨论帖       | 1,717              |
| 数据来源         | GoodJob.Guide 社区 |

## 目录结构

```
.
├── AGENTS.md                  # AI Agent 配置文件
├── README.md                  # 项目说明文档（本文件）
├── goodjob.guide.csv          # 原始数据文件
└── skills/
    ├── SKILL.md               # Skill 总览与索引（含热门 TOP100、完整帖子索引）
    └── references/            # 帖子详情（5,442 个 .md 文件，以 post_id 命名）
        ├── 01963dd2-9645-73f0-881c-01c27e403484.md
        ├── 01963dda-81f1-7389-bc67-f7ef16f1bf3d.md
        └── ...
```

## Skill 文件元数据

每个 reference 文件包含丰富的 YAML frontmatter 元数据，确保 Agent 检索精准有效：

| 字段            | 说明                                        |
| --------------- | ------------------------------------------- |
| `name`          | 帖子标题/公司名称                           |
| `company`       | 公司名称（如有）                            |
| `address`       | 公司地址（如有）                            |
| `business`      | 主营业务（如有）                            |
| `category`      | 分类：公司评价/求职经验/面试经验等          |
| `risks`         | 风险标签列表（拖欠工资/无偿加班/职场PUA等） |
| `keywords`      | 内容关键词                                  |
| `pv`            | 浏览量                                      |
| `comment_count` | 评论数                                      |

## 使用方式

### 作为 AI Agent 知识库

将本目录配置为 AI Agent 的 Skills 目录，Agent 通过 `skills/SKILL.md` 理解知识库结构，根据用户查询检索 `skills/references/` 中的对应文件。

### 直接浏览

所有文件均为标准 Markdown 格式，可用任何编辑器或 Markdown 阅读器打开。

## 免责声明

> ⚠️ 本知识库中的所有内容均来自 [GoodJob.Guide 社区](https://goodjob.guide/) 用户的公开分享，仅代表发布者个人观点和经历，不代表任何官方立场。信息仅供参考，请求职者结合自身情况综合判断。
