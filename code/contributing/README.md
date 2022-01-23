---
description: Thank you for expressing your interest in contributing to PancakeSwap!
---

# Contributing

![](<../../.gitbook/assets/docs masthead (18) (1).png>)

PancakeSwap is an open-source project. If you want to contribute to the project, this section is here to guide you through your first steps with the PancakeSwap team 🥞

Before starting any development, we highly encourage you to submit an issue on Github in order to discuss the problem, and the solution with the team. 

## Setup your dev environment

1.  Fork the repository and an [add upstream remote](https://docs.github.com/en/free-pro-team@latest/github/collaborating-with-issues-and-pull-requests/configuring-a-remote-for-a-fork). E.g.

    ```bash
    $ git remote add upstream git@github.com:pancakeswap/pancake-frontend.git
    ```
2.  Make sure you have the latest version of the default branch ( `develop` or `master` )

    ```bash
    $ git checkout develop
    $ git pull upstream develop
    ```
3.  Create your own branch and install dependencies

    ```bash
    $ git checkout -b branch-name
    $ yarn
    ```
4. Happy coding 🎉

## Coding rules

We try to maintain as much consistency as we can between each of our repository. Your pull request has more chances to be accepted if you follow some the following rules, and write high quality code. **Let's get started** 💪

### Use the UIKit

{% hint style="warning" %}
Check the [UI Kit](https://github.com/pancakeswap/pancake-toolkit/tree/master/packages/pancake-uikit) before you start doing anything. A lot of components are already created, and we don't want that you waste your time reinventing the wheel 😉
{% endhint %}

If a variant of a component needs to be created, use the corresponding component in the UI Kit as a base. For example:

```javascript
import styled from 'styled-components'
import { Button } from '@pancakeswap-libs/uikit'

const NewButtonVariant = styled(Button)`
  // custom styles here
`
```

### Use the tools!

Most of our repos use [Typescript](https://www.typescriptlang.org/docs), [ESLint](https://eslint.org/docs/user-guide/getting-started), and [Prettier](https://prettier.io). Make sure you're familiar with Typescript’s best practices, and enable an ESLint and Prettier plugin for your IDE.

{% hint style="warning" %}
Make sure your code is formatted with Prettier, and is free from any ESLint error before you submit a pull request.
{% endhint %}

### Some good practices

* Keep components as small and ["dumb"](https://en.wikipedia.org/wiki/Pure\_function) as possible.
* Use [Composition over Inheritance](https://reactjs.org/docs/composition-vs-inheritance.html).
* Keep in mind that your code will be read and maintained by several other developers. Make it as clear and easy to update as possible.

## Committing <a href="#committing" id="committing"></a>

Our commit messages follow [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) using [commitlint](https://commitlint.js.org/#/).‌

| Type         | Description                                                                                                 |
| ------------ | ----------------------------------------------------------------------------------------------------------- |
| **build**    | Changes that affect the build system or external dependencies (example scopes: gulp, broccoli, npm)         |
| **ci**       | Changes to our CI configuration files and scripts (example scopes: Travis, Circle, BrowserStack, SauceLabs) |
| **docs**     | Documentation only changes                                                                                  |
| **feat**     | A new feature                                                                                               |
| **fix**      | A bug fix                                                                                                   |
| **perf**     | A code change that improves performance                                                                     |
| **refactor** | A code change that neither fixes a bug nor adds a feature                                                   |
| **style**    | Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons, etc)      |
| **test**     | Adding missing tests or correcting existing tests                                                           |

_More at_ [_Angular's guidelines_](https://github.com/angular/angular/blob/22b96b9/CONTRIBUTING.md#type)_​_

## Creating your pull request

Your code is ready to be submitted for review, congratulations🥳

* All pull requests **must** have a description of what the PR is trying to accomplish.
* Keep pull requests **as small as possible**. Larger pull requests should be broken up into smaller chunks with a dedicated base branch. Please tag the PR's that are merging into your base branch with the `epic` tag.
* If possible self-review your PR and **add comments** where additional clarification is needed.

{% hint style="info" %}
Create a [draft PR](https://github.blog/2019-02-14-introducing-draft-pull-requests/) as soon as possible so we can view your ongoing progress.
{% endhint %}

**Thanks for helping us making PancakeSwap even more awesome** ❤
