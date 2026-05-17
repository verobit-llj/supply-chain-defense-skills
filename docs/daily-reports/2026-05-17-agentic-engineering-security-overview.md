# Дневной обзор аналитика: Вайбкодинг, Agentic Engineering и Безопасность Supply Chain

**Дата:** 17 мая 2026 (24 часа назад)
**Repo:** supply-chain-defense-skills

---

### 1. Вайбкодинг и Agentic Engineering

За последние 24 часа ( и ближайшие дни) доминирует обсуждение перехода от **vibe coding** (быстрое прототипирование по "вибу") к **agentic engineering** (структурированные агенты с oversight, тестами, ревью). Simon Willison ранее отметил их сближение в своей работе — это уже норма.

** Ключевые обновления:**
- **Claude Code** (Anthropic): Полноценный surface-agnostic агент (shell, VS Code, JetBrains, GitHub Actions, web/mobile). Subagents, skills, hooks, plan mode, multitask/parallel agents. Многие используют `.claude.md` + AGENTS.md для правил (включая подтверждения разрушительных действий).
- **Cursor** (3.2+): Parallel subagents (/multitask) стали стандартом.
- **Google Antigravity (Gemini)**: Упоминается как конкурент с параллельными агентами.
- **OpenAI Codex/GPT**: Более "исполнительный" стиль — лучше для четких задач, bugfix, стабильной реализации.

** Паттерны и лучшие практики:**
- Agent Teams: Спавнить специализированных суб-агентов для совместного планирования.
- Karpathy: Agentic engineering — эволюция vibe coding. Инженер = архитектор + supervisor.

** Полезно:** Medium scorecard мая 2026; YouTube live-сессии.

---

### 2. Безопасность и Supply Chain

** Критично:** Продолжается эхо **Mini Shai-Hulud** (11 мая 2026) — массовая атака на npm + PyPI (170+ пакетов). Пострадали TanStack, Mistral AI SDK, UiPath, OpenSearch, Guardrails AI. Крадут credentials, self-propagate. Затронуто ~1800 разработчиков. OpenAI отозвала code-signing certs.

** Рекомендации для AI coding agents:**
- Пиннинг версий + delay updates.
- SCA-тулы (Socket, Snyk, Endor Labs).
- SBOM как living artifact.
- Для агентов: изолированные среды, минимальные permissions, review всех изменений.

** Новые практики:** Переход к operational SBOM (c VEX, continuous monitoring). Инструменты: Syft + Dependency-Track/Anchore, Chainguard, Cosign.

** Риски выросли:** AI-generated code + supply chain = compound threat.

---

### 3. Rust + WASM

- **Rust 1.96** (выход 28 мая 2026): Важное изменение для WASM — удаление `--allow-undefined` в wasm-ld. Может сломать существующие проекты (prepare сейчас!).
- Экосистема: Bun мигрировал на Rust. Rust-to-WASM в production (Figma, 1Password, Shopify).
- **Безопасность/SBOM:** cargo-pants, cdxgen (CycloneDX SBOM для Rust), depsguard.

** Лучшие практики:** Component Model, строгие проверки undefined symbols, аудит зависимостей в CI.

---

### 4. Общие выводы и рекомендации

** Что внедрить прямо сейчас:**
- **Claude Code** + AGENTS.md/Skills + parallel teams для сложных задач; Codex/Cursor — для execution.
- Supply chain defense: Socket/Snyk + pinned deps + SBOM generation (Syft/cdxgen) в CI. Review всех AI PRs + тесты.
- Rust WASM: Подготовься к 1.96 (тестируй nightly).

** Риски, которые выросли:**
- Supply chain worm (npm/PyPI) + AI agents, которые легко тянут новые deps.
- Over-reliance на vibe → technical debt и security holes.

** Добавить в supply-chain-defense-skills:**
- Mini Shai-Hulud case study + mitigation playbook.
- Living SBOM pipeline (Syft + Dependency-Track).
- Rust WASM security checklist (allow-undefined removal, cargo-audit/pants).
- Agent review checklist (permissions, diff review, test coverage).

** Итог дня:** Agentic engineering maturing, но безопасность — must-have. Фокус на oversight и verifiable supply chain. Следи за Rust 1.96 и обновлениями Claude Code.

---

**Источники и ссылки:** См. предыдущий ответ аналитика для детальных ссылок.