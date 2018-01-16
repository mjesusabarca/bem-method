# Предсобранный вариант поставки (dist) библиотеки bem-components. Быстрый старт

* [Описание урока](#Описание-урока)
* [Подключение библиотеки в проект](#Подключение-библиотеки-в-проект)
* [Работа с блоками](#Работа-с-блоками)
* [Результат](#Результат)

## Описание урока

Один из вариантов поставки (dist) библиотеки [bem-components](https://ru.bem.info/platform/libs/bem-components/6.0.0/) — это предварительно собранные файлы ([бандлы](https://ru.bem.info/methodology/build/#Введение)), которые подключаются ссылками в HTML страницы и не требуют совместимости с проектом. Это самый быстрый способ попробовать [блоки](https://ru.bem.info/methodology/key-concepts/#Блок) библиотеки в действии.

> **Важно!** Предсобранные файлы библиотеки не позволяют пользоваться всеми преимуществами БЭМ-библиотек: [уровнями переопределения](../../../method/key-concepts/key-concepts.ru.md#Уровень-переопределения), [миксами](../../../method/key-concepts/key-concepts.ru.md#Микс) и возможностью [точечной сборки проекта](../../../method/build/build.ru.md#Определение-списка-БЭМ-сущностей). Для максимально эффективного использования библиотеки, воспользуйтесь поставками [source или compiled](https://ru.bem.info/platform/libs/bem-components/6.0.0/#source-compiled).

В этом уроке **вы научитесь:**
* [Подключать библиотеку в проект](#Подключение-библиотеки-в-проект)
* [Использовать блоки из библиотеки](#Работа-с-блоками)

В результате вы получите форму приветствия с полем ввода и кнопкой, как показано на рисунке ниже. Имя пользователя при нажатии на кнопку отобразится в приветствии.

![Страница приветствия](https://cdn.rawgit.com/bem-site/bem-method/bem-info-data/articles/quick-start-static/quick-start-static__hello-user.svg)

Для работы с примерами, описанными в документе, необходимы:

* базовые навыки
  * HTML
  * CSS
  * JavaScript
  * БЭМ

* понимание технологий БЭМ
  * [i-bem.js](https://ru.bem.info/platform/i-bem/)
  * [BEMHTML](https://ru.bem.info/platform/bem-xjst/8/)

### Как выполнить урок

Есть два способа выполнить этот урок: вы можете писать код прямо в браузере или использовать любую среду веб-разработки, которая позволяет редактировать и запускать код, написанный на HTML, JavaScript и CSS. Например, в [JSFiddle](https://jsfiddle.net).

> Все примеры выполнены в JSFiddle.

## Подключение библиотеки в проект

Существует [несколько способов](https://ru.bem.info/platform/libs/bem-components/6.0.0/#Подключение-предсобранных-файлов-библиотеки-dist) получить предсобранные бандлы библиотеки. В документе рассмотрен способ подключения файлов с CDN:

Схема подключения файла с CDN: `//yastatic.net/название-библиотеки/версия/платформа/имя-файла`.

> Полный список [предсобранных бандлов библиотеки bem-components](https://tech.yandex.ru/jslibs/).

Чтобы подключить библиотеку в проект:
* Добавьте элементы `<link>` и `<script>` в HTML страницы.
* Укажите путь к бандлу со стилями в элементе `<link>`: `https://yastatic.net/bem-components/latest/desktop/bem-components.css`.
* Укажите путь к бандлу с JavaScript-реализацией блоков в элементе `<script>`: `https://yastatic.net/bem-components/latest/desktop/bem-components.no-autoinit.js`.

> **Важно!** Чтобы добавлять блокам собственный код на [i-bem.js](https://ru.bem.info/platform/i-bem/), используйте бандлы **без автоинициализации**.

HTML-разметка страницы с подключенной библиотекой bem-components:

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>bem-components as a library</title>
    <link rel="stylesheet" href="https://yastatic.net/bem-components/latest/desktop/bem-components.css">
    <script src="https://yastatic.net/bem-components/latest/desktop/bem-components.no-autoinit.js"></script>
</head>
</html>
```

Дополнительно подключать на страницу предсобранные бандлы библиотеки `bem-core` не нужно, они уже включены в сборку.

## Работа с блоками

Чтобы добавить блок на страницу, необходимо:

1. **Выбрать блок**

  Зайдите в описание блока на [сайте библиотеки](https://ru.bem.info/platform/libs/bem-components/6.0.0/) и выберите подходящий пример:
  * [input](https://ru.bem.info/platform/libs/bem-components/6.0.0/touch-phone/input/#Модификатор-type-10)
  * [button](https://ru.bem.info/platform/libs/bem-components/6.0.0/touch-phone/button/#Кнопка-отправки-формы-модификатор-type-в-значении-submit-1)

2. **Получить HTML-разметку выбранного блока**

  Используйте пример из документации, чтобы получить HTML любым из перечисленных способов:
  * [Использовать готовый HTML](#Использование-готового-html)
  * [Генерировать HTML в браузере](#Генерация-html-в-браузере)&#032;&#032;
  > **Важно!** [HTML можно генерировать на сервере](https://github.com/bem/bem-components/blob/v6/README.ru.md#Работа-с-библиотекой-в-виде-dist), но это выходит за рамки данного урока.

### Использование готового HTML

Чтобы работать с готовым HTML-кодом блока, [подключите](##Подключение-библиотеки-в-проект) бандлы с JavaScript-реализацией блока: `https://yastatic.net/bem-components/latest/desktop/bem-components.no-autoinit.js`.

Чтобы получить готовую HTML-разметку блока, перейдите во вкладку `HTML` в примере этого блока:

![Вкладка HTML для примера блока input](https://cdn.rawgit.com/bem-site/bem-method/dist/platform/tutorials/dist-quick-start/dist-quick-start-html.png)

Скопируйте код и вставьте на страницу.

HTML-разметка страницы будет выглядеть следующим образом:

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>bem-components as a library</title>
    <link rel="stylesheet" href="https://yastatic.net/bem-components/latest/desktop/bem-components.css">
    <script src="https://yastatic.net/bem-components/latest/desktop/bem-components.no-autoinit.js"></script>
</head>
<body>
    <!-- Блок hello для создания формы приветствия -->
    <form class="hello i-bem" data-bem='{ "hello": {} }'>
        <div class="hello__greeting">Hello, %user name%!</div>
        <!-- HTML-код для блока input -->
        <span class="input input_theme_islands input_size_m i-bem" data-bem='{"input":{}}'>
            <span class="input__box">
                <input class="input__control" placeholder="User name" autocomplete="off" autocorrect="off" autocapitalize="off" spellcheck="false">
            </span>
        </span>
        <!-- HTML-код для блока button -->
        <button class="button button_theme_islands button_size_m button_type_submit button__control i-bem" data-bem='{"button":{}}' role="button" type="submit">
            <span class="button__text">Click</span>
        </button>
    </form>
</body>
</html>
```

> При обновлении шаблонов в библиотеке потребуется вручную вносить изменения в каждый обновленный блок.

Блоки `input` и `button` отобразились [на странице](https://jsfiddle.net/inna__neige/0hLmLmzn/6/). Чтобы имя из поля ввода появлялось в приветствии, опишите поведение блоков:

> **Важно!** Hеобходимо явно вызвать `init();`, если требуется инициализировать блоки, заранее присутствующие в HTML-разметке.

```javascript
modules.define('hello', ['i-bem-dom', 'input', 'button'],
    function(provide, bemDom, Input, Button) {

    provide(bemDom.declBlock('hello', {
        onSetMod: {
            js: {
                inited: function() {
                    this._input = this.findChildBlock(Input);
                }
            }
        },

        _onSubmit: function(e) {
            e.preventDefault();
            this._elem('greeting').domElem.text('Hello, ' + this._input.getVal() + '!');
        }
    }, {
        lazyInit: true,
        onInit: function() {
            this._domEvents().on('submit', this.prototype._onSubmit);
        }
    }));

});
// Вызов `init();`
modules.require('i-bem-dom__init', function(init) { init(); });
```

Проект в [JSFiddle](https://jsfiddle.net/inna__neige/0hLmLmzn/).

### Генерация HTML в браузере

Чтобы генерировать HTML-разметку блока в браузере, используйте шаблонизатор [BEMHTML](https://ru.bem.info/platform/bem-xjst/8/), который преобразует BEMJSON в HTML. Для этого [подключите](##Подключение-библиотеки-в-проект) бандлы, которые содержат код шаблонизатора: `https://yastatic.net/bem-components/latest/desktop/bem-components.no-autoinit.js+bemhtml.js`.

> Подробнее о [BEMJSON-формате](https://ru.bem.info/platform/bemjson/) входных данных.

Чтобы получить `BEMJSON`-код блока, перейдите во вкладку `BEMJSON` в примере этого блока:

![Вкладка BEMJSON для примера блока input](https://cdn.rawgit.com/bem-site/bem-method/dist/platform/tutorials/dist-quick-start/dist-quick-start-bemjson.png)

Скопируйте код и вставьте на страницу.

HTML-разметка страницы будет выглядеть следующим образом:

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>bem-components as a library</title>
    <link rel="stylesheet" href="https://yastatic.net/bem-components/latest/desktop/bem-components.css">
    <script src="https://yastatic.net/bem-components/latest/desktop/bem-components.no-autoinit.js+bemhtml.js"></script>
</head>
<body class="page page_theme_islands">
    <!-- Блок hello для создания формы приветствия -->
    <form class="hello i-bem" data-bem='{ "hello": {} }'>
        <div class="hello__greeting">Hello, %user name%!</div>
    </form>
</body>
</html>
```

Блоки `input` и `button` появятся на странице в результате выполнения скрипта с шаблоном:

```javascript
modules.define('hello', ['i-bem-dom', 'BEMHTML', 'input', 'button'],
    function(provide, bemDom, BEMHTML, Input, Button) {

    provide(bemDom.declBlock('hello', {
        onSetMod: {
            js: {
                inited: function() {
                    bemDom.append(this.domElem, BEMHTML.apply([ // Выполнение шаблона
                        {
                            block: 'input',
                            mods: {
                                theme: 'islands',
                                size: 'm'
                            },
                            placeholder: 'User name'
                        },
                        {
                            block: 'button',
                            mods: {
                                theme: 'islands',
                                size: 'm',
                                type: 'submit'
                            },
                            text: 'Say hello'
                        }
                    ]));

                    this._input = this.findChildBlock(Input);
                }
            }
        },

        _onSubmit: function(e) {
            e.preventDefault();
            this._elem('greeting').domElem.text('Hello, ' + this._input.getVal() + '!');
        }
    }, {
        onInit: function() {
            this._domEvents().on('submit', this.prototype._onSubmit);
        }
    }));
});

// Вызов `init();`
modules.require('i-bem-dom__init', function(init) { init(); });
```

> Такой код не потребует изменений шаблонах при обновлении библиотеки до новой версии. Однако генерируемая в браузере разметка может хуже индексироваться поисковыми системами.

Проект в [JSFiddle](https://jsfiddle.net/inna__neige/df6uuw7u/).

## Результат

Форма приветствия готова. Чтобы она выглядела, как на рисунке в начале документа, добавьте блокам новые [стили](https://gist.github.com/innabelaya/dacca124dc486e7a3b0854752d9013e7).

**Не получилось?**

Если при создании формы возникли сложности, поищите решение на [форуме](https://ru.bem.info/forum/). Если готового ответа не нашлось, создайте пост со своим вопросом.
