# MVPify — Claude Code Skill

> Your battle-tested PM partner that stops you from building too much, too fast.
>
> 你的资深 PM 搭档，在第一行代码之前，帮你把需求砍到刚刚好。

---

## The Problem / 痛点

This skill was born from burning **over 100 million tokens** learning this lesson the hard way.

With vCoding, you always want to build something ambitious in one shot. You sketch out a "complete solution"
with Claude — multiple services, complex workflows, a full feature set. It *feels* like the right move.
But then: you're drowning in a massive feature system. Tokens melt away. The architecture keeps evolving.
Dependencies pile up. **And the core loop still isn't running.**

You've spent enormous token budget on something that never ships.

---

这个 skill 来自烧掉**上亿 token** 的真实教训。

用 vCoding 时，你总想一次做个大的。和 Claude 一起勾勒出"完整方案"——多个服务、复杂流程、全套功能。感觉很对。
但接下来：你迷失在巨大的功能体系里。Token 大量消耗。架构不断演进。依赖越堆越多。
**而核心闭环还是没跑起来。**

你花掉了巨量 token 预算，系统却没上线。

---

## What It Does / 它做什么

MVPify intercepts your request and forces a structured breakdown across 4 phases:

1. **Prune** — separates core features from nice-to-haves, asks permission to defer non-essentials
2. **Define MVP** — identifies the single smallest *functional closed loop* that validates the make-or-break assumption
3. **Decompose** — breaks the MVP into ordered steps with In/Out scope and "Done when" criteria
4. **Prioritize** — assigns P0 / P1 / P2 priority, and blocks implementation until you confirm

---

MVPify 拦截你的需求，强制走 4 个阶段的结构化拆解：

1. **裁剪** — 区分核心功能与锦上添花，征得你同意后推迟非必要项
2. **定义 MVP** — 找出最小可行的**功能闭环**，聚焦验证最关键的市场假设
3. **拆解** — 将 MVP 分解为有序步骤，每步明确 In/Out Scope 与"完成标准"
4. **优先级** — 标注 P0 / P1 / P2，在你确认前不动一行代码

---

## Install / 安装

### Manual / 手动安装

Clone this repo and copy the skill folder into your Claude Code skills directory:

```bash
git clone https://github.com/Zhang-Yiqian/MVPify.git
cp -r MVPify/skills/MVPify ~/.openclaw/skills/MVPify
```

---

克隆仓库后，将 skill 文件夹复制到 Claude Code 的 skills 目录：

```bash
git clone https://github.com/Zhang-Yiqian/MVPify.git
cp -r MVPify/skills/MVPify ~/.openclaw/skills/MVPify
```

---

## Usage / 使用方式

Invoke it before describing a large task:

```
/MVPify [your feature request here]
```

Or Claude will trigger it automatically when you describe a large, multi-faceted request containing words like "system", "platform", "full", "complete", or multiple unrelated subsystems.

---

在描述大型需求前触发它：

```
/MVPify [你的需求描述]
```

或者当你的需求包含"系统"、"平台"、"完整"、"全部"等词，或同时涉及多个子系统时，Claude 会自动触发它。

---

## Example / 示例

**Input / 输入:**
> Build a dashboard with charts, filter sidebar, real-time updates, and email notifications when thresholds are crossed.
>
> 做一个带图表、筛选侧边栏、实时更新和阈值邮件通知的 Dashboard。

**MVPify output / 输出:**

| Step | Title | Priority |
|------|-------|----------|
| 1 | Static dashboard with hardcoded data, one chart | P0 |
| 2 | Wire real data from existing API | P0 |
| 3 | Client-side filter sidebar | P1 |
| 4 | Real-time polling (setInterval) | P1 |
| 5 | Email threshold notifications | P2 |

- Flags real-time + email as non-core — deferred to P1/P2
- Defines MVP: prove the layout and data layer work first
- Waits for your confirmation before writing any code

---

- 实时更新和邮件通知被标记为非核心，推迟至 P1/P2
- MVP 目标：先跑通布局和数据层
- 在你确认前不写任何代码

---

## License / 许可证

MIT
