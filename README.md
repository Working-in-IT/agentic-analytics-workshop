# Агентная аналитика для продактов

Материалы воркшопа Podlodka ProductCrew «Агентная аналитика для продактов». Контекст продукта превращает AI-агента из улучшенного ChatGPT в аналитического партнёра — покажем разницу на двух кейсах в двух репозиториях.

## Сайт

**[working-in-it.github.io/agentic-analytics-workshop](https://working-in-it.github.io/agentic-analytics-workshop)**

## Что внутри

- **[Главная](https://working-in-it.github.io/agentic-analytics-workshop/index.html)** — что покажем, программа, материалы
- **[Подготовка](https://working-in-it.github.io/agentic-analytics-workshop/setup.html)** — Python, git, VS Code, Claude Code, smoke test (macOS / Linux / Windows)
- **[Промпты](https://working-in-it.github.io/agentic-analytics-workshop/prompts.html)** — два промпта для двух демо, готовые к копированию

## Структура воркшопа

Два публичных репо для A/B-контраста:

| Репо | Контекст | Что внутри |
|------|----------|------------|
| [**fitflow-bare**](https://github.com/Working-in-IT/fitflow-bare) | минимальный | Только `data/fitflow.db` — без описания продукта, без словаря данных, без скиллов |
| [**fitflow-rich**](https://github.com/Working-in-IT/fitflow-rich) | богатый | Та же база + CLAUDE.md, PRODUCT_CONTEXT.md, data dictionary, 7 аналитических скиллов |

Датасет одинаковый: SQLite-база FitFlow (вымышленное фитнес-приложение) — 107K событий и 1.1K NPS-отзывов на русском.

## Формат воркшопа (90 мин)

| Часть | Время | Что делаем |
|-------|-------|------------|
| Введение | 15 мин | Что такое агентная аналитика, чем агент отличается от чат-бота, почему контекст — главная инвестиция |
| Демо 1 — числа | 25 мин | Воронка онбординга: плохой промпт в bare → хороший промпт в bare → тот же вопрос в rich |
| Демо 2 — текст | 15 мин | Анализ NPS-фидбэка: тот же контраст на другом типе данных |
| Перенос на свой продукт | 25 мин | Пять шагов: что взять из rich-репо, как описать свой продукт, какие скиллы пригодятся |
| Q&A | 10 мин | Вопросы, ссылки, как продолжить после воркшопа |

## Инструмент

**VS Code** с расширением **[Claude Code](https://docs.anthropic.com/en/docs/claude-code)** и активной подпиской Claude (Pro / Max / Team / Enterprise) или API-доступом.

**[Полная инструкция по установке](https://working-in-it.github.io/agentic-analytics-workshop/setup.html)** — пройдите за день до воркшопа.

## Быстрый старт

```bash
# Установить инструменты (см. setup.html для деталей по ОС)
brew install python@3.12 git
brew install --cask visual-studio-code
code --install-extension anthropic.claude-code

# Склонировать оба репо
cd ~/Projects
git clone https://github.com/Working-in-IT/fitflow-bare.git
git clone https://github.com/Working-in-IT/fitflow-rich.git

# Зависимости для скиллов rich-репо
cd fitflow-rich
python3 -m venv .venv && source .venv/bin/activate
pip install scikit-learn scipy numpy
```

Дальше — открыть оба репо в VS Code, авторизоваться в Claude Code, [взять промпты](https://working-in-it.github.io/agentic-analytics-workshop/prompts.html) и сравнить ответы.

## Три принципа агентной аналитики

1. **Контекст решает** — чем лучше описан продукт и данные, тем точнее анализ. Хороший промпт даёт generic-ответ без контекста; контекст превращает generic в product-grounded.
2. **A/B-контраст обучает быстрее объяснений** — один промпт в двух репо за 30 минут даёт понимание, на которое уходят дни чтения статей.
3. **Инвестиция один раз, эффект в каждом запросе** — CLAUDE.md и data/README.md пишутся один раз, дальше агент использует их в каждом анализе.

## Кредиты

- Оригинальные данные FitFlow: [Working-in-IT/agentic-analytics-workshop](https://github.com/Working-in-IT/agentic-analytics-workshop) (прошлая версия)
- Идея skill-pack для агентов: [nimrodfisher/data-analytics-skills](https://github.com/nimrodfisher/data-analytics-skills) (с атрибуцией)
- Автор: [Данила Шевцов](https://t.me/working_in_it) / Telegram-канал «Работая в айтишечке»

---

Working in IT
