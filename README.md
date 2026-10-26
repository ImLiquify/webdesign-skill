# /webdesign

A Claude Code skill that runs a web design request through the best design skills in the right order: copy, real-world references, design direction and build, motion, browser check, review, and performance. It loads only the skills the request needs and gives each stage one owner, so skills don't fight over the look.

## Install

```bash
npx skills add ImLiquify/webdesign-skill@webdesign -g -y
```

Then install the skills it routes to (any missing one is skipped):

```bash
npx skills add vercel-labs/skills --skill find-skills -g -y
npx skills add vercel-labs/agent-skills@web-design-guidelines -g -y
npx skills add pbakaus/impeccable@impeccable -g -y
npx skills add leonxlnx/taste-skill@design-taste-frontend -g -y
npx skills add nextlevelbuilder/ui-ux-pro-max-skill@ui-ux-pro-max -g -y
npx skills add emilkowalski/skills@apple-design -g -y
npx skills add shadcn-ui/ui@shadcn -g -y
npx skills add coreyhaines31/marketingskills@copywriting -g -y
npx skills add anthropics/skills@frontend-design -g -y
```

## Use

```
/webdesign a landing page for a coffee shop
/webdesign quick a one-section hero for my portfolio
/webdesign review the homepage and fix what you find
/webdesign upgrade
```

| Mode | What it does |
|---|---|
| (default) | Full pipeline: copy, references, build, motion, browser check, review, performance |
| `quick` | Skips optional stages |
| `review` | Audits existing UI, reports findings, asks before fixing |
| `upgrade` | Searches skills.sh for better skills, vets them, installs only what you approve |

## How it works

| Stage | Owner |
|---|---|
| Copy (sites) | `copywriting` |
| References | browser: studies 3 well-designed sites and writes a brief of patterns to borrow |
| Direction and build | `design-taste-frontend` (sites) or `impeccable` (apps), helped by `ui-ux-pro-max` and `shadcn` |
| Motion | `apple-design`, only for gestures and interactive transitions |
| Browser check | screenshots at 375px and 1440px |
| Review | `web-design-guidelines`, then `impeccable` audit and polish |
| Performance | `webperf`, only for production or when speed comes up |

Visual changes always go through the design lead and reuse your site's existing fonts, colours and spacing. A **Lessons** section in the skill file records what went wrong in past runs, and every run reads it.

The skill only runs when you type `/webdesign`. Claude never starts it on its own.

## License

MIT
