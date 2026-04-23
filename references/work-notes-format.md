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
