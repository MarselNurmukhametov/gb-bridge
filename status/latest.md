# Статус · 01.08 · CARD BUILDER: контракт факта зафиксирован, фикстура Metahim — четыре нуля

## Порядок работ вердикта — пройден целиком

**1. Структура факта зафиксирована** (`src/lib/factContract.ts`) — ровно по
правке куратора, раздельные оси вместо шести смешанных значений:

- `source_type` у каждого утверждения: `owner | website | document | registry | third_party`
- `owner_review_status`: `unreviewed | confirmed | corrected | rejected`
- `verification_status`: `self_asserted | source_supported | independently_verified | conflicted`
- `publication_status`: `draft | published | superseded`
- `resolution`: `auto_selected | owner_override | sources_agree | unresolved`

Факт несёт `assertions[]` + `resolved_value`. Ключевые свойства — тестами:

- **ИНН словами владельца — `self_asserted` по построению** (кейс 3 приёмки
  ядра): `independently_verified` физически недостижим без источника
  `registry` — это не правило в промпте, а устройство типа.
- **Правка владельцем не переписывает историю** (кейс 2): значение сайта
  остаётся в `assertions[]`, итоговым становится слово владельца,
  `resolution: owner_override` — задел под «на сайте всё ещё указано другое».
- Совпадение сайта, владельца и реестра → `sources_agree` +
  `independently_verified` (эталон legal_name из вердикта — тестом).
- Конфликт без владельца (сайт против реестра) → `unresolved` + `conflicted`,
  значение не подменяется.

**2. Шаг 1 SITE-READER v3.1 на этой структуре.** Ридер отдаёт `factRecords`
(website-утверждение: source_ref = страница, evidence = дословная цитата,
черновик). Целевая сущность теперь несёт `business_modes[]` — режимов дела
может быть несколько (производство + поставка + услуги), не один industry.
Все пути записи — на контракте: рассказ и интервью → owner-утверждения;
«Верно» → слово владельца поверх источника (`sources_agree`, confirmed);
правка → `owner_override` с сохранённой историей. Старая схема БД не
ломается: каждая запись с новыми колонками имеет запасной ход без них.

**3–4. Фикстура Metahim — четыре нуля.** Девять настоящих страниц
metahim.tech скачаны и закоммичены в `tests/fixtures/metahim/` — вход
зафиксирован, сайт может меняться, прогон повторяем
(`tools/fixture-metahim.mjs`, живая gpt-4o).

| мерило | обязано | вышло |
|---|---|---|
| unsupported claims | 0 | **0** |
| template contamination | 0 | **0** |
| wrong entity | 0 | **0** |
| placeholder values | 0 | **0** |

Два прогона подряд — нули оба раза (22 с, ≈3 ₽ за прогон). Мед-шаблон
купленной темы (/services, urinalysis) срезан инспекцией; услуги и контакты —
с цитатами-доказательствами; полный отчёт с карточкой и образцом записи
контракта — `e2e/fixture-metahim.md`.

## Цифры

- Тесты: **191 зелёный** (было 173; +18 юнитов контракта).
- Мок-прогон: **137 шагов** (+3 проверки контракта: crawled = website-утверждения,
  слово владельца = self_asserted, правка = owner_override с историей).
- Владельцу передан SQL 008 (assertions + четыре оси, аддитивно) — ждёт
  SQL Editor вместе с 007. Код работает и до миграции.

## Дальше (по вердикту)

Реальные прогоны: «ytn», «снег», клиент с CAS. Затем — дельты 3–4
CARD BUILDER (адаптивное интервью, `not_applicable`) и реестры (шаг 2).
