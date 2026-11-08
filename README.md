# viewringer Disclosure Check — a free Claude Code skill

A [Claude Code](https://code.claude.com/docs/en/overview) skill that checks affiliate shorts scripts, titles, and descriptions before you post. Paste your text and it returns a pass / caution / fail table with rewrites you can paste as-is.

It checks three things:
1. **Affiliate disclosure** (FTC Endorsement Guides, Amazon Associates): is it the right wording, in the first line of the description, and on screen at the start and end?
2. **Health and efficacy claims**: "cures", "relieves pain", "boosts immunity", "germ-free" and the like on household products.
3. **Hype and superlatives**: "best", "#1", "100%", "today only" and other claims with no source.

Results are for reference only and are not legal advice.

## Install
Copy the `disclosure-check` folder into your skills folder:

```
cp -r disclosure-check ~/.claude/skills/
```

- `~/.claude/skills/` makes it available in every project. To use it in one project only, copy it to `.claude/skills/` inside that project folder.
- On Windows, the folder is `%USERPROFILE%\.claude\skills\`.
- Restart Claude Code after copying.
- If you also use the paid viewringer pack in the same project, both skills can answer "check this script". Install this one only where you don't use the paid pack.

Requires a Claude plan that includes Claude Code (Pro or higher). No API keys or other tools.

## Use
In Claude Code, type `check this script` and paste your script, title, or description.

Try it with: `Best germ-free rack, cures back pain, today only!`

## Example output (real run, shortened)
Input: `check this script` + `Best germ-free rack, cures back pain, today only!`
```
## Check results (checked 2026-11-08)
Summary: pass 0 · caution 0 · fail 6

| # | Section | Item | Result | Problem line (where) | Suggested rewrite |
|---|---|---|---|---|---|
| 1 | Disclosure | First line of description | ❌ Fail | No description was provided, and the script has no disclosure | First line of description: "As an Amazon Associate I earn from qualifying purchases." |
| 3 | Health/efficacy | "cures back pain" | ❌ Fail | Script, hook line: says the product treats a medical condition | "It stands [N] cm tall, so things sit at about waist height." |
| 6 | Hype | "today only!" | ❌ Fail | Script, hook line: deadline pressure that can't be verified | "Check the current price at the link." |
...
```

## Want the full workflow?
The paid **viewringer Shopping Shorts** pack turns an Amazon link into a full plan: hooks, an 8-cut shot list, narration, per-cut AI video prompts, platform copy, and a 6-section check (adds price wording, copyright, and platform labels).
→ https://viewringer.gumroad.com/l/shorts-planner

## License
MIT — see [LICENSE](LICENSE).
