# Конспекты научных статей

Каждый конспект — один файл `<short_id>.md` в этой директории.

## Конвенция YAML-заголовка

Каждый файл начинается с YAML front-matter:

```yaml
---
id: arlitt_1996
authors: "Arlitt M.F., Williamson C.L."
year: 1996
title: "Web Server Workload Characterization: The Search for Invariants"
journal: "ACM SIGMETRICS Performance Evaluation Review"
doi: "10.1145/233008.233034"
core: true
status: done  # done | in_progress | todo
---
```

Поля:

| Поле | Описание |
| --- | --- |
| `id` | Уникальный идентификатор, совпадает с именем файла |
| `authors` | Авторы (строка) |
| `year` | Год публикации |
| `title` | Полное название |
| `journal` | Журнал / конференция |
| `doi` | DOI или URL |
| `core: true` | Статья входит в основной список литературы |
| `status` | Состояние конспекта |

## Структура конспекта

После YAML front-matter:

```markdown
## Основная идея

1–3 предложения о главном вкладе работы.

## Ключевые результаты

– Результат 1
– Результат 2

## Релевантность для диплома

Как эта работа используется в главах 1–3.

## Цитаты для диплома

> «Важная цитата» (с. 127)
```

## Реестр конспектов

| ID | Авторы | Год | Статус | Core |
| --- | --- | --- | --- | --- |
| `arlitt_1996` | Arlitt, Williamson | 1996 | todo | ✓ |
| `bezemer_2019` | Bezemer, Zaidman | 2019 | todo | ✓ |
| `fielding_2000` | Fielding | 2000 | todo | ✓ |
| `gan_2019` | Gan et al. | 2019 | todo | ✓ |
| `halili_2008` | Halili | 2008 | todo | ✓ |
| `heusser_2012` | Heusser, Leitner | 2012 | todo | ✓ |
| `kleinrock_1975` | Kleinrock | 1975 | todo | ✓ |
| `menasce_2000` | Menascé, Almeida | 2000 | todo | ✓ |
| `molyneaux_2009` | Molyneaux | 2009 | todo | ✓ |
| `shkuro_2019` | Shkuro | 2019 | todo | — |
