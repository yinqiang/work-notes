# Work Notes Skill

工作日志助手 — 为 AI 编程 Agent 提供个人工作日志管理能力，自动处理每日 git 提交记录录入、手动记录补充、周工作汇总和月度 PMI 生成。

## 功能特性

- **每日提交录入** — 从任意仓库查询 git 提交，简化后翻译成中文，追加到对应星期
- **手动记录** — 说「记录：xxx」直接补充当天条目
- **周工作汇总** — 「列一下本周工作成果」按星期分组列出所有条目
- **月度 PMI 生成** — 汇总当月所有周志，按项目生成中英双语一句话总结
- **路径无关** — 不硬编码任何路径，自动识别或创建工作日志目录
- **多目录支持** — 可同时维护多个独立的工作日志仓库

## 快速上手

### 安装

```bash
npx skills add 你的用户名/work-notes
```

### 首次使用

找不到工作日志目录时，skill 会询问你指定已有路径或创建新目录。确认后会写入 `.worknotes` 标记文件，后续自动识别。

### 示例工作流

```
查看 ~/projects/myapp 里今天的提交日志，简化后翻译成中文加入今天的工作记录
```
→ 查询 git，简化 commit，追加到本周对应星期

```
记录：完成用户认证模块的 API 联调
```
→ 追加到当天星期条下

```
列一下本周目前的工作成果
```
→ 按星期分组列出本周所有条目

```
生成月度 PMI
```
→ 收集当月所有 W* 文件，按项目归类，输出中英双语总结

## 工作日志格式

### 周志（`YYYY-MM-WN.md`）

```markdown
# 2026年4月第4周工作日志

周一 (04-20):
- 【项目名】具体工作内容

周二 (04-21):
```

### 月度 PMI 报告（`PMI-YYYY-M.DD~M.DD.md`）

```markdown
- 【项目1】中文一句话总结
- 【项目2】中文一句话总结

- Project 1: English one-sentence summary
- Project 2: English one-sentence summary
```

## 目录识别逻辑

skill 从当前工作目录向上逐级搜索（最多 5 层），匹配以下任一条件即识别为工作日志目录：

- 存在 `YYYY-MM-W*.md` 文件（周志）
- 存在 `PMI-*.md` 文件（PMI 月报）
- 存在 `.worknotes` 标记文件

找不到时询问用户指定或创建。

## 目录结构

```
work-notes/
├── SKILL.md
├── README.md
└── references/
    ├── work-notes-format.md   # 周志详细格式规范
    └── pmi-format.md          # PMI 月报格式规范
```

## 安装方式

```bash
# 从 GitHub 安装
npx skills add https://github.com/你的用户名/work-notes

# 或克隆到本地
git clone https://github.com/你的用户名/work-notes.git
```
