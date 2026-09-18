# Work Notes Format Reference

## File Naming

- Weekly log: `YYYY-MM-WN.md` (e.g., `2026-04-W4.md`), WN = week number in the month
- PMI monthly report: `PMI-YYYY-M.DD~M.DD.md` (e.g., `PMI-2026-3.15~4.14.md`)

## Weekly Log Structure

```markdown
# YYYY年M月第N周工作日志

周一 (MM-DD):
- 【项目名】具体工作内容

周二 (MM-DD):
- 非项目条目直接写
```

## Rules

- One file per week, Monday to Friday only
- Title format: `# YYYY年M月第N周工作日志`
- Date separator: `周X (MM-DD):`
- Blank days keep the weekday line (do not delete)
- Project entries: `- 【项目名】内容` (Chinese brackets, e.g., `【TSthUSD】`)
- Non-project entries: plain text, e.g., `- 周会：xxx`
- Images stored in `images/`, naming `YYYYMMDDHHMMSS_description.png`
- Todo items use `todo.md`, format `- [ ] 内容`

## Pre-Write Date Check (Required)

Before writing/editing any work log entry, confirm today's real date:

- Run `date +"%Y-%m-%d %A"` or read the environment's Today's date.
- Convert relative phrases ("today", "yesterday", "记录一下") to absolute dates before deciding which `YYYY-MM-WN.md` and which weekday section to use.
- When crossing week (Monday) or month boundaries, verify whether a new `YYYY-MM-WN.md` file is needed instead of appending to the previous week.
- If the user hasn't specified a date, default to the current real date; ask once if ambiguous.

## Weekly Summary Format (Three sections, one sentence each)

When the user asks for a weekly summary organized by 需求/问题、产出/成果、预期/收益:

```markdown
**需求/问题：** [one sentence — core problems/requirements this week]

**产出/成果：** [one sentence — key deliverables this week]

**预期/收益：** [one sentence — expected benefits from this work]
```

- One sentence per section, no enumeration
- Expand only if the user explicitly asks for more detail

## Weekly Report Body — Section 1 (本周工作成果及总结) Style

The overview section is written for readers outside the project. It must differ from the per-day details below it.

- **Formal written tone.** No colloquial phrasing, no stream-of-consciousness narration.
- **No jargon pile-up.** Class names, function names, file paths, config keys, enums, commands and abbreviations (toolset / i18n / Slate / P95 / FString / StaticMesh ...) belong in the per-day details, not here. If an English abbreviation is unavoidable, give its Chinese equivalent on first use.
- **One theme per numbered item.** Merge related work first; state what was done and what it fixed or delivered, in one sentence.
- **5–7 items**, ordered by importance/value, no duplication across items.
- **Title line** (`**条目标题：**`) follows the same standard: formal, no abbreviations, no implementation terms.
- **Order of work:** read the full weekly log → group into themes → write the overview → then write the per-day details (which keep the technical specifics).

Bad (colloquial): "原先所有工具都堆在一个注册文件里，现在按类别拆回各自模块，顺带修掉了运行控制工具误把编辑器场景当成运行场景的问题"

Bad (jargon): "各 toolset 从 ToolRegistryFactory 迁出、目录改为从注册点自动发现、风险声明前移；i18n 原生目录键转为 FString 修复 UE5.8 JSON 目录键问题"

Good: "工具注册架构整理：工具按类别拆分至各自模块，工具清单改为自动发现，权限与风险等级在注册处统一声明"

