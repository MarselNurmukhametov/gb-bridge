# Трейсы последнего прогона

Источник: `npm run e2e` — путь сайт → интервью → публикация → чат.
Контакты замаскированы (••• + 4 знака), персональных данных нет.

```
=== ЧАТ КАРТОЧКИ (глазами посетителя) ===
агент: {}
  ✓ агент здоровается первым
Error: ПРОВАЛ: развилка из услуг карточки: []
--- лог приложения ---
   ▲ Next.js 15.5.22
   - Local:        http://localhost:3123
   - Network:      http://192.0.2.2:3123

 ✓ Starting...
 ✓ Ready in 398ms
[site-reader] verstak-mebel.test:8077: фактов 10, на подтверждение 1 · DETERMINISTIC_CONTACTS:3 · IMPLAUSIBLE_PENDING:trust.credentials(гарантия 400 лет > 50)
[perplexity] 403 Host not in allowlist: api.perplexity.ai. Add this host to your network egress settings to allow access.
[site-reader] verstak-mebel.test:8077: фактов 10, на подтверждение 1 · DETERMINISTIC_CONTACTS:3 · IMPLAUSIBLE_PENDING:trust.credentials(гарантия 400 лет > 50)
[perplexity] 403 Host not in allowlist: api.perplexity.ai. Add this host to your network egress settings to allow access.
[site-reader] verstak-mebel.test:8077: фактов 10, на подтверждение 1 · DETERMINISTIC_CONTACTS:3 · IMPLAUSIBLE_PENDING:trust.credentials(гарантия 400 лет > 50)
[perplexity] 403 Host not in allowlist: api.perplexity.ai. Add this host to your network egress settings to allow access.
[site-reader] verstak-mebel.test:8077: фактов 10, на подтверждение 1 · DETERMINISTIC_CONTACTS:3 · IMPLAUSIBLE_PENDING:trust.credentials(гарантия 400 лет > 50)
[perplexity] 403 Host not in allowlist: api.perplexity.ai. Add this host to your network egress settings to allow access.
[pending-fail-closed] Supabase POST facts → 400: {"message":"column facts.pending_reason does not exist"}
```
