# GB — инвентаризация 08.08.2026

Собрано прогоном по живому проду. Правило запроса соблюдено: строки
«работает» без ссылки нет; всё, что не проверено, помечено как непроверенное.

**Проверка ссылок.** Все коды ниже сняты `curl` из чистой среды без кук и
без сессии — это эквивалент инкогнито. Браузером глазами я их не открывал.

---

## БЛОК 0. Точка кода

| что | значение |
| --- | --- |
| SHA в `main` | `008544cd3ae55e11b6e207574a0d5d1d7603e52c` (`008544c`) |
| SHA в Production | `008544c` |
| совпадают | **да** |
| незамерженные ветки | нет |
| открытые PR | нет |

Канон — прод: **https://gb-agent-git-main-gb16.vercel.app**
Смотреть надо здесь. Своего домена (`grandbazar.ai`) на этом проекте нет.

`/api/health` → https://gb-agent-git-main-gb16.vercel.app/api/health — **200**

```
commit: 008544c · branch: main
supabase: true · deepseek: true · openai: true
debugToken: true · seedToken: SEED_TOKEN (fingerprint c03d1af9, длина 32)
provider: deepseek · webSearch: true
leadEmail: FALSE
migration013/016/017/018: true · seedStatus/seedRegistry/seedDedup: true
модели: extract gpt-5.6-sol (openai) · compile gpt-5.6-luna · dialog gpt-5.6-luna
```

Ветка `claude/seed-token-env-check-yd7sog` смержена в `main` перемоткой,
кнопка Марселя не нужна.

**Миграции 019 в health нет** — проверки на неё не заведено, применена она
или нет, из сессии не видно. Код работает в обоих случаях.

---

## БЛОК 1. Ссылки

### Платформа

| экран | ссылка | что увидит владелец | код |
| --- | --- | --- | --- |
| корень | https://gb-agent-git-main-gb16.vercel.app/ | редирект на `/start` | **307** |
| вход с нуля | https://gb-agent-git-main-gb16.vercel.app/start | экран разговора | **200** |
| реестр карточек | https://gb-agent-git-main-gb16.vercel.app/catalog | список, поиск, 12 строк + «показать ещё» | **200** |
| витрина демо | https://gb-agent-git-main-gb16.vercel.app/t/demo | демо-карточка | **200** |
| телеметрия | https://gb-agent-git-main-gb16.vercel.app/gb-debug?token=ZLLtRD%2BxL4%2F392ppqdovWfFUlEE46DEJ | счётчики и лента трейсов | **200** |

Лендинга нет: корень уводит на `/start`.

### Машинный слой

| адрес | есть? | код |
| --- | --- | --- |
| https://gb-agent-git-main-gb16.vercel.app/robots.txt | да | **200** |
| https://gb-agent-git-main-gb16.vercel.app/api/lavka/demo.json | да | **200** |
| https://gb-agent-git-main-gb16.vercel.app/api/lavkas.json | **нет** | 404 |
| https://gb-agent-git-main-gb16.vercel.app/llms.txt | **нет** | 404 |
| https://gb-agent-git-main-gb16.vercel.app/llms-full.txt | **нет** | 404 |
| https://gb-agent-git-main-gb16.vercel.app/for-machines | **нет** | 404 |

### Первые три ссылки, чтобы увидеть лучшее за пять минут

1. https://gb-agent-git-main-gb16.vercel.app/catalog — вся площадь одним экраном
2. https://gb-agent-git-main-gb16.vercel.app/t/premialnyy-mednyy-loft-cupru-n9rq — самая полная карточка (53 факта, 10/12 слотов)
3. https://gb-agent-git-main-gb16.vercel.app/gb-debug?token=ZLLtRD%2BxL4%2F392ppqdovWfFUlEE46DEJ — что происходит внутри

### Карточки посева — все 25 строк реестра

