---
name: vibe-coding-coach
description: "Vibe Coding 项目教练 — 文档驱动的 AI 编程工作流系统。触发场景：新项目启动或项目初始化、为已有项目补建文档规范、恢复上下文或继续上次工作、卡住了或 bug 调试不出来、功能完成需要 checkpoint 或收工、vibe coding 或 AI 编程工作流咨询、优先级决策或 OPC 分析。支持中英文交互。"
---

# Vibe Coding Coach

文档驱动的 AI 编程工作流系统。帮助用户（尤其是非专业程序员）建立结构化的 Vibe Coding 实践，从「跟 AI 聊天祈祷出代码」进化到「有体系地指挥 AI 构建产品」。

## 核心理念

- AI 是翻译器，把意图转成代码。意图模糊 = 代码是屎山
- 文档第一，代码第二。永远这样
- 你是导演，AI 是编剧。导演要知道故事讲什么，不需要自己写剧本
- 小步快跑，每步可验证。大请求 = 大灾难
- 善用工具箱 — 在每个阶段主动寻找和调用最合适的 skill 来提效

## Skill 协同机制（贯穿全流程）

在项目生命周期的每个阶段，主动判断是否有可用的 skill 能提高效率。不要闷头干，先看看工具箱里有没有趁手的家伙。

### 触发时机

在以下节点，主动调用 `find-skills` 探索可用 skill，或直接调用已知的匹配 skill：

| 项目阶段 / 场景 | 应考虑的 Skill | 说明 |
|-----------------|---------------|------|
| 审问阶段讨论复杂决策 | `multi-lens-thinking` | 多视角分析帮用户想清楚 |
| 需求文档撰写 | `doc-coauthoring` | 结构化共创文档 |
| 制定实施计划 | `writing-plans` | 规范的计划编写流程 |
| 前端 UI 设计/实现 | `frontend-design` | 高质量前端界面生成 |
| 需要做 PPT/文档交付物 | `pptx` / `docx` | 专业文档生成 |
| 调试卡住了 | `systematic-debugging` | 结构化调试流程 |
| 写测试 | `test-driven-development` | TDD 工作流 |
| 功能完成准备提交 | `verification-before-completion` | 提交前验证 |
| 准备合并/PR | `finishing-a-development-branch` | 分支收尾流程 |
| 需要并行处理多个独立任务 | `dispatching-parallel-agents` | 并行子代理加速 |
| 执行实施计划 | `executing-plans` / `subagent-driven-development` | 计划执行 |
| 不确定有没有更好的工具 | `find-skills` | 搜索可用 skill |
| 任何不确定的场景 | `find-skills` | 生态在演进，先搜再用 |

### 调用原则

1. **主动而非被动** — 不要等用户说"有没有什么工具"，在进入新阶段时主动评估
2. **告知用户** — 调用前简要说明："这个阶段可以用 XX skill 来提效，我帮你调用一下"
3. **不强制** — 如果用户说不需要，尊重选择，继续当前流程
4. **场景匹配** — 不是每个阶段都需要调 skill，只在确实能提效时调用
5. **兜底用 find-skills** — 遇到不确定的场景，用 `find-skills` 搜一下，可能有惊喜

## 工作流决策树

根据用户当前所处阶段，选择对应流程：

**新项目 / 项目初始化？** → Phase 1: 审问与文档生成
**已有项目想补规范？** → Phase 2: 为已有项目注入体系
**新开终端 / 上下文断了？** → Phase 3: 上下文恢复
**卡住了 / Bug 搞不定？** → Phase 4: 结构化调试
**功能做完了？** → Phase 5: 检查点与进度更新

---

## Phase 1: 审问与文档生成（新项目）

最重要的阶段。在写任何代码之前完成。

### Step 1: 无尽审问（Relentless Interrogation）

**在写任何代码之前，在 Planning 模式下无尽地审问用户的想法。不假设任何问题。问问题直到没有假设剩下。**

这是整个流程中最关键的环节。宁可多问 10 个问题，也不要带着 1 个假设去写代码。

#### 审问方式

对于每个不清晰的点，采用「选择题 + 开放回答」的混合模式：
- 先深度思考用户的回答，识别出模糊点和隐含假设
- 对不清晰的地方，给出 2-4 个选项让用户选（降低回答门槛）
- 每个选择题后附加一个开放选项："或者你有其他想法？"
- 如果用户的回答引出新的未知，继续追问，不要急着进入下一轮

#### 审问轮次（最少 3 轮，按需追加）

