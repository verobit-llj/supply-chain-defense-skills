# Agentic Engineering Patterns (из Anthropic, Karpathy и лучших практик)

** Цель файла:** Дать агенту структурированные паттерны безопасного и эффективного agentic coding, а не только чистый "vibe".

## 1. Основное различие: Vibe Coding vs Agentic Engineering

**Vibe Coding** (Karpathy, 2025): Дай себе волю, пиши на натуральном языке, забудь про код.
**Agentic Engineering** (Karpathy, 2026): Более зрелая дисциплина — декомпозиция, оверсайт, параллельная работа агентов, human judgment.

** Вывод:** Чистый vibe подходит для прототипов. Для production и критической инфраструктуры нужен Agentic Engineering.

## 2. Ключевые паттерны от Anthropic

### Pattern: Planning Mode First
** Правило:** Перед выполнением крупной задачи агент обязан показать план.

** Пример промпта:**
> "Think step by step. First create a detailed plan with phases, then ask for my approval before implementing each phase."

### Pattern: Human Oversight Loop
** Правило:** Все критически е изменения (auth, payments, unsafe, supply chain) должны проходить через подтверждение человека.

### Pattern: Multi-Agent + Sub-agents
** Правило:** Разделять сложные задачи на специализированных под-агентов (один делает план, второй — реализацию, третий — ревью безопасности).

### Pattern: Security by Design from the Start
** Правило:** При постановке задачи сразу просить агента учесть требования безопасности и supply chain risks.

## 3. Паттерны от Karpathy (Agentic Engineering)

- Агенты как "interns" или "ghosts" — они нуждаются в вкусе, judgment и оверсайте.
- Декомпозируй задачи на мелкие, проверяемые шаги.
- Используй параллельную работу нескольких агентов с разными ролями.
- Человек остаётся ответственным за архитектуру и качество.

## 4. Практические промпты и подходы

**Planning + Security Check:**
> "Create a detailed implementation plan first. In the plan, explicitly mark all security-sensitive parts and supply chain risks. Only after my approval proceed with coding."

**Review Loop:**
> "After implementing, perform a security review of the changes, especially regarding dependencies and unsafe code. Highlight any risks."

**Sub-agent approach:**
> "Act as a project manager. Create one sub-agent for architecture, one for implementation, and one for security review. Coordinate between them."

---

** Используй эти паттерны вместо с чистым vibe coding, когда работаешь над серьёзными проектами.**