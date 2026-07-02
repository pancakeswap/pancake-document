---
description: Obrigado por manifestar interesse em contribuir com o PancakeSwap!
---

# Contribuindo

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/developers-header.png)

O PancakeSwap é um projeto de código aberto. Se você quiser contribuir com o projeto, esta seção está aqui para guiá-lo nos primeiros passos com a equipe do PancakeSwap 🥞

Antes de iniciar qualquer desenvolvimento, recomendamos fortemente que você envie uma issue no Github para discutir o problema e a solução com a equipe.

## Configure seu ambiente de desenvolvimento

Instale o [yarn](https://classic.yarnpkg.com/lang/en/docs/install/) se ainda não tiver instalado.

1.  Faça um fork e clone o [repositório](https://github.com/pancakeswap/pancake-frontend)

    ```bash
    $ git clone [fork_repo_url]
    ```
2.  Adicione o remote [upstream](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/configuring-a-remote-for-a-fork). Por exemplo:

    ```bash
    $ git remote add upstream git@github.com:pancakeswap/pancake-frontend.git
    ```
3.  Certifique-se de ter a versão mais recente do branch padrão ( `develop` )

    ```bash
    $ git checkout develop
    $ git pull upstream develop
    ```
4.  Crie seu próprio branch e instale as dependências

    ```bash
    $ git checkout -b nome-do-branch
    $ yarn
    ```
5. Bom desenvolvimento 🎉

## Regras de codificação

Buscamos manter o máximo de consistência possível entre cada um de nossos repositórios. Seu pull request terá mais chances de ser aceito se você seguir as regras abaixo e escrever código de alta qualidade. **Vamos começar** 💪

### Use o UIKit

{% hint style="warning" %}
Verifique o [UI Kit](https://github.com/pancakeswap/pancake-frontend/tree/master/packages/uikit) antes de começar qualquer coisa. Muitos componentes já estão criados, e não queremos que você perca tempo reinventando a roda 😉
{% endhint %}

Se uma variante de um componente precisar ser criada, use o componente correspondente no UI Kit como base. Por exemplo:

```javascript
import styled from 'styled-components'
import { Button } from '@pancakeswap/uikit'

const NewButtonVariant = styled(Button)`
  // custom styles here
`
```

### Use as ferramentas!

A maioria dos nossos repositórios usa [Typescript](https://www.typescriptlang.org/docs), [ESLint](https://eslint.org/docs/user-guide/getting-started) e [Prettier](https://prettier.io). Certifique-se de estar familiarizado com as boas práticas do Typescript e habilite um plugin de ESLint e Prettier na sua IDE.

{% hint style="warning" %}
Certifique-se de que seu código está formatado com Prettier e sem erros de ESLint antes de enviar um pull request.
{% endhint %}

### Algumas boas práticas

* Mantenha os componentes o menores e mais ["puros"](https://en.wikipedia.org/wiki/Pure_function) possível.
* Use [Composição em vez de Herança](https://reactjs.org/docs/composition-vs-inheritance.html).
* Lembre-se de que seu código será lido e mantido por vários outros desenvolvedores. Torne-o o mais claro e fácil de atualizar possível._​_

## Criando seu pull request

Seu código está pronto para ser enviado para revisão, parabéns 🥳

* Todos os pull requests **devem** ter uma descrição do que o PR está tentando realizar.
* Mantenha os pull requests **o menores possível**. Pull requests maiores devem ser divididos em partes menores com um branch base dedicado. Por favor, marque os PRs que estão sendo mesclados no seu branch base com a tag `epic`.
* Se possível, faça uma auto-revisão do seu PR e **adicione comentários** onde for necessária uma esclarecimento adicional.

{% hint style="info" %}
Crie um [draft PR](https://github.blog/2019-02-14-introducing-draft-pull-requests/) o mais cedo possível para que possamos acompanhar seu progresso.
{% endhint %}

### Título do Pull Request

Nossos Títulos de Pull Request seguem o [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) usando [commitlint](https://commitlint.js.org/#/).‌

_Mais em_ [_Diretrizes do Angular_](https://github.com/angular/angular/blob/22b96b9/CONTRIBUTING.md#type)

| Tipo         | Descrição                                                                                                      |
| ------------ | -------------------------------------------------------------------------------------------------------------- |
| **build**    | Mudanças que afetam o sistema de build ou dependências externas (exemplos de escopos: gulp, broccoli, npm)     |
| **ci**       | Mudanças em arquivos e scripts de configuração de CI (exemplos de escopos: Travis, Circle, BrowserStack, SauceLabs) |
| **docs**     | Mudanças somente na documentação                                                                               |
| **feat**     | Uma nova funcionalidade                                                                                        |
| **fix**      | Uma correção de bug                                                                                            |
| **perf**     | Uma mudança de código que melhora o desempenho                                                                 |
| **refactor** | Uma mudança de código que não corrige um bug nem adiciona uma funcionalidade                                   |
| **style**    | Mudanças que não afetam o significado do código (espaços em branco, formatação, ponto e vírgula ausente, etc)  |
| **test**     | Adição de testes ausentes ou correção de testes existentes                                                     |

**Obrigado por nos ajudar a tornar o PancakeSwap ainda mais incrível** ❤
