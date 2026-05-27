# adps-site

Source for **adpsagent.com** — the public site of the **Agent Design Patterns Society (ADPS)**.

## What this is

A small institutional site for a research community sedimenting reusable architecture patterns for production-grade AI agent systems. Built as a static site, no framework, no build step.

## Stack

- Vanilla HTML / CSS / JS
- GitHub Pages + custom domain (CNAME → `adpsagent.com`)
- Local preview: `python3 -m http.server 8000` from repo root, then open `http://localhost:8000`
- Deploy: `git push origin main` — auto-publish in 1-3 minutes

## Structure

```
/                  EN home
/patterns/         28-pattern matrix overview
/research/         arXiv paper + abstract + citation
/founders/         4 founding members
/join/             How to participate
/zh/               Chinese mirror (full bilingual)
css/style.css      Single stylesheet (forked from kage-ai.com v0.7, re-themed cool/brass)
```

## Founding members (2026)

- **Jia Huang** — framework, writing, global narrative
- **Bingsheng Ru (茹炳晟)** — software engineering, R&D productivity
- **Willem (Ning) Jiang (姜宁)** — open source, harness, workflow
- **Bo Liang (梁博)** — enterprise SaaS, FinTech, production feedback

## Related assets

- Paper: [arXiv:2605.13850](https://arxiv.org/abs/2605.13850)
- Pattern catalog: [huangjia2019/agent-design-patterns](https://github.com/huangjia2019/agent-design-patterns)
- Book companion: [huangjia2019/designing-ai-agents](https://github.com/huangjia2019/designing-ai-agents)
- Manning book: [*Designing AI Agents*](https://www.manning.com/books/designing-ai-agents)

## License

Site content: CC BY 4.0. Code in linked repositories: see those repositories.
