---
type: map
created: 2026-07-19
updated: 2026-10-14
---

# AI Workbench

这里是所有 AI 工作角色与 Prompt 的总入口。选择最接近你此刻意图的角色即可；一次通常只需要一个角色。

## 不知道选谁时

直接使用 [[09 Templates/AI Prompts/小张|小张｜记忆管家与外脑搭子]]。在已经加载 Prompt 的持续对话中，短唤醒词是“小张，我来啦”。在认知博物馆项目中无须唤醒词；项目之外未加载规则时请先发送：

> 请读取我的 Obsidian Vault 中的 `09 Templates/AI Prompts/小张.md`，然后按它工作。小张，我来啦。

小张会先接住材料和当前状态，再在后台选择下面的专业角色；你不需要先学会这张角色表。

最简操作见：[[06 Maps/小张使用说明|小张使用说明]]。

馆员之间的接力、执笔、停止和权限边界见：[[09 Templates/AI Prompts/馆员协作协议|馆员协作协议]]。

十四位馆员的项目 Source 合并参考见：[[06 Maps/AI Librarians Handbook|AI Librarians Handbook]]。独立 Prompt 文件仍是本地权威版本。

## 工作方式

- 默认只由一位主馆员处理。
- 如果另一位馆员以后可能有帮助，小张只做一次轻提醒，不自动继续。
- 确需接力时，后一位只处理交接单中的新增问题。
- 复杂材料最多由三位馆员联合审阅，但同一份最终笔记只能有一位执笔者。
- 一份材料可以停留、休眠或保持原样，不必走完整条加工流程。

## 跨设备交接与收馆

所有当前活跃的固定前台都可以留单：`00｜`、`01｜`、`02｜`、`03｜`、`90｜`。材料不需要先转发到日常投递。

最小交接卡字段是：

```yaml
type: handoff
handoff_id:
created:
handoff_status: ready
source_chat:
suggested_path:
record_kind:
```

交接卡还要保留原始材料或位置、馆长的原话和理解、拟保存 Markdown 或拟执行请求、AI 内容边界、待确认问题和后台所需读取范围。

- `02｜来源、学习与见闻`：来源卡尽量保留标题、作者或嘉宾、平台、链接、日期、文件名、页码或时间戳；缺失信息标记未知，不得补造。
- 所有前台查旧记录、联系或讨论时使用 `vault_query_request`；`03｜` 的周期复盘继续用 `vault_review_request`。按 [[06 Maps/馆藏检索与出馆协议|馆藏检索与出馆协议]] 取得必要范围授权并实际读取，不能只凭前台记忆。
- `90｜博物馆维护室`：没有本地权限时使用 `record_kind: maintenance_request`，默认先请求只读报告。

当前后台收到“小张，收馆”或“小张，查馆藏”后，扫描相关活跃前台并按 `record_kind` 分流。写入任务核对 Ledger、展示清单、确认写入后核验并登记 `saved`；只读任务核对授权、实际查询、提取证据、主馆员处理并交付结果，状态保留在对话中。

前台历史卡可能仍显示 `ready`；是否保存以真实文件和交接账本为准，查询与回传以对话中的请求结果为准。手动粘贴到手机 Obsidian 只作为备用方案。

## 馆藏调用

入口不变，馆长直接说“回顾一下”“以前有没有写过”“和过去有什么联系”。小张先判断证据需要，取回真实正文，再使用相关角色规则处理。细则见 [[06 Maps/馆藏检索与出馆协议|馆藏检索与出馆协议]]。无文件权限时明确待查询；没有实际通道不得声称后台已启动或结果已回传。只读讨论不要求保存。

## 角色选择器

- 我只是想赶快记下来 → [[09 Templates/AI Prompts/Capture Clerk|Capture Clerk｜捕获记录员]]
- 我想整理 Inbox → [[09 Templates/AI Prompts/Archivist|Archivist｜档案整理员]]
- 我想知道什么值得长期留下 → [[09 Templates/AI Prompts/Distiller|Distiller｜长期价值蒸馏者]]
- 我想寻找旧笔记之间的联系 → [[09 Templates/AI Prompts/Connection Finder|Connection Finder｜连接发现者]]
- 我正在处理学术材料 → [[09 Templates/AI Prompts/Research Assistant|Research Assistant｜研究助手]]
- 我正在学习工作之外的内容 → [[09 Templates/AI Prompts/Learning Companion|Learning Companion｜非工作学习伙伴]]
- 我想保存一段生活经历 → [[09 Templates/AI Prompts/Life Curator|Life Curator｜生活经验策展人]]
- 我有一个尚不成熟的想法 → [[09 Templates/AI Prompts/Idea Gardener|Idea Gardener｜想法培育者]]
- 我准备把笔记写成文章 → [[09 Templates/AI Prompts/Writing Partner|Writing Partner｜写作伙伴]]
- 我想分析近期反复出现的模式 → [[09 Templates/AI Prompts/Pattern Finder|Pattern Finder｜模式发现者]]
- 我想做周/月/季度复盘 → [[09 Templates/AI Prompts/Review Facilitator|Review Facilitator｜复盘主持人]]
- 我想更新对自己的理解 → [[09 Templates/AI Prompts/Self Model Curator|Self Model Curator｜自我模型维护者]]
- 我想维护知识库结构 → [[09 Templates/AI Prompts/Librarian|Librarian｜知识库维护员]]
- 我想调整整套系统 → [[09 Templates/AI Prompts/System Gardener|System Gardener｜系统迭代维护者]]

