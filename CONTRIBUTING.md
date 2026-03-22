# Contributing to AI Dev OS

Thank you for your interest in contributing to AI Dev OS!

## How to Contribute

### Reporting Issues

- Use [GitHub Issues](https://github.com/yunbow/ai-dev-os/issues) to report bugs or suggest improvements
- Include the file path and section when reporting documentation issues

### Pull Requests

1. Fork the repository
2. Create a feature branch (`git checkout -b improve-spec`)
3. Make your changes
4. Commit with a descriptive message
5. Push to your fork and open a Pull Request

### What to Contribute

| Directory | What We Need | Guidelines |
|-----------|-------------|------------|
| `spec/` | Corrections, clarifications, new design principles | Changes here affect the entire ecosystem. Discuss in an Issue first. |
| `theory/` | New theoretical connections, updated research references | Keep factual and well-cited. |
| `getting-started/` | Better examples, new language/tool combinations | Must stay in sync with rules/plugin repos. |
| `docs/i18n/` | Translations, translation improvements | See Translation Guide below. |

### Translation Guide

- English files in `spec/`, `theory/`, `getting-started/` are the source of truth
- Translations go in `docs/i18n/{lang}/` mirroring the English structure
- Currently supported: `ja` (Japanese), `zh-CN` (Chinese), `ko` (Korean), `es` (Spanish)
- Keep technical terms, code blocks, URLs, and file paths in English
- Add `Languages:` footer with link back to English version

### Versioning

| Change Type | Version |
|-------------|---------|
| Spec changes (4-layer model, dependency rule) | MAJOR |
| New theory documents, getting-started updates | MINOR |
| Typo fixes, wording improvements | PATCH |

## Code of Conduct

Be respectful, constructive, and inclusive. We welcome contributors of all experience levels.

## Questions?

Open an Issue or start a Discussion on GitHub.

---

Languages: English | [日本語](docs/i18n/ja/CONTRIBUTING.md)
