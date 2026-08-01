# Фикстура Metahim · 9 страниц · модель openai (gpt-4o) · живая

Вход зафиксирован в `gb-agent/tests/fixtures/metahim/` — прогон повторяем.

Прогон: 22.2 с · ≈3.18 ₽ · модель gpt-4o

## Целевая сущность (этап 0)
```json
{
 "display_name": "Metahim",
 "legal_name": "LLC METAHIM",
 "domain": "metahim.tech",
 "entity_type": "company",
 "primary_topics": [
  "AI in drug discovery",
  "pharmaceutical research",
  "personalized medicine",
  "gene editing",
  "biotech innovations"
 ],
 "business_modes": [
  "услуги",
  "консалтинг"
 ],
 "country": "Russia",
 "site_lang": "en"
}
```

## Мерила приёмки

| мерило | обязано | вышло |
|---|---|---|
| unsupported claims | 0 | **0** |
| template contamination | 0 | **0** |
| wrong entity | 0 | **0** |
| placeholder values | 0 | **0** |

## Что в карточке

- **identity.display_name** — Metahim (LLC METAHIM)
  откуда: https://metahim.tech/ · «Metahim (LLC METAHIM)»
- **offer.services** — Metahim использует искусственный интеллект и машинное обучение для ускорения открытия и разработки лекарств.
  откуда: https://metahim.tech/ · «We use Artificial Intelligence and Machine Learning to empower scientists to pursue their »
- **offer.services** — Metahim предлагает услуги по интеграции ИИ с коммерческими системами обработки данных.
  откуда: https://metahim.tech/our-services · «Personalized AI integration with commercial supercomputing data processing systems»
- **offer.services** — Metahim предлагает услуги по выбору исследовательских лабораторий и поставке сырья и оборудования для лабораторных исследований.
  откуда: https://metahim.tech/our-services · «Selection of research laboratories; Provision and supply of raw materials and equipment fo»
- **offer.services** — Metahim предлагает услуги по выбору платформ ИИ, соответствующих целям исследований.
  откуда: https://metahim.tech/our-services · «Selection of AI platforms aligned with research objectives»
- **offer.services** — Metahim предлагает анализ данных DeepMind.
  откуда: https://metahim.tech/our-services · «DeepMind data analysis»
- **contacts.channel** — Телефон: 4951377400
  откуда: https://metahim.tech/contact-us · «Phone number 4951377400»
- **contacts.channel** — Почта: info@metahim.tech
  откуда: https://metahim.tech/contact-us · «E-mail info@metahim.tech»
- **contacts.channel** — Адрес: здание 25, улица Шлякова, помещение 12, Сергиев Посад, Московская область, 141302, Россия.
  откуда: https://metahim.tech/contact-us · «Company address Building 25, Shlyakova street, room 12, Sergiev Posad, Moscow region, 1413»

Страницы по ролям: 9 из 9 · режимы дела: услуги, консалтинг
Инспекции: TRANSLATED:2 · IRRELEVANT_DROPPED:1(мед-шаблон)

## Контракт факта (образец записи)
```json
{
 "key": "identity.display_name",
 "resolved_value": "Metahim (LLC METAHIM)",
 "assertions": [
  {
   "value": "Metahim (LLC METAHIM)",
   "source_type": "website",
   "source_ref": "https://metahim.tech/",
   "evidence": "Metahim (LLC METAHIM)"
  }
 ],
 "owner_review_status": "unreviewed",
 "verification_status": "source_supported",
 "resolution": "auto_selected",
 "publication_status": "draft"
}
```

ИТОГ: все четыре мерила — нули. Фикстура зелёная.
