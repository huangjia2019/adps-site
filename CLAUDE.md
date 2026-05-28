# CLAUDE.md — adps-site

Operating notes for Claude when working on this repository.

## What this is

`adpsagent.com` source. **ADPS** = Agent Design Patterns Society — a research community, not a personal site. Voice and visual identity should reflect that: institutional, restrained, not personality-driven.

## Tone rules

- **Not Jia's personal site.** Hide first-person voice. Use plural "we" or institutional voice.
- **No marketing register.** No "thrilled to announce," no "join the revolution," no emoji.
- **Cool palette, brass accent.** Deep blue (`#0f3a5f`) primary, brass (`#b8842b`) for badges/section markers. Do NOT use the kage-ai warm brown/orange — those are Jia's personal brand and ADPS is deliberately differentiated.
- **Reference register:** IEEE/ACM/Linux Foundation tier, not startup landing page.

## Structure rules

- CSS forked from `~/Documents/99-website/kage-ai-site/css/style.css` v0.7. Only colors changed in `:root`; all structural classes (`.intro`, `.block`, `.post-list`, `.training-card`, etc.) reused as-is.
- Bilingual mirror: every EN page has a `/zh/` counterpart at the same path depth.
- Pages use `<body class="page-home">` (home), `<body class="page-essay">` (article-style content pages).

## When editing

- **Hand-write HTML.** No build tools, no framework. Edit `.html` files directly.
- **Test locally:** `python3 -m http.server 8000` from repo root.
- **Commit attribution:** NO `Co-Authored-By: Claude` line. ADPS is solo-attributed to its founders. (See `~/.claude/projects/.../memory/feedback_commit_attribution.md`.)

## Deployment

- GitHub Pages, custom domain via CNAME
- Push to `main` → auto-publish (1-3 min)
- DNS: `adpsagent.com` apex + `www` CNAME → `huangjia2019.github.io`

## Pending setup (user action required)

- **Formspree form ID**: the "Reach out" form on `/` and `/zh/` has `action="https://formspree.io/f/YOUR_FORM_ID"` as a placeholder. Steps:
  1. Sign up at [formspree.io](https://formspree.io) (free tier = 50 submissions/month)
  2. Create a new form, name it "ADPS Reach Out"
  3. Copy the form's endpoint URL (looks like `https://formspree.io/f/abcd1234`)
  4. Replace `YOUR_FORM_ID` everywhere: `grep -rl YOUR_FORM_ID . | xargs sed -i 's|formspree.io/f/YOUR_FORM_ID|formspree.io/f/abcd1234|g'`
  5. Submissions land in the inbox of whatever email you signed up with — store there or export to spreadsheet
- **GoatCounter**: same pattern. Sign up at [goatcounter.com](https://www.goatcounter.com), claim `adps` subdomain. Script in HTML already points to `adps.goatcounter.com/count`.

## Future work

- Migrate `agent-design-patterns` repo from `huangjia2019/*` to a future `ADPS` GitHub Organization. All current links use `huangjia2019/agent-design-patterns` and will need a sweep.
- Add per-pattern detail pages under `/patterns/<pattern-slug>/` once the catalog stabilizes.
- Replace SVG avatar placeholders with real head shots (240×240 cropped, named `avatar-jia.png` etc. — will override SVGs).

## Anti-patterns to avoid

- Don't write blog-style essays on this site. Essays go on `kage-ai.com` (Jia's personal). ADPS is institutional reference, not personal writing.
- Don't embed Jia's photo or first-person bio anywhere except the `/founders/` page where all four members get equal treatment.
- Don't add marketing CTAs ("Buy the book!" "Subscribe!"). Asset links should be flat references.
