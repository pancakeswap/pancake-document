---
description: Grazie per aver espresso il tuo interesse a contribuire a PancakeSwap!
---

# Contribuire

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/developers-header.png)

PancakeSwap è un progetto open-source. Se vuoi contribuire al progetto, questa sezione è qui per guidarti nei tuoi primi passi con il team di PancakeSwap 🥞

Prima di iniziare qualsiasi sviluppo, ti incoraggiamo vivamente a inviare una issue su Github per discutere il problema e la soluzione con il team.

## Configura il tuo ambiente di sviluppo

Installa [yarn](https://classic.yarnpkg.com/lang/en/docs/install/) se non lo hai già.

1.  Fai un fork e clona il [repository](https://github.com/pancakeswap/pancake-frontend)

    ```bash
    $ git clone [fork_repo_url]
    ```
2.  Aggiungi il remote [upstream](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/configuring-a-remote-for-a-fork). Ad esempio:

    ```bash
    $ git remote add upstream git@github.com:pancakeswap/pancake-frontend.git
    ```
3.  Assicurati di avere l'ultima versione del branch predefinito (`develop`)

    ```bash
    $ git checkout develop
    $ git pull upstream develop
    ```
4.  Crea il tuo branch e installa le dipendenze

    ```bash
    $ git checkout -b branch-name
    $ yarn
    ```
5. Buona programmazione 🎉

## Regole di codice

Cerchiamo di mantenere la massima coerenza possibile tra tutti i nostri repository. La tua pull request ha più possibilità di essere accettata se segui le regole seguenti e scrivi codice di alta qualità. **Cominciamo** 💪

### Usa il UIKit

{% hint style="warning" %}
Controlla il [UI Kit](https://github.com/pancakeswap/pancake-frontend/tree/master/packages/uikit) prima di iniziare qualsiasi cosa. Molti componenti sono già stati creati e non vogliamo che tu sprechi tempo a reinventare la ruota 😉
{% endhint %}

Se è necessario creare una variante di un componente, usa il componente corrispondente nel UI Kit come base. Ad esempio:

```javascript
import styled from 'styled-components'
import { Button } from '@pancakeswap/uikit'

const NewButtonVariant = styled(Button)`
  // custom styles here
`
```

### Usa gli strumenti!

La maggior parte dei nostri repo usa [Typescript](https://www.typescriptlang.org/docs), [ESLint](https://eslint.org/docs/user-guide/getting-started) e [Prettier](https://prettier.io). Assicurati di conoscere le best practice di Typescript e di abilitare un plugin ESLint e Prettier per il tuo IDE.

{% hint style="warning" %}
Assicurati che il tuo codice sia formattato con Prettier e privo di errori ESLint prima di inviare una pull request.
{% endhint %}

### Alcune buone pratiche

* Mantieni i componenti il più piccoli e ["dumb"](https://en.wikipedia.org/wiki/Pure_function) possibile.
* Usa la [Composition over Inheritance](https://reactjs.org/docs/composition-vs-inheritance.html).
* Tieni a mente che il tuo codice verrà letto e mantenuto da molti altri sviluppatori. Rendilo il più chiaro e facile da aggiornare possibile._​_

## Creare la tua pull request

Il tuo codice è pronto per essere inviato in revisione, congratulazioni 🥳

* Tutte le pull request **devono** avere una descrizione di ciò che la PR cerca di realizzare.
* Mantieni le pull request **il più piccole possibile**. Le pull request più grandi devono essere suddivise in parti più piccole con un branch base dedicato. Tagga con `epic` le PR che vengono unite nel tuo branch base.
* Se possibile, auto-rivedi la tua PR e **aggiungi commenti** dove è necessaria una spiegazione aggiuntiva.

{% hint style="info" %}
Crea una [draft PR](https://github.blog/2019-02-14-introducing-draft-pull-requests/) il prima possibile così possiamo vedere il tuo progresso in corso.
{% endhint %}

### Titolo della Pull Request

Il titolo delle nostre Pull Request segue i [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) usando [commitlint](https://commitlint.js.org/#/).‌

_Ulteriori dettagli nelle [linee guida di Angular](https://github.com/angular/angular/blob/22b96b9/CONTRIBUTING.md#type)_

| Tipo         | Descrizione                                                                                                    |
| ------------ | -------------------------------------------------------------------------------------------------------------- |
| **build**    | Modifiche che influenzano il sistema di build o le dipendenze esterne (es.: gulp, broccoli, npm)               |
| **ci**       | Modifiche ai file di configurazione CI e agli script (es.: Travis, Circle, BrowserStack, SauceLabs)            |
| **docs**     | Modifiche solo alla documentazione                                                                             |
| **feat**     | Una nuova funzionalità                                                                                         |
| **fix**      | Una correzione di bug                                                                                          |
| **perf**     | Una modifica al codice che migliora le prestazioni                                                             |
| **refactor** | Una modifica al codice che non corregge un bug né aggiunge una funzionalità                                    |
| **style**    | Modifiche che non influenzano il significato del codice (spazi bianchi, formattazione, punto e virgola mancante, ecc.) |
| **test**     | Aggiunta di test mancanti o correzione di test esistenti                                                       |

**Grazie per aiutarci a rendere PancakeSwap ancora più straordinario** ❤
