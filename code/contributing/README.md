---
description: Obrigado por expressar seu interesse em contribuir com a PancakeSwap!
---

# Contribuindo

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/developers-header.png)

PancakeSwap é um projeto de código aberto. Se você deseja contribuir com o projeto, esta seção está aqui para guiá-lo em seus primeiros passos com a equipe da PancakeSwap 🥞&#x20;

Antes de iniciar qualquer desenvolvimento, recomendamos que você envie um "issue" no Github para discutir o problema e a solução com a equipe.

## Configure seu ambiente de desenvolvimento

Instale [yarn](https://classic.yarnpkg.com/lang/en/docs/install/) se você não tem.

1.  Faça o Fork e clone o [repositório](https://github.com/pancakeswap/pancake-frontend)

    ```bash
    $ git clone [fork_repo_url]
    ```
2.  Adicione [upstream](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/configuring-a-remote-for-a-fork) remote. Por exemplo,

    ```bash
    $ git remote add upstream git@github.com:pancakeswap/pancake-frontend.git
    ```
3.  Certifique-se de ter a versão mais recente do branch padrão (`develop` )

    ```bash
    $ git checkout develop
    $ git pull upstream develop
    ```
4.  Crie seu próprio branch e instale as dependências

    ```bash
    $ git checkout -b branch-name
    $ yarn
    ```
5. Feliz Programação 🎉

## Regras de Código

Tentamos manter o máximo de consistência possível entre cada um de nossos repositórios. Sua solicitação pull tem mais chances de ser aceita se você seguir as regras a seguir e escrever um código de alta qualidade. **Vamos começar** 💪

### Use os UIKit

{% hint style="warning" %}
Cheque o [UI Kit](https://github.com/pancakeswap/pancake-frontend/tree/master/packages/uikit) antes de começar a fazer alguma coisa. Um monte de componentes já foram criados, e não queremos que você perca tempo reinventando a roda 😉
{% endhint %}

Se for necessário criar uma variante de um componente, use o componente correspondente no UI Kit como base. Por exemplo:

```javascript
import styled from 'styled-components'
import { Button } from '@pancakeswap/uikit'

const NewButtonVariant = styled(Button)`
  // custom styles here
`
```

### Use as tools!

A maioria de nossos repositórios usam [Typescript](https://www.typescriptlang.org/docs), [ESLint](https://eslint.org/docs/user-guide/getting-started), e [Prettier](https://prettier.io). Certifique-se de estar familiarizado com as melhores práticas de Typescript e habilite o plugin ESLint e Prettier na sua IDE.

{% hint style="warning" %}
Certifique-se de que seu código esteja formatado com Prettier e livre de qualquer erro ESLint antes de enviar um pull request.
{% endhint %}

### Algumas boas práticas

* Mantenha os componentes tão pequenos e ["idiotas"](https://en.wikipedia.org/wiki/Pure\_function) quanto possível.
* Use [Composition ao invés de Inheritance](https://reactjs.org/docs/composition-vs-inheritance.html).
* Lembre-se de que seu código será lido e mantido por vários outros desenvolvedores. Torne-o o mais claro e fácil de atualizar possível.

## Criando seu pull request

Seu código está pronto para ser enviado para revisão, parabéns🥳

* Todas os pull requests **devem** ter uma descrição do que o PR está tentando realizar.
* Mantenha as pull requests o **menor possível**. Pull Requests maiores devem ser divididas em partes menores com um branch base dedicada. Por favor, marque os PRs que estão se fundindo em sua ramificação base com a tag `epic.`
* Se possível, faça uma autoavaliação de seu RP e a**dicione comentários** quando forem necessários esclarecimentos adicionais.

{% hint style="info" %}
Crie um [rascunho do PR](https://github.blog/2019-02-14-introducing-draft-pull-requests/)  o mais rápido possível para que possamos ver seu progresso contínuo.
{% endhint %}

### Título do Pull Request&#x20;

Nosos títulos de Pull Request seguem [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) usando [commitlint](https://commitlint.js.org/#/).‌

_Mais na_ [_Documentação de Angular_](https://github.com/angular/angular/blob/22b96b9/CONTRIBUTING.md#type)

| Tipo         | Descrição                                                                                                                    |
| ------------ | ---------------------------------------------------------------------------------------------------------------------------- |
| **build**    | Alterações que afetam o sistema de compilação ou dependências externas (exemplos de escopos: gulp, broccoli, npm)            |
| **ci**       | Alterações em nossos arquivos e scripts de configuração de CI (exemplos de escopos: Travis, Circle, BrowserStack, SauceLabs) |
| **docs**     | Mudanças só de Documentação                                                                                                  |
| **feat**     | Uma nova característica                                                                                                      |
| **fix**      | Uma correção de bug                                                                                                          |
| **perf**     | Uma mudança de código que melhora o desempenho                                                                               |
| **refactor** | Uma alteração de código que não corrige um bug nem adiciona um recurso                                                       |
| **style**    | Alterações que não afetam o significado do código (espaço em branco, formatação, falta de ponto-e-vírgula etc.)              |
| **test**     | Adicionando testes ausentes ou corrigindo testes existentes                                                                  |

Obrigado por nos ajudar a tornar a PancakeSwap ainda mais incrível ❤
