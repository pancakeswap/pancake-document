---
description: Merci de l'intérêt que vous portez à la contribution à PancakeSwap !
---

# Contribution

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/developers-header.png)

PancakeSwap est un projet open source. Si vous souhaitez contribuer au projet, cette section est là pour vous guider dans vos premiers pas avec l'équipe PancakeSwap 🥞

Avant de commencer tout développement, nous vous encourageons vivement à soumettre une issue sur Github afin de discuter du problème et de la solution avec l'équipe.

## Configurer votre environnement de développement

Installez [yarn](https://classic.yarnpkg.com/lang/en/docs/install/) si ce n'est pas déjà fait.

1.  Forkez et clonez le [dépôt](https://github.com/pancakeswap/pancake-frontend)

    ```bash
    $ git clone [fork_repo_url]
    ```
2.  Ajoutez le remote [upstream](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/configuring-a-remote-for-a-fork). Par exemple :

    ```bash
    $ git remote add upstream git@github.com:pancakeswap/pancake-frontend.git
    ```
3.  Assurez-vous d'avoir la dernière version de la branche par défaut ( `develop` )

    ```bash
    $ git checkout develop
    $ git pull upstream develop
    ```
4.  Créez votre propre branche et installez les dépendances

    ```bash
    $ git checkout -b branch-name
    $ yarn
    ```
5. Bon codage 🎉

## Règles de codage

Nous cherchons à maintenir autant de cohérence que possible entre nos dépôts. Votre pull request aura plus de chances d'être acceptée si vous respectez les règles suivantes et écrivez du code de qualité. **C'est parti** 💪

### Utiliser le UIKit

{% hint style="warning" %}
Consultez le [UI Kit](https://github.com/pancakeswap/pancake-frontend/tree/master/packages/uikit) avant de commencer quoi que ce soit. De nombreux composants sont déjà créés, et nous ne souhaitons pas que vous perdiez du temps à réinventer la roue 😉
{% endhint %}

Si une variante d'un composant doit être créée, utilisez le composant correspondant du UI Kit comme base. Par exemple :

```javascript
import styled from 'styled-components'
import { Button } from '@pancakeswap/uikit'

const NewButtonVariant = styled(Button)`
  // custom styles here
`
```

### Utilisez les outils !

La plupart de nos dépôts utilisent [Typescript](https://www.typescriptlang.org/docs), [ESLint](https://eslint.org/docs/user-guide/getting-started) et [Prettier](https://prettier.io). Assurez-vous de bien connaître les bonnes pratiques Typescript et activez un plugin ESLint et Prettier pour votre IDE.

{% hint style="warning" %}
Assurez-vous que votre code est formaté avec Prettier et ne contient aucune erreur ESLint avant de soumettre une pull request.
{% endhint %}

### Quelques bonnes pratiques

* Gardez les composants aussi petits et [« purs »](https://en.wikipedia.org/wiki/Pure_function) que possible.
* Utilisez la [composition plutôt que l'héritage](https://reactjs.org/docs/composition-vs-inheritance.html).
* Gardez à l'esprit que votre code sera lu et maintenu par plusieurs autres développeurs. Rendez-le aussi clair et facile à mettre à jour que possible._​_

## Créer votre pull request

Votre code est prêt à être soumis pour révision, félicitations 🥳

* Toutes les pull requests **doivent** contenir une description de ce que la PR cherche à accomplir.
* Gardez les pull requests **aussi petites que possible**. Les pull requests de grande taille doivent être découpées en parties plus petites avec une branche de base dédiée. Merci de taguer les PRs qui fusionnent dans votre branche de base avec le tag `epic`.
* Si possible, auto-révisez votre PR et **ajoutez des commentaires** là où des clarifications supplémentaires sont nécessaires.

{% hint style="info" %}
Créez une [PR en mode brouillon](https://github.blog/2019-02-14-introducing-draft-pull-requests/) dès que possible afin que nous puissions suivre votre progression.
{% endhint %}

### Titre de la Pull Request

Nos titres de Pull Request suivent les [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) en utilisant [commitlint](https://commitlint.js.org/#/).‌

_Plus d'informations dans_ [_les directives d'Angular_](https://github.com/angular/angular/blob/22b96b9/CONTRIBUTING.md#type)

| Type         | Description                                                                                                         |
| ------------ | ------------------------------------------------------------------------------------------------------------------- |
| **build**    | Modifications affectant le système de build ou les dépendances externes (exemples : gulp, broccoli, npm)            |
| **ci**       | Modifications des fichiers de configuration et scripts CI (exemples : Travis, Circle, BrowserStack, SauceLabs)     |
| **docs**     | Modifications de la documentation uniquement                                                                        |
| **feat**     | Une nouvelle fonctionnalité                                                                                         |
| **fix**      | Une correction de bug                                                                                               |
| **perf**     | Une modification du code améliorant les performances                                                                |
| **refactor** | Une modification du code qui ne corrige pas un bug ni n'ajoute de fonctionnalité                                    |
| **style**    | Modifications n'affectant pas la signification du code (espaces blancs, formatage, points-virgules manquants, etc.) |
| **test**     | Ajout de tests manquants ou correction de tests existants                                                           |

**Merci de nous aider à rendre PancakeSwap encore plus formidable** ❤
