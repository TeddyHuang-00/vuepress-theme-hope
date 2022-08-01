---
title: Поддержка каналов
icon: rss
category:
  - Продвинутые
tag:
  - Продвинутые
  - Канал
---

Тема добавляет поддержку каналов с помощью [`vuepress-plugin-feed2`][feed2].

::: info

`vuepress-theme-hope` предоставляет `plugins.feed` в параметрах темы для `vuepress-plugin-feed2`.

:::

<!-- more -->

## Включить вывод ленты

Плагин `vuepress-plugin-feed2` может генерировать для вас файлы каналов в следующих трех форматах:

- Atom 1.0
- JSON 1.1
- RSS 2.0

::: tip

Atom и JSON предназначены для улучшения адаптации программного обеспечения для фидов.

Пожалуйста, используйте RSS, если это возможно.

:::

Пожалуйста, установите для `plugins.feed.atom`, `plugins.feed.json` или `plugins.feed.rss` значение `true` в параметрах темы в соответствии с форматом, который вы хотите сгенерировать.

::: tip

Конечно, вы можете включить их все. Это не выбор 1 из 3 ситуаций.

:::

Учитывая, что сейчас мало кто придерживается фида, этот плагин предоставляет минимальную настройку для настройки автоматического создания подробных файлов фида. Также это позволяет вам свободно определять выходное содержимое канала.

## Настройки канала

Вы можете настроить информацию канала подачи, установив `plugins.feed.channel` в параметрах темы.

Мы рекомендуем следующие настройки:

- Преобразуйте дату создания фида в ISOString и запишите ее в `channel.pubDate`
- Период обновления контента, установленный в `channel.ttl` (единица измерения: минуты)
- Установите информацию об авторских правах через `channel.copyright` или откатитесь к `copyright` в настройках темы
- Установите автора канала через `channel.author` или вернитесь к `author` в настройках темы

::: tip Настройки канала по умолчанию

- Название и описание канала это название и описание сайта по умолчанию

- Ссылка на канал и время последнего обновления будут автоматически сгенерированы плагином.

:::

Подробные параметры и их значения по умолчанию смотрите в разделе [Конфигурация канала подачи][feed2-channel]

## Управление генерацией

### Генерация по умолчанию

По умолчанию все статьи добавляются в ленту новостей.

Содержимое, читаемое по умолчанию, смотрите в разделе [Конфигурация → Управление элементами][feed2-item]

### Настроить элемент фида

Вы можете управлять тем, как создается элемент фида в конкретной статье, настроив параметр `feed` в frontmatter.

Подробные параметры и их значения по умолчанию смотрите в разделе [Конфигурация → Настройки проекта][feed2-item].

### Настроить генерацию ленты

Вы можете получить полный контроль над генерацией элементов фида, настроив `plugins.feed.getter`.

Подробные параметры и их значения по умолчанию смотрите в разделе [Конфигурация → Геттер фидов][feed2-getter].

### Конфигурация I18n

Плагин генерирует отдельные каналы для каждого языка.

Вы можете указать разные настройки для разных языков через `plugins.feed.locales`.

[feed2]: https://vuepress-theme-hope.github.io/v2/feed/
[feed2-channel]: https://vuepress-theme-hope.github.io/v2/feed/config/channel.html
[feed2-item]: https://vuepress-theme-hope.github.io/v2/feed/config/item.html
[feed2-getter]: https://vuepress-theme-hope.github.io/v2/feed/config/getter.html