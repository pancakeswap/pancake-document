---
description: Спасибо за интерес к участию в развитии PancakeSwap!
---

# Участие в разработке

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/developers-header.png)

PancakeSwap — проект с открытым исходным кодом. Если ты хочешь внести вклад в проект, этот раздел поможет тебе сделать первые шаги совместно с командой PancakeSwap 🥞

Прежде чем приступать к разработке, мы настоятельно рекомендуем открыть issue на Github, чтобы обсудить проблему и решение с командой.

## Настройка среды разработки

Установи [yarn](https://classic.yarnpkg.com/lang/en/docs/install/), если он ещё не установлен.

1.  Сделай форк и клонируй [репозиторий](https://github.com/pancakeswap/pancake-frontend)

    ```bash
    $ git clone [fork_repo_url]
    ```
2.  Добавь удалённый репозиторий [upstream](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/configuring-a-remote-for-a-fork). Например:

    ```bash
    $ git remote add upstream git@github.com:pancakeswap/pancake-frontend.git
    ```
3.  Убедись, что у тебя самая последняя версия ветки по умолчанию (`develop`)

    ```bash
    $ git checkout develop
    $ git pull upstream develop
    ```
4.  Создай свою ветку и установи зависимости

    ```bash
    $ git checkout -b branch-name
    $ yarn
    ```
5. Приятного кодинга 🎉

## Правила написания кода

Мы стараемся поддерживать максимальную согласованность между нашими репозиториями. Твой pull request с большей вероятностью будет принят, если ты следуешь приведённым ниже правилам и пишешь код высокого качества. **Начнём** 💪

### Используй UIKit

{% hint style="warning" %}
Перед тем как что-то делать, ознакомься с [UI Kit](https://github.com/pancakeswap/pancake-frontend/tree/master/packages/uikit). Многие компоненты уже созданы, и мы не хотим, чтобы ты тратил время на изобретение велосипеда 😉
{% endhint %}

Если нужно создать вариант компонента, используй соответствующий компонент из UI Kit в качестве основы. Например:

```javascript
import styled from 'styled-components'
import { Button } from '@pancakeswap/uikit'

const NewButtonVariant = styled(Button)`
  // custom styles here
`
```

### Используй инструменты!

В большинстве наших репозиториев используются [Typescript](https://www.typescriptlang.org/docs), [ESLint](https://eslint.org/docs/user-guide/getting-started) и [Prettier](https://prettier.io). Убедись, что ты знаком с лучшими практиками Typescript, и установи плагины ESLint и Prettier для своей IDE.

{% hint style="warning" %}
Перед отправкой pull request убедись, что твой код отформатирован с помощью Prettier и не содержит ошибок ESLint.
{% endhint %}

### Несколько полезных практик

* Делай компоненты как можно меньше и ["тупее"](https://en.wikipedia.org/wiki/Pure_function).
* Используй [Композицию вместо Наследования](https://reactjs.org/docs/composition-vs-inheritance.html).
* Помни, что твой код будет читать и поддерживать несколько других разработчиков. Делай его максимально понятным и лёгким для обновления._​_

## Создание pull request

Твой код готов к проверке, поздравляем 🥳

* Все pull request **обязательно** должны содержать описание того, что PR пытается реализовать.
* Делай pull request **как можно меньше**. Большие pull request следует разбивать на более мелкие части с отдельной базовой веткой. Пожалуйста, помечай PR, которые сливаются в твою базовую ветку, тегом `epic`.
* По возможности самостоятельно проверяй свой PR и **добавляй комментарии** там, где требуются дополнительные пояснения.

{% hint style="info" %}
Создай [черновик PR](https://github.blog/2019-02-14-introducing-draft-pull-requests/) как можно раньше, чтобы мы могли следить за твоим прогрессом.
{% endhint %}

### Заголовок Pull Request

Заголовки Pull Request следуют соглашению [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) с использованием [commitlint](https://commitlint.js.org/#/).‌

_Подробнее в_ [_руководстве Angular_](https://github.com/angular/angular/blob/22b96b9/CONTRIBUTING.md#type)

| Тип          | Описание                                                                                                                   |
| ------------ | -------------------------------------------------------------------------------------------------------------------------- |
| **build**    | Изменения, влияющие на систему сборки или внешние зависимости (примеры: gulp, broccoli, npm)                               |
| **ci**       | Изменения в файлах и скриптах CI-конфигурации (примеры: Travis, Circle, BrowserStack, SauceLabs)                          |
| **docs**     | Изменения только в документации                                                                                            |
| **feat**     | Новая функциональность                                                                                                     |
| **fix**      | Исправление ошибки                                                                                                         |
| **perf**     | Изменение кода, улучшающее производительность                                                                              |
| **refactor** | Изменение кода, которое не исправляет ошибку и не добавляет функциональность                                               |
| **style**    | Изменения, не влияющие на смысл кода (пробелы, форматирование, пропущенные точки с запятой и т. д.)                       |
| **test**     | Добавление отсутствующих тестов или исправление существующих                                                               |

**Спасибо за помощь в том, чтобы сделать PancakeSwap ещё лучше** ❤
