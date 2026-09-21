# AI Camp · Enrich and Pitch

Claude Skill для outbound-разведки B2B-клиентов в Казахстане: досье на компанию + готовое opening-сообщение под ЛПР.

AI Camp Almaty 2026: воркшоп майской сессии **«AI в продажах на практике»** и живое демо сентябрьской сессии **«AI в продажах и коммуникациях»** (21.09).
Спикер: **Дмитрий Коробовцев**, AI Surfers.

---

## Что делает

```
/enrich-and-pitch Globalink Logistics. Мы продаём: AI-инструменты для отдела продаж.
```

Skill:
1. Подтверждает, что нашёл именно ту компанию (особенно важно для KZ — много омонимов в реестре)
2. Делает разведку в 4 этапа: компания и ЛПР, рынок (бесплатно), LinkedIn ЛПР и соцсети (Instagram) - с ключом Apify
3. Извлекает SPSV-материал (Ситуация / Проблема / Решение / Ценность)
4. Формирует hook через 3 итерации с показом изменений
5. Рендерит HTML-отчёт с двумя вкладками: «Аналитика» + «Коммуникация»
6. Автоматически открывает отчёт в браузере

Время от вызова до отчёта: несколько минут на этапы 1-2, этапы 3-4 добавляют ещё пару минут. После этапов 2 и 3 скилл спрашивает, продолжать ли.

---

## Quick Start

### Что нужно установить (one-time, ~15 мин)

1. **VS Code** — `code.visualstudio.com`
2. **Claude Code extension** — поиск «Claude Code» в VS Code marketplace
3. **Anthropic аккаунт** — Claude Pro или API ключ (`console.anthropic.com`)

### Запуск

```bash
git clone https://github.com/dkoraitest/ai-camp-enrich-and-pitch.git
cd ai-camp-enrich-and-pitch
code .
```

Если хочешь этапы 3-4 (LinkedIn и Instagram ЛПР), скопируй `.env.example` в `.env` и впиши ключ Apify. Без ключа скилл работает на бесплатном стеке.

В VS Code откроется репо со встроенным Claude Code. Вызывай skill из чата:

```
/enrich-and-pitch <название компании>. Мы продаём: <что мы продаём>.
```

---

## Free стек vs опциональные платные интеграции

Skill работает **out-of-the-box на free-стеке** (WebSearch, WebFetch, adata.kz, hh.kz). Не требует API-ключей.

Для **продвинутого качества** можно подключить:
- **Apify** - профиль и посты ЛПР в LinkedIn, Instagram компании. Бесплатного плана ($5 в месяц) хватает на десятки компаний: этапы 3-4 стоят центы на компанию. Ключ: console.apify.com → Settings → Integrations
- **goszakup.gov.kz token** — история госзакупок компаний (бесплатно, нужна заявка)
- **Scrape.do** — обход блокировок ($0.10-1/запрос)

Skill автоопределяет наличие env-ключей и переключается на paid-режим, если они есть.

---

## Структура репозитория

```
ai-camp-enrich-and-pitch/
├── .claude/skills/enrich-and-pitch/
│   ├── SKILL.md                       # сам скилл
│   └── templates/report.html          # HTML-шаблон отчёта
├── reports/                           # тут появляются твои HTML-отчёты (в .gitignore)
├── .env.example                       # шаблон ключей, все необязательные
├── README.md
└── LICENSE
```

---

## Другие материалы AI Camp Almaty 2026

- **[ai-camp-sales-cabinet](https://github.com/dkoraitest/ai-camp-sales-cabinet)** - главная практика сентябрьской сессии: рабочий слой отдела продаж поверх CRM, кабинет менеджера и руководителя

Майские воркшопы:

- **[ai-camp-info-helper](https://github.com/dkoraitest/ai-camp-info-helper)** — Claude Skill с cron-запуском: утренние поводы касания по списку клиентов
- **[ai-camp-lead-scoring](https://github.com/dkoraitest/ai-camp-lead-scoring)** — Промпт + методология приоритизации входящих лидов для РОПа
- **[ai-camp-proposal-template](https://github.com/dkoraitest/ai-camp-proposal-template)** — Skill `make-proposal`: транскрипт звонка → SPSV → research → brainstorming → HTML КП

---

## Контакты + обратная связь

Telegram: @dkorobovtsev
Email: dkor.aitest@gmail.com

Если что-то не работает, что-то получилось не так как описано, или хочешь поделиться кейсом из своего бизнеса — пиши.

---

## License

MIT — см. [LICENSE](LICENSE).