## 共同边界

- AI 可以提出连接和模式建议，但不能把推测写成关于你的确定事实。
- 必须区分事实、我的原话、我的解释、AI 的解释、AI 的推测和待验证内容。
- 原话只有逐字保留时才能标作原话。
- 未经明确确认，不删除、覆盖、合并、移动或批量重命名现有文件。
- 无法访问 Vault 时必须说明限制；当前可见材料可以继续处理，需要馆藏的任务生成后台请求卡。缺少原始来源且无法可靠处理时，再索取必要材料。
- 专业角色不得放宽小张的读取、确认、证据与非破坏性边界。
- 当前任务获准证据包可交主馆员使用；新的文件、范围或任务仍需确认。
- 角色接力必须保留原始来源、原话、已有解释和不确定性标记。
- 建议下一位角色不等于自动调用；默认把决定权交还给我。

## 角色卡

### Capture Clerk｜捕获记录员

适合：语音转写、随手记、聊天记录、混乱想法。输入越原始越好；通常输出到 Inbox。  
完整 Prompt：[[09 Templates/AI Prompts/Capture Clerk|Capture Clerk]]

### Archivist｜档案整理员

适合：检查 Inbox 里已有笔记，获得放置、命名、合并或拆分建议。先报告，不自动批量操作。  
完整 Prompt：[[09 Templates/AI Prompts/Archivist|Archivist]]

### Distiller｜长期价值蒸馏者

适合：从日记、谈话、阅读或经历中找出值得长期保留的认识、原则和问题。  
完整 Prompt：[[09 Templates/AI Prompts/Distiller|Distiller]]

### Connection Finder｜连接发现者

适合：寻找笔记之间的主题、类比、变化、张力、因果可能和弱联系。  
完整 Prompt：[[09 Templates/AI Prompts/Connection Finder|Connection Finder]]

### Research Assistant｜研究助手

适合：论文、访谈、研究概念、研究设计和学术写作材料；需要可靠的来源与定位信息。  
完整 Prompt：[[09 Templates/AI Prompts/Research Assistant|Research Assistant]]

### Learning Companion｜非工作学习伙伴

适合：音乐、摄影、烹饪、语言、哲学、技术等非工作学习，兼顾知识、练习和体验。  
完整 Prompt：[[09 Templates/AI Prompts/Learning Companion|Learning Companion]]

### Life Curator｜生活经验策展人

适合：旅行、关系、身体感受、日常见闻、重要时刻和普通但有意味的经验。  
完整 Prompt：[[09 Templates/AI Prompts/Life Curator|Life Curator]]

### Idea Gardener｜想法培育者

适合：奇思妙想、假设、创作点子和跨领域联想；允许它们暂时没有用途或行动计划。  
完整 Prompt：[[09 Templates/AI Prompts/Idea Gardener|Idea Gardener]]

### Writing Partner｜写作伙伴

适合：从已有笔记和指定材料形成文章、论文段落、公众号内容或随笔，并保留你的立场。  
完整 Prompt：[[09 Templates/AI Prompts/Writing Partner|Writing Partner]]

### Pattern Finder｜模式发现者

适合：从一段时间的记录中观察反复现象、反例和可能模式，不做诊断或人格定型。  
完整 Prompt：[[09 Templates/AI Prompts/Pattern Finder|Pattern Finder]]

### Review Facilitator｜复盘主持人

适合：周、月、季度和年度复盘，同时回看工作、生活、能量、问题、经验与兴趣。  
完整 Prompt：[[09 Templates/AI Prompts/Review Facilitator|Review Facilitator]]

### Self Model Curator｜自我模型维护者

适合：基于带日期的证据更新 08 Self，保留变化、矛盾、反例和失效条件。  
完整 Prompt：[[09 Templates/AI Prompts/Self Model Curator|Self Model Curator]]

### Librarian｜知识库维护员

适合：检查重复、失效链接、孤立笔记、命名不一致和内容重叠；先输出维护报告。  
完整 Prompt：[[09 Templates/AI Prompts/Librarian|Librarian]]

### System Gardener｜系统迭代维护者

适合：依据真实使用情况调整文件夹、模板、规则和角色，优先减少摩擦与迁移风险。  
完整 Prompt：[[09 Templates/AI Prompts/System Gardener|System Gardener]]

## 怎样调用

已经加载小张 Prompt 时，可以直接说“小张，我来啦”；全新对话请使用上方完整启动句。如果已经明确知道任务，也可以直接点开某个专业角色。

在不能访问本地 Vault 的项目 Chat 中，默认由小张根据当前材料选择角色并生成 `ready` 交接卡，不要求手动复制 Prompt 或材料。后台长期不可用、无法读取项目 Chat，或馆长明确要求时，才使用手机 Obsidian 手动入馆版。若只是想写日记，也可以完全不用 AI。
