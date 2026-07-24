# sun-felt-wechat-illustrator

<p align="center">
  <strong>把一篇中文公众号文章，做成一套真正帮助阅读的 3D 毛毡视觉。</strong>
</p>

<p align="center">
  <img src="./readme/hero-v1.png" width="100%" alt="真实 3D 毛毡画面中，一双手把一张文章卡放入工作台，右侧形成头条封面、分享封面和正文配图三种成品板；标题为「一篇文章，一套视觉」。">
</p>

<p align="center">
  <a href="./LICENSE"><img src="https://img.shields.io/badge/License-MIT-17233d.svg" alt="MIT License"></a>
  <img src="https://img.shields.io/badge/Codex-Skill-d8672e.svg" alt="Codex Skill">
  <img src="https://img.shields.io/badge/Language-中文-73809a.svg" alt="中文">
</p>
`sun-felt-wechat-illustrator` 是面向 Codex 的中文内容视觉 Skill。它不是为文章补几张装饰图，而是先理解读者任务，再把文章组织成统一的头条封面、分享封面与正文配图系统。

## 从文章，到一套可读的视觉

| 你提供 | Skill 交付 |
| --- | --- |
| 一篇中文文章、Markdown 或正文 | 约 `2.35:1` 的头条长封面 + `1:1` 分享页封面 |
| 文章的主题、读者与约束 | 依据真实理解节点推荐的正文配图 |
| 一次明确的创作请求 | 每张图的精确插入位置、计划、提示词与质检记录 |

正文图默认使用 **16:9**。如需 **4:3** 或 **3:4**，请在请求中明确指定。

## 真实案例

每个案例都从一篇文章延展为“分享封面 + 头条长封面 + 正文配图”的统一系列，而不是单张插画。

<table>
  <tr>
    <td width="33.33%"><img src="examples/chat-dead.webp" alt="聊天已死：公众号视觉案例"></td>
    <td width="33.33%"><img src="examples/ai-agent.webp" alt="AI Agent：公众号视觉案例"></td>
    <td width="33.33%"><img src="examples/first-principles.webp" alt="第一性原理：公众号视觉案例"></td>
  </tr>
  <tr>
    <td align="center"><strong>聊天已死</strong><br>8 张视觉</td>
    <td align="center"><strong>AI Agent</strong><br>5 张视觉</td>
    <td align="center"><strong>第一性原理</strong><br>5 张视觉</td>
  </tr>
</table>

## 它为什么不同

- **一图一事**：每张正文图只解决一个读者任务——理解流程、区分概念、看见因果或记住行动。
- **图文同生**：标题、标签与画面在同一次生成中完成；文字是毛毡切字或刺绣的一部分，不用本地排字覆盖。
- **真实材质**：以短羊毛纤维、厚毡裁片、切边和锁边针脚作为交付标准，拒绝皮革、橡胶与平面伪文字。
- **可直接发布**：统一系列色板与文字层级，并交付每张正文图应放在原文哪一句之后。

对灾难、创伤、法律判决等严肃题材，Skill 会切换为克制模式；必要时停止生成，避免把真实处境玩具化。

## 快速开始

将此仓库克隆到 Codex 的技能目录（通常是 `~/.codex/skills`）：

```bash
git clone https://github.com/sunyifeng11111/sun-felt-wechat-illustrator.git \
  ~/.codex/skills/sun-felt-wechat-illustrator
```

随后在 Codex 中附上文章并提出任务：

```text
使用 sun-felt-wechat-illustrator，为下面这篇文章生成一套公众号视觉：

- 头条长封面和方形分享封面都保留标题
- 推荐正文配图数量，并生成对应图片
- 正文图默认使用 16:9
- 给出每张图应插入在哪个原句之后

文章：
（粘贴 Markdown 或正文）
```

也可以收窄范围：

```text
只生成 3 张 4:3 正文配图；不要封面。每张图保留少量毛毡文字锚点。
```

## 工作方式

```text
读文章与约束  →  找到读者任务  →  统一系列工艺  →  逐张生成与质检  →  给出插入指南
```

生成时会判断标题来源、文章类型、核心命题、情绪与题材风险；再建立可追溯计划，并在原图与缩略图中检查毛毡材质、文字、标签和可读性。未达标版本只保留在草稿中。

## 输出内容

```text
felt-illustrations/<article-slug>/
├── 00-cover-wide.png       # 公众号头条长封面
├── 00-cover-square.png     # 分享页方形封面
├── 01-<slug>.png           # 正文配图
├── placement-guide.md      # 每张正文图的精确插入位置
├── plan.md                 # 内容路由与视觉计划
├── prompts/                # 每个候选的提示词
└── qa/text-verification.md # 文字与材质质检记录
```

## 使用前提

- 可调用内置图像生成能力的 Codex 环境
- 一篇中文文章、Markdown 或正文；文章越完整，选点和插入建议越准确
- 对封面范围、文字、正文图数量或画幅有偏好时，可在请求中直接说明

详细的内容路由、毛毡材质标准、提示词模板与质检清单在 [SKILL.md](./SKILL.md) 和 `references/` 中维护。

## 关于作者

全网同名：**孙同学玩AI**

| 平台 | 账号 |
| --- | --- |
| 抖音 | 孙同学玩AI |
| 小红书 | 孙同学玩AI |
| 视频号 | 孙同学玩AI |
| X | 孙同学玩AI |
| 公众号 | 孙同学玩AI |

## 许可证

本项目采用 [MIT License](./LICENSE)。