| GB-ID | витрина | наполнение | собрана | источник | статус |
| --- | --- | --- | --- | --- | --- |
| `GB-7V3482` | [pillow-loft-dlya-polnoy-rela-ya7q](https://gb-agent-git-main-gb16.vercel.app/t/pillow-loft-dlya-polnoy-rela-ya7q) | 31 фактов · 8/12 слотов | 2026-08-07 | https://loft2rent.ru/loft/3593/215475 | посев |
| `GB-CZD2YX` | [osd-loft-s-ochen-strannymi-d-6rqx](https://gb-agent-git-main-gb16.vercel.app/t/osd-loft-s-ochen-strannymi-d-6rqx) | 40 фактов · 9/12 слотов | 2026-08-07 | https://loft2rent.ru/loft/3593/215438 | посев |
| `GB-CZTXBY` | [bolshoy-loft-100m2-s-bilyard-o28x](https://gb-agent-git-main-gb16.vercel.app/t/bolshoy-loft-100m2-s-bilyard-o28x) | 38 фактов · 10/12 слотов | 2026-08-07 | https://loft2rent.ru/loft/83754/84266 | посев |
| `GB-PB5JHW` | [loft-ermitazh-s-letney-veran-tm9m](https://gb-agent-git-main-gb16.vercel.app/t/loft-ermitazh-s-letney-veran-tm9m) | 31 фактов · 8/12 слотов | 2026-08-07 | https://loft2rent.ru/loft/43392/158026 | посев |
| `GB-7JE9H9` | [sevilya-uyutnyy-loft-s-mebel-7fi4](https://gb-agent-git-main-gb16.vercel.app/t/sevilya-uyutnyy-loft-s-mebel-7fi4) | 43 фактов · 9/12 слотов | 2026-08-07 | https://loft2rent.ru/loft/142644/192374 | посев |
| `GB-CMUMM2` | [premialnyy-mednyy-loft-cupru-n9rq](https://gb-agent-git-main-gb16.vercel.app/t/premialnyy-mednyy-loft-cupru-n9rq) | 53 фактов · 10/12 слотов | 2026-08-07 | https://loft2rent.ru/loft/22257/57955 | посев |
| `GB-HSZVLV` | [loft-erker-s-verandoy-6hz0](https://gb-agent-git-main-gb16.vercel.app/t/loft-erker-s-verandoy-6hz0) | 44 фактов · 8/12 слотов | 2026-08-07 | https://loft2rent.ru/loft/884/215882 | посев |
| `GB-LR6VT2` | [sanandreas-loft-dlya-teh-qz95](https://gb-agent-git-main-gb16.vercel.app/t/sanandreas-loft-dlya-teh-qz95) | 34 фактов · 8/12 слотов | 2026-08-07 | https://loft2rent.ru/loft/3593/215450 | посев |
| `GB-5JUZ2V` | [euphoria-stilnyy-loft-na-tag-bfau](https://gb-agent-git-main-gb16.vercel.app/t/euphoria-stilnyy-loft-na-tag-bfau) | 40 фактов · 8/12 слотов | 2026-08-07 | https://loft2rent.ru/loft/3593/41471 | посев |
| `GB-RVABF7` | [dvuhetazhnyy-dom-dlya-meropr-1oec](https://gb-agent-git-main-gb16.vercel.app/t/dvuhetazhnyy-dom-dlya-meropr-1oec) | 46 фактов · 10/12 слотов | 2026-08-07 | https://loft2rent.ru/loft/155206/182635 | посев |
| `GB-5TVX6A` | [loft-noar-nxlu](https://gb-agent-git-main-gb16.vercel.app/t/loft-noar-nxlu) | 39 фактов · 9/12 слотов | 2026-08-07 | https://loft2rent.ru/loft/108186/116727 | посев |
| `GB-2GVRYX` | [alle-hall-uyutnoe-prostranst-eyuk](https://gb-agent-git-main-gb16.vercel.app/t/alle-hall-uyutnoe-prostranst-eyuk) | 34 фактов · 7/12 слотов | 2026-08-07 | https://loft2rent.ru/loft/121787/121789 | посев |
| `GB-NYA3BK` | — | снята куратором | 2026-08-07 | https://loft2rent.ru/loft/30985/124045 | — |
| `GB-AFL7AD` | [klassik-elegantnyy-loft-v-kl-b97d](https://gb-agent-git-main-gb16.vercel.app/t/klassik-elegantnyy-loft-v-kl-b97d) | 50 фактов · 9/12 слотов | 2026-08-07 | https://loft2rent.ru/loft/142644/142902 | посев |
| `GB-UJKXH4` | [loft-palermo-14l9](https://gb-agent-git-main-gb16.vercel.app/t/loft-palermo-14l9) | 36 фактов · 8/12 слотов | 2026-08-07 | https://loft2rent.ru/loft/58720/197479 | посев |
| `GB-DD9KBH` | [memori-tancevalnyy-loft-s-ka-5du7](https://gb-agent-git-main-gb16.vercel.app/t/memori-tancevalnyy-loft-s-ka-5du7) | 33 фактов · 8/12 слотов | 2026-08-07 | https://loft2rent.ru/loft/142644/142871 | посев |
| `GB-ZE8A2R` | [prostranstvo-s-terassoy-do-5-p6tr](https://gb-agent-git-main-gb16.vercel.app/t/prostranstvo-s-terassoy-do-5-p6tr) | 8 фактов · 7/12 слотов | 2026-08-07 | https://loft2rent.ru/loft/199576/215741 | посев |
| `GB-7EFXBX` | [graphics-loft-s-graficheskim-gcuy](https://gb-agent-git-main-gb16.vercel.app/t/graphics-loft-s-graficheskim-gcuy) | 31 фактов · 9/12 слотов | 2026-08-07 | https://loft2rent.ru/loft/3593/215455 | посев |
| `GB-N8ZH8N` | [prostornyy-loft-na-vernisazh-w5jy](https://gb-agent-git-main-gb16.vercel.app/t/prostornyy-loft-na-vernisazh-w5jy) | 40 фактов · 10/12 слотов | 2026-08-07 | https://loft2rent.ru/loft/2148/189515 | посев |
| `GB-4KE4CJ` | — | снята куратором | 2026-08-07 | https://loft2rent.ru/loft/186117/212972 | — |
| `GB-GLT6WG` | [uyutnyy-loft-persid-2fnx](https://gb-agent-git-main-gb16.vercel.app/t/uyutnyy-loft-persid-2fnx) | 45 фактов · 9/12 слотов | 2026-08-07 | https://loft2rent.ru/loft/108186/116722 | посев |
| `GB-R4AXYB` | [blekberri-kamernyy-loft-v-te-xz4l](https://gb-agent-git-main-gb16.vercel.app/t/blekberri-kamernyy-loft-v-te-xz4l) | 35 фактов · 8/12 слотов | 2026-08-07 | https://loft2rent.ru/loft/142644/222812 | посев |
| `GB-X824E7` | [brodniki-loft-isad](https://gb-agent-git-main-gb16.vercel.app/t/brodniki-loft-isad) | 9 фактов · 7/12 слотов | 2026-08-07 | https://loft2rent.ru/loft/115308/115382 | посев |
| `GB-MM2W7A` | [loft-lodzh-9-ozzp](https://gb-agent-git-main-gb16.vercel.app/t/loft-lodzh-9-ozzp) | 31 фактов · 8/12 слотов | 2026-08-07 | https://loft2rent.ru/loft/6825/143877 | посев |
| `GB-3QL8FL` | — | снята куратором | 2026-08-07 | https://loft2rent.ru/loft/13771/44595 | — |
**Всего карточек в базе: 37.** Из них посевных 22, с подтверждённым
владельцем 3, скрытых 0. Числа из `/gb-debug`.

**Пятнадцати карточек в этой таблице нет, и это честный пробел.** Реестр
посева (`/api/cards?format=csv`) содержит только посевные. Старые карточки
(`demo`, `researchlabs-*`, `r-labs-*`, «Горки», пять боевых с d2table.ru,
liberum-auto.ru, gorky-team.ru, b2b.rms-company.ru, partnertorg.com,
`GB-Q2GPQK`) в нём не лежат, а `/catalog` рендерит только первые 12 строк —
остальные догружаются кнопкой на клиенте, и в HTML их нет. **Полного
списка слагов из базы у меня нет.**

Достать его можно одним запросом (Марселю, в Supabase SQL editor):

```sql
select slug, identifier, edit_token, seed_status,
       card->'source'->>'domain' as domain, created_at, updated_at
from cards order by created_at;
```

### Экраны правки — ссылок нет, и это тоже честный минус

`…/t/<slug>/edit?t=<токен>` собрать не могу: `edit_token` лежит только в
базе, и **ни один эндпоинт его не отдаёт — это сделано нарочно**, токен
есть дверь в чужое дело. Тот же SQL выше вернёт токены, и ссылки
собираются подстановкой.

### Мост

Репозиторий подключён и склонирован, все четыре файла на месте:

| файл | raw-ссылка |
| --- | --- |
| статус | https://raw.githubusercontent.com/MarselNurmukhametov/gb-bridge/main/status/latest.md |
| тесты | https://raw.githubusercontent.com/MarselNurmukhametov/gb-bridge/main/tests/latest.txt |
| трейсы | https://raw.githubusercontent.com/MarselNurmukhametov/gb-bridge/main/traces/latest.md |
| аудит | https://raw.githubusercontent.com/MarselNurmukhametov/gb-bridge/main/audit/latest.md |

Эта инвентаризация:
https://raw.githubusercontent.com/MarselNurmukhametov/gb-bridge/main/status/inventory-08-08.md

Свежесть содержимого этих четырёх файлов я не сверял — только наличие.

---

## БЛОК 2. Что реально работает

### Работает насквозь

| способность | доказательство |
| --- | --- |
| чтение страницы объекта → факты | 22 из 22 карточек наполнены живым чтением, средне 36 фактов. Таблица выше |
| сборка по 12 слотам + контракты + приёмка | средне 8,5 слота из 12, порог «≥7» прошли 22 из 22 |
| постоянный ID `GB-` | колонка GB-ID в таблице выше, ID не менялись при пересборке |
| JSON-LD и машинный блок | https://gb-agent-git-main-gb16.vercel.app/api/lavka/demo.json — 200 |
| чат агента, валидатор, регрессия | 22 карточки прошли критическую четвёрку 4/4 |
| реестр `/catalog` | 200, 12 строк, поиск, метки происхождения |
| ссылка на источник кликабельна | на витрине ведёт на страницу объекта, `rel=nofollow` |
| скрытие карточки владельцем | `/api/cards/hide`: без токена 400, с чужим 403, серия 429 |

### Работает с оговоркой

| что | оговорка |
| --- | --- |
| приёмка карточки | из 32 живых прогонов 10 упёрлись в приёмку и потребовали починки сторожей; сейчас 22/22, но запас прочности не мерян |
| стоимость сборки | выросла с 0,28 ₽ до 1,68 ₽ за карточку — читаем вчетверо больше |
| две карточки тонкие | `BRODNIKI LOFT` 9 фактов, `Пространство с террасой` 8 — на источнике материала объективно меньше |
| `/catalog` | показывает 12 из 22, остальное кнопкой на клиенте |

### Не работает

| что | как проявляется |
| --- | --- |
| **заявка живому человеку НЕ доходит** | `/api/health` → `leadEmail: false`. Заявка пишется в таблицу `leads` (их 5), но письмо не уходит никуда: адрес не настроен. Владелец о заявке не узнает |
| `/llms.txt`, `/llms-full.txt` | 404 |
| `/for-machines` | 404 |
| `/api/lavkas.json` | 404 |
| лендинг | нет, корень редиректит на `/start` |

### Не проверял в этой инвентаризации

`/start` глазами не проходил — экран отдаёт 200, но состояние интервью с
нуля (жалоба на служебные строки и счётчик блоков) **не перепроверено**.
Добор фактов разговором, очередь вопросов гостей, экран правки — не
открывал. Стабильность «сколько из десяти запусков дали карточку» на
сайтах компаний не мерил: вся неделя ушла на страницы объектов.

---

## БЛОК 3. Цифры

| показатель | значение |
| --- | --- |
| коммитов в `main` за сессию | 24 |
| PR смержено | 0 (мерж перемоткой веткой) |
| тестов зелёных | **1077** |
| карточек в базе | 37 |
| из них посевных наполнено | 22 из 22 |
| подтверждено владельцем | 3 |
| диалогов | 132 |
| трейсов | 300 (потолок выборки) |
| заявок создано | 5 |
| **заявок дошло до человека** | **0** — доставки нет |
| стоимость сборки карточки | 1,68 ₽ (было 0,28 ₽) |
| сожжено всего (по трейсам) | 71,31 ₽ |

Цифра 71,31 ₽ — сумма по последним 300 трейсам, то есть **нижняя
граница**: более старые в выборку не попали.

---

## БЛОК 4. Дефекты

### Видит клиент

1. **Заявка уходит в никуда.** Гость оставляет телефон, агент говорит
   «владелец свяжется» — владелец об этом не узнаёт. `leadEmail: false`.
   Причина: не настроен адрес доставки. Починка: ~1 час плюс переменная
   окружения.
2. **Две тонкие карточки** — https://gb-agent-git-main-gb16.vercel.app/t/brodniki-loft-isad
   (9 фактов). Причина: на источнике мало материала. Это граница
   источника, не дефект конвейера.

### Видит владелец

3. **Экран правки недостижим без базы.** Токен нигде не показывается
   после создания; если владелец потерял письмо — восстановления нет.
   Починка: экран восстановления по контакту, ~день.
4. **`/catalog` показывает 12 из 22** до нажатия кнопки. Постраничность
   клиентская, поисковику видны только первые 12.

### Внутри

5. **Полного списка карточек нет ни в одном эндпоинте.** Инвентаризацию
   пришлось собирать из двух источников, и 15 карточек в неё не попали.
   Починка: служебный список в `/gb-debug`, ~2 часа.
6. **Миграция 019 не проверяется** в `/api/health`, в отличие от 013–018.
   Починка: одна строка проверки, ~15 минут.
7. **Два таймаута на партии** (290 с без ответа) — воспроизводились на
   `GB-CMUMM2` и `GB-RVABF7`, со второй попытки прошли. Причина не
   разобрана.
8. **Порог регрессии на пересборке жёстче, чем на первой сборке**: 4 из 4
   против 10 из 13. Не трогал сознательно, но перекос остаётся.

---

## БЛОК 5. Хвосты и мёртвый код

| что | состояние |
| --- | --- |
| `src/lib/publicRegistry.ts` | удалён, заменён дизайнерским `catalogList.ts` |
| моя временная вёрстка `/catalog` | снята целиком, приехал дизайн GB LONDON 11 |
| `tools/enrich-twice.mjs`, `seed-batch.mjs` | живые, использовались на этой неделе |
| слово «лавка» во внутренних именах | остаётся: `/api/lavka/<slug>.json`, `lavkaSchema.ts` — это машинный контракт, переименование сломает чужие ссылки |
| ветка `claude/seed-token-env-check-yd7sog` | смержена, можно удалять |
| `sql/019_hide_journal.sql` | применена или нет — не знаю, проверки нет |

---

## БЛОК 6. Что нужно от Марселя

1. **Доставка заявок.** Vercel → проект `gb-agent` → Settings →
   Environment Variables → добавить `LEAD_EMAIL` со своим адресом
   (значение — почта, куда слать заявки). Без неё пункт 1 Блока 4 не
   чинится кодом.
2. **Проверить миграцию 019.** Supabase → SQL Editor → прогнать
   `sql/019_hide_journal.sql`, если ещё не прогонялась. Она идемпотентна
   (`if not exists`), повторный прогон безвреден.
3. **Отдать список карточек.** Supabase → SQL Editor → запрос из Блока 1,
   результат в мост — тогда инвентаризация закроется полностью.
4. Кнопок Merge не нужно: незамерженного нет.

---

## БЛОК 7. Готовность к дизайну

### Экраны, которые есть в коде

| экран | URL | кем нарисован |
| --- | --- | --- |
| вход с нуля | `/start` | дизайн, GB LONDON |
| витрина карточки | `/t/<slug>` | дизайн, GB LONDON 10 (`passportMarkup.ts`, генерируется) |
| правка владельцем | `/t/<slug>/edit` | дизайн |
| реестр | `/catalog` | дизайн, GB LONDON 11 |
| телеметрия | `/gb-debug` | **разработка**, служебный, дизайну не отдавался |

### Состояний, которых нет вообще

- **Скрытая карточка.** Логика есть (уходит из площади и поиска), экрана
  нет: страница отдаёт 404 без объяснения. Владельцу, который скрыл своё
  дело и вернулся по ссылке, показывать нечего.
- **Тонкая карточка** — отдельного состояния нет, пустые слоты рисуются
  теми же пробелами, что и у полной.
- **Ошибка сборки** — экрана нет: отказ виден только в ответе API.
- **Загрузка `/catalog`** — состояния нет, страница серверная.

### Данные на экран реестра

`CatalogRow`: `slug`, `title`, `gist`, `city`, `owned`. **Пустыми могут
быть `gist` и `city`** — источник не всегда их даёт; `title` и `slug` есть
всегда. Витрина карточки получает все 12 слотов, из них пустыми могут быть
любые, кроме 1, 5, 11, 12.

### Что сырое и всё равно переделывать

`/gb-debug` — верстался разработкой на скорую руку.

### Что трогать нельзя без переделки логики

- **Плашка посева** «Собрано из открытых источников» — часть контракта
  честности, снимать нельзя.
- **Метка источника ссылкой** — я менял `span` на `a` по прямому
  разрешению; дизайну нужно свериться, а не откатить.
- **Точка происхождения в реестре** (чёрная/серая) — считается тем же
  предикатом, что решает индексацию.
- **`rel="nofollow"`** на строках неподтверждённых карточек — замок от
  индексации, снятие откроет посев поисковику.
