# Статус · 2026-08-06 12:18 UTC

Состояние на 06.08.2026 · ветка `main`, коммит `87185ab` · тестов зелёных: **981** · прод (/api/health): `87185ab`

## Сквозные пути

```
  зелёный · правка по секретной ссылке переживает пересборку
  зелёный · добор пробела закрывает слот словами владельца
  зелёный · с нуля: разговор → карточка → ссылка на правку
  зелёный · посев: карточка из открытых источников → клейм по GB-ID
  зелёный · конвейер: CSV куратора → посевные карточки
Все 6 путей зелёные.
```

## Live (/api/health)

```json
{
    "ok": true,
    "service": "gb-agent",
    "commit": "87185ab",
    "branch": "main",
    "checks": {
        "supabase": true,
        "deepseek": true,
        "openai": true,
        "debugToken": true,
        "provider": "deepseek",
        "webSearch": true,
        "leadEmail": false,
        "migration013": true,
        "migration016": true,
        "migration017": false,
        "seedStatus": true,
        "seedRegistry": true,
        "seedDedup": false,
        "models": {
            "default_provider": "deepseek",
            "extract": {
                "provider": "openai",
                "model": "gpt-5.6-sol",
                "configured": true
            },
            "compile": {
                "provider": "openai",
                "model": "gpt-5.6-luna",
                "configured": true
            },
            "dialog": {
                "provider": "openai",
                "model": "gpt-5.6-luna",
                "configured": true
            },
            "dialog_control": {
                "provider": "openai",
                "model": "gpt-5.6-luna",
                "configured": true
            },
            "websearch": "gpt-5",
            "plan": {
                "extract": "gpt-5.6-sol \u2014 \u0437\u0430\u043c\u0435\u0440 proflain.com: 20 \u0444\u0430\u043a\u0442\u043e\u0432 \u043f\u0440\u043e\u0442\u0438\u0432 12 \u0443 \u0434\u0435\u0448\u0451\u0432\u043e\u0439 \u043d\u0430 \u0442\u043e\u043c \u0436\u0435 \u0442\u0435\u043a\u0441\u0442\u0435",
                "compile": "gpt-5.6-luna \u2014 \u043f\u0435\u0440\u0435\u0441\u043a\u0430\u0437 \u0433\u043e\u0442\u043e\u0432\u044b\u0445 \u0444\u0430\u043a\u0442\u043e\u0432, \u0432\u0445\u043e\u0434 \u043a\u043e\u0440\u043e\u0442\u043a\u0438\u0439, \u0440\u0435\u0437\u0443\u043b\u044c\u0442\u0430\u0442 \u043f\u0440\u043e\u0432\u0435\u0440\u044f\u044e\u0442 \u0441\u0442\u043e\u0440\u043e\u0436\u0430 \u043a\u043e\u0434\u043e\u043c",
                "dialog": "gpt-5.6-luna \u2014 \u0437\u0430\u043c\u0435\u0440: 0 \u043d\u0430\u0440\u0443\u0448\u0435\u043d\u0438\u0439 \u0443 \u0432\u0441\u0435\u0445 \u0442\u0440\u0451\u0445 \u043c\u043e\u0434\u0435\u043b\u0435\u0439, \u0434\u0435\u0448\u0451\u0432\u0430\u044f \u0432 18 \u0440\u0430\u0437 \u0434\u0435\u0448\u0435\u0432\u043b\u0435 \u0441\u0438\u043b\u044c\u043d\u043e\u0439",
                "dialog_control": "gpt-5.6-luna \u2014 \u043a\u043e\u043d\u0442\u0440\u043e\u043b\u044c \u0441\u0440\u0430\u0432\u043d\u0438\u0442\u0435\u043b\u044c\u043d\u043e\u0433\u043e \u043f\u0440\u043e\u0433\u043e\u043d\u0430, \u0432 \u043f\u0440\u043e\u0434\u0435 \u043d\u0435 \u0443\u0447\u0430\u0441\u0442\u0432\u0443\u0435\u0442"
            }
        },
        "prices": {
            "deepseek-chat": {
                "in": 0.28,
                "out": 0.42,
                "source": "provider",
                "effective_at": "2025-09-01"
            },
            "deepseek-v4-flash": {
                "in": 0.28,
                "out": 0.42,
                "source": "estimate",
                "effective_at": "2026-08-01"
            },
            "deepseek-v4-pro": {
                "in": 0.55,
                "out": 2.19,
                "source": "estimate",
                "effective_at": "2026-08-01"
            },
            "deepseek-reasoner": {
                "in": 0.55,
                "out": 2.19,
                "source": "provider",
                "effective_at": "2025-09-01"
            },
            "gpt-4o-mini": {
                "in": 0.15,
                "out": 0.6,
                "source": "provider",
                "effective_at": "2025-09-01"
            },
            "gpt-4o": {
                "in": 2.5,
                "out": 10,
                "source": "provider",
                "effective_at": "2025-09-01"
            },
            "gpt-5.6-luna": {
                "in": 0.2,
                "out": 1.2,
                "source": "owner",
                "effective_at": "2026-07-30"
            },
            "gpt-5.6-terra": {
                "in": 2,
                "out": 12,
                "source": "owner",
                "effective_at": "2026-07-30"
            },
            "gpt-5.6-sol": {
                "in": 5,
                "out": 30,
                "source": "owner",
                "effective_at": "2026-07-30"
            },
            "gpt-5": {
                "in": 0.63,
                "out": 5,
                "source": "estimate",
                "effective_at": "2026-08-01"
            },
            "text-embedding-3-small": {
                "in": 0.02,
                "out": 0,
                "source": "provider",
                "effective_at": "2025-09-01"
            },
            "claude-sonnet-4-5-20250929": {
                "in": 3,
                "out": 15,
                "source": "provider",
                "effective_at": "2025-09-01"
            },
            "claude-haiku-4-5-20251001": {
                "in": 1,
                "out": 5,
                "source": "provider",
                "effective_at": "2025-09-01"
            }
        }
    }
}
```

## До запуска

| № | Пункт | Состояние |
|---|-------|-----------|
| 1 | Посевная карточка честна: плашка, границы обязательств, клейм по GB-ID | готово |
| 2 | Вход конвейера: CSV куратора → карточки, с проверкой, дедупом и реестром | готово |
| 3 | Наполнение по сайту: тест-партия 10 площадок прогнана и принята | ждёт CSV от куратора |
| 4 | Доступность на дате: `availability_mode`, занятость, срок ответа | не начато |
| 5 | Категории волны конфигом (156) и отчёт по волне куратору | не начато |
| 6 | Миграции 016 и 017 применены на проде и видны в `/api/health` | 016 применена, у 017 нет `dedup_key` |


Полная картина продукта и правила — в `HANDOFF.md` рядом.
