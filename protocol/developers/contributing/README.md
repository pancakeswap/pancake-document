---
description: Vielen Dank für Ihr Interesse, zu PancakeSwap beizutragen!
---

# Beitragen

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/developers-header.png)

PancakeSwap ist ein Open-Source-Projekt. Wenn Sie zum Projekt beitragen möchten, finden Sie in diesem Abschnitt eine Anleitung für Ihre ersten Schritte mit dem PancakeSwap-Team 🥞

Bevor Sie mit der Entwicklung beginnen, empfehlen wir Ihnen dringend, ein Issue auf Github einzureichen, um das Problem und die Lösung mit dem Team zu besprechen.

## Ihre Entwicklungsumgebung einrichten

Installieren Sie [yarn](https://classic.yarnpkg.com/lang/en/docs/install/), falls noch nicht geschehen.

1.  Forken und klonen Sie das [Repository](https://github.com/pancakeswap/pancake-frontend)

    ```bash
    $ git clone [fork_repo_url]
    ```
2.  Fügen Sie [upstream](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/configuring-a-remote-for-a-fork) als Remote hinzu. Zum Beispiel:

    ```bash
    $ git remote add upstream git@github.com:pancakeswap/pancake-frontend.git
    ```
3.  Stellen Sie sicher, dass Sie die neueste Version des Standard-Branches ( `develop` ) haben

    ```bash
    $ git checkout develop
    $ git pull upstream develop
    ```
4.  Erstellen Sie Ihren eigenen Branch und installieren Sie die Abhängigkeiten

    ```bash
    $ git checkout -b branch-name
    $ yarn
    ```
5. Viel Spaß beim Programmieren 🎉

## Programmierrichtlinien

Wir versuchen, zwischen allen unseren Repositories so viel Konsistenz wie möglich aufrechtzuerhalten. Ihr Pull Request hat bessere Chancen, akzeptiert zu werden, wenn Sie die folgenden Regeln befolgen und hochwertigen Code schreiben. **Legen wir los** 💪

### Das UIKit verwenden

{% hint style="warning" %}
Sehen Sie sich das [UI Kit](https://github.com/pancakeswap/pancake-frontend/tree/master/packages/uikit) an, bevor Sie anfangen. Viele Komponenten sind bereits erstellt, und wir möchten nicht, dass Sie Zeit damit verschwenden, das Rad neu zu erfinden 😉
{% endhint %}

Wenn eine Variante einer Komponente erstellt werden muss, verwenden Sie die entsprechende Komponente im UI Kit als Basis. Zum Beispiel:

```javascript
import styled from 'styled-components'
import { Button } from '@pancakeswap/uikit'

const NewButtonVariant = styled(Button)`
  // custom styles here
`
```

### Die Tools nutzen!

Die meisten unserer Repos verwenden [Typescript](https://www.typescriptlang.org/docs), [ESLint](https://eslint.org/docs/user-guide/getting-started) und [Prettier](https://prettier.io). Stellen Sie sicher, dass Sie mit den Best Practices von Typescript vertraut sind, und aktivieren Sie ein ESLint- und Prettier-Plugin für Ihre IDE.

{% hint style="warning" %}
Stellen Sie sicher, dass Ihr Code mit Prettier formatiert ist und keine ESLint-Fehler enthält, bevor Sie einen Pull Request einreichen.
{% endhint %}

### Einige gute Praktiken

* Halten Sie Komponenten so klein und ["rein"](https://en.wikipedia.org/wiki/Pure_function) wie möglich.
* Verwenden Sie [Komposition statt Vererbung](https://reactjs.org/docs/composition-vs-inheritance.html).
* Bedenken Sie, dass Ihr Code von mehreren anderen Entwicklern gelesen und gepflegt wird. Machen Sie ihn so klar und leicht zu aktualisieren wie möglich.

## Ihren Pull Request erstellen

Ihr Code ist bereit zur Überprüfung eingereicht zu werden, herzlichen Glückwunsch 🥳

* Alle Pull Requests **müssen** eine Beschreibung dessen enthalten, was der PR zu erreichen versucht.
* Halten Sie Pull Requests **so klein wie möglich**. Größere Pull Requests sollten in kleinere Teile mit einem dedizierten Basis-Branch aufgeteilt werden. Bitte versehen Sie die PRs, die in Ihren Basis-Branch gemergt werden, mit dem `epic`-Tag.
* Wenn möglich, überprüfen Sie Ihren PR selbst und **fügen Sie Kommentare** hinzu, wo zusätzliche Erklärungen erforderlich sind.

{% hint style="info" %}
Erstellen Sie so früh wie möglich einen [Draft PR](https://github.blog/2019-02-14-introducing-draft-pull-requests/), damit wir Ihren Fortschritt verfolgen können.
{% endhint %}

### Titel des Pull Requests

Unsere Pull-Request-Titel folgen [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) unter Verwendung von [commitlint](https://commitlint.js.org/#/).‌

_Mehr dazu in_ [_Angulars Richtlinien_](https://github.com/angular/angular/blob/22b96b9/CONTRIBUTING.md#type)

| Typ          | Beschreibung                                                                                                        |
| ------------ | ------------------------------------------------------------------------------------------------------------------- |
| **build**    | Änderungen, die das Build-System oder externe Abhängigkeiten betreffen (Beispiel-Scopes: gulp, broccoli, npm)       |
| **ci**       | Änderungen an CI-Konfigurationsdateien und -skripts (Beispiel-Scopes: Travis, Circle, BrowserStack, SauceLabs)     |
| **docs**     | Nur Dokumentationsänderungen                                                                                        |
| **feat**     | Ein neues Feature                                                                                                   |
| **fix**      | Eine Fehlerbehebung                                                                                                 |
| **perf**     | Eine Code-Änderung, die die Performance verbessert                                                                  |
| **refactor** | Eine Code-Änderung, die weder einen Fehler behebt noch ein Feature hinzufügt                                        |
| **style**    | Änderungen, die die Bedeutung des Codes nicht beeinflussen (Leerzeichen, Formatierung, fehlende Semikolons, etc.)   |
| **test**     | Fehlende Tests hinzufügen oder bestehende Tests korrigieren                                                         |

**Vielen Dank, dass Sie dabei helfen, PancakeSwap noch großartiger zu machen** ❤