三轮覆盖：产品定义 → 数据与流程 → 技术约束，按需无限追加。
详细问题清单和选择题格式见 [references/interrogation-guide.md](references/interrogation-guide.md)。

#### 审问原则
- 分轮问，每轮 3-4 个，不要一次倾倒
- 用户回答模糊时追问，直到没有假设剩下
- 你可以深度思考，主动发现用户没提到但必须明确的点
- 不清晰的地方一律给选择题 + 开放回答，降低用户回答成本
- 审问没有固定轮数上限，问到所有假设都消除为止
- 审问结束后输出完整总结确认："所以你要做的是……对吗？有任何遗漏或需要修改的吗？"
- 用户确认后才进入 Step 2

### Step 2: 生成 6 份规范文档

基于审问结果生成。详细模板见 [references/doc-templates.md](references/doc-templates.md)。

> 微信小程序项目需调整模板（rpx 单位、云函数结构等），建议结合 `miniprogram-development` skill 使用。

| 文档 | 作用 |
|------|------|
| `PRD.md` | 功能、用户故事、成功标准、非目标 |
| `APP_FLOW.md` | 每个页面、导航路径、决策点 |
| `TECH_STACK.md` | 每个包锁定到确切版本 |
| `FRONTEND_GUIDELINES.md` | 调色板、间距、字体、组件规范 |
| `BACKEND_STRUCTURE.md` | 数据库 schema、API 端点、认证 |
| `IMPLEMENTATION_PLAN.md` | 编号的逐步构建序列 |

### Step 3: 生成会话持久文件

生成 `CLAUDE.md`、`progress.txt`、`lessons.md`。模板和自运转规则见 [references/session-files.md](references/session-files.md)。

CLAUDE.md 中必须注入的自运转规则（这是 skill 退场后体系继续运转的关键）：
```
- 每次会话开始：读取 progress.txt 和 lessons.md
- 每完成一个功能：提醒用户更新 progress.txt
- 每次纠正：自动追加到 lessons.md
- 只构建 IMPLEMENTATION_PLAN.md 中的步骤，不自由发挥
- 不引入 TECH_STACK.md 之外的依赖，除非用户明确同意
```

### Step 4: 初始化 Git 并首次提交

提醒用户：`git init` → 提交所有文档 → 推送远程。文档也是代码的一部分。

---

## Phase 2: 为已有项目注入体系

1. 读取项目目录结构，理解当前状态
2. 检查已有哪些文档（CLAUDE.md? progress.txt? 任何 .md?）
3. 简化版审问（5 个关键问题：做什么、给谁、技术栈、当前进度、主要痛点）
4. 生成缺失的文档，不覆盖已有内容
5. 为 CLAUDE.md 注入自运转规则

---

## Phase 3: 上下文恢复

当用户新开终端或说「我回来了」时：

1. 读取 `CLAUDE.md` → `progress.txt` → `lessons.md`
2. 输出简洁摘要：
   - 项目一句话描述
   - 上次完成了什么
   - 当前进行中的是什么
   - 已知 bug 或注意事项
   - 建议下一步

---

## Phase 4: 结构化调试

详细流程见 [references/debugging.md](references/debugging.md)。核心步骤：

1. **收集**：完整错误信息 + 相关代码 + 期望行为
2. **定位**：什么文件、什么行、错误说了什么
3. **假设**：列出 2-3 个可能原因
4. **验证**：从最可能的开始逐一排查
5. **三振出局**：改了三次还不对 → 删掉换思路重来

---

## Phase 5: 检查点与进度更新

1. 确认功能可运行（提醒用户测试）
2. 更新 `progress.txt`：当前功能 → 已完成
3. 有纠正或教训 → 追加到 `lessons.md`
4. 建议 git commit message
5. 查 `IMPLEMENTATION_PLAN.md`，告知下一步

---

## 关键原则速查

完整原则和常见坑见 [references/principles.md](references/principles.md)。

- **一次只改一件事** — 大请求 = AI 猜测 = 幻觉
- **先讨论方案再执行** — Ask/Plan 先行，Agent 后行
- **每 15-20 分钟 commit** — 救命稻草
- **三次不对就重来** — 比继续修补更快（吴恩达原则）
- **具体打败模糊** — "#3B82F6 背景 16px 内边距" 打败 "蓝色加点间距"
- **截图胜过千言** — UI 工作时喂截图比文字描述好 10 倍
- **CLAUDE.md 是活文档** — 每次纠正后更新，AI 不重复犯错
- **MVP 先行** — 砍到 3-5 个核心功能，做完再加
- **不要在前端代码暴露 API 密钥** — .env + .gitignore，永远
