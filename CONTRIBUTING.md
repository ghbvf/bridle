# Contributing to Bridle

> Bridle is **AI-generated and exploratory**. The most valuable contributions are **practical evidence** — case studies of teams adopting (or rejecting) specific mechanisms.

## What we want

In rough order of value:

1. **Real adoption cases** — refute or validate any specific mechanism with evidence from a real project
2. **Anti-pattern additions** — failure modes you've seen in practice that aren't in §12
3. **Tool alternatives** — recommendations replacing or complementing items in `three-leaps-bootstrap.md` Appendix A
4. **Measurement data** — concrete numbers (acceptance rates, governance ROI, R-tier breach incidents)
5. **Translations** — additional languages beyond zh/en
6. **Bug fixes / typos / broken links** — always welcome

## What we don't want

- Speculation without evidence
- "Best practice" claims (Bridle is exploratory by design — see §10 "self-governance red lines")
- Adding mechanisms because they're trendy ("we should integrate vector DBs because LLMs use them")

## How to contribute

### Issues

Open an issue first if you're unsure your change fits scope. Use one of these prefixes:

- `case:` — real adoption evidence (with project name + outcome)
- `anti-pattern:` — failure mode observation
- `tool:` — tool recommendation or replacement
- `data:` — measurement / benchmark
- `bug:` — broken link, typo, factual error
- `discuss:` — open-ended discussion of methodology direction

### Pull requests

1. Fork → branch from `main` → push → open PR against `main`
2. PR title format: same prefix as issue (`case: ACME's L2 intent rollout`)
3. Keep changes focused — one anti-pattern or one tool per PR
4. For methodology changes, update both Chinese and English versions
5. For deck changes, update both `deck/index.html` and `deck/en/index.html`

## Methodology change checklist

If your change touches `three-leaps.md` / `three-leaps.en.md`:

- [ ] Both zh and en versions updated
- [ ] `examples/` updated if a referenced field changed
- [ ] `deck/index.html` + `deck/en/index.html` updated if a section name changed
- [ ] Reading-map table in §0 / §0 updated if a chapter shifted

## Style

- Tone: terse, claims tied to evidence, no marketing language
- Markdown: plain GFM; no HTML except where needed for diagrams
- Code examples: minimal, runnable, comments explain *why* not *what*
- Diagrams: ASCII art preferred over images (better diff, better accessibility, no asset management)

## Decision log

Significant methodology changes are recorded in `docs/adr/` (Architecture Decision Records). Open a PR with a new ADR before changing any axiom (§3.2), pillar (§3.3), or layer (§2).

## Code of conduct

Be respectful. Disagreements about methodology should focus on evidence and reasoning, not personalities. Personal attacks lead to comment lock or ban.

## License

By contributing, you agree your contributions are licensed under the [MIT License](./LICENSE).
