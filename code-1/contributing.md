# Contributing

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbKS2mFRDg91ZWCu1Fz%2F-MbKZ6RWPn-lpd84iP22%2Fdocs%20masthead%20\(18\).png?alt=media\&token=4447fa07-2e56-48de-b4f6-16316b83f3dd)

Pancake is an open-source project. If you want to contribute to the project, this section is here to guide you through your first steps with the Pancake team 🥞

Before starting any development, we highly encourage you to submit an issue on Github in order to discuss the problem, and the solution with the team. If you want to reach out to the dev team directly, contact **@chef\_chungus** on Telegram ![](https://firebasestorage.googleapis.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MQGgFwNps60bbH7yY91%2F-MQGkpAKkjaKCYaDRZJk%2FLogo.svg?alt=media\&token=e7a73219-f26f-4702-bb12-ed8d9dedc658)

## Setup your dev environment <a href="#setup-your-dev-environment" id="setup-your-dev-environment"></a>

1. Fork the repository and an [add upstream remote](https://docs.github.com/en/free-pro-team@latest/github/collaborating-with-issues-and-pull-requests/configuring-a-remote-for-a-fork). E.g.
2.  Make sure you have the latest version of the default branch ( `develop` or `master` )

    ```
    $ git checkout develop$ git pull upstream develop
    ```
3.  Create your own branch and install dependencies

    ```
    $ git checkout -b branch-name$ yarn
    ```
4. Happy coding 🎉

## Coding rules <a href="#coding-rules" id="coding-rules"></a>

We try to maintain as much consistency as we can between each of our repository. Your pull request has more chances to be accepted if you follow some the following rules, and write high quality code. **Let's get started** 💪

### Use the UIKit <a href="#use-the-uikit" id="use-the-uikit"></a>

Check the [UI Kit](https://github.com/pancakeswap/pancake-uikit) before you start doing anything. A lot of components are already created, and we don't want that you waste your time reinventing the wheel 😉

If a variant of a component needs to be created, use the corresponding component in the UI Kit as a base. For example:

```
import styled from 'styled-components'import { Button } from '@pancakeswap-libs/uikit'​const NewButtonVariant = styled(Button)`  // custom styles here`
```

### Use the tools ! <a href="#use-the-tools" id="use-the-tools"></a>

Most of our repos use [Typescript](https://www.typescriptlang.org/docs), [ESLint](https://eslint.org/docs/user-guide/getting-started), and [Prettier](https://prettier.io). Make sure you are familiar with Typescript’s best practices, and enable an ESLint and Prettier plugin for your IDE.

Make sure your code is formatted with Prettier, and is free from any ESLint error before you submit a pull request.

### Some good practices <a href="#some-good-practices" id="some-good-practices"></a>

* Keep components as small and ["dumb"](https://en.wikipedia.org/wiki/Pure\_function) as possible.
*
* Keep in mind that your code will be read and maintained by several other developers. Make it as clear and easy to update as possible.

## Committing <a href="#committing" id="committing"></a>

Our commit messages follow [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) using [commitlint](https://commitlint.js.org/#/).‌

_More at_ [_Angular's guidelines_](https://github.com/angular/angular/blob/22b96b9/CONTRIBUTING.md#type)_​_

## Creating your pull request  <a href="#creating-your-pull-request" id="creating-your-pull-request"></a>

Your code is ready to be submitted for review, congratulations🥳

* All pull requests **must** have a description of what the PR is trying to accomplish.
* Keep pull requests **as small as possible**. Larger pull requests should be broken up into smaller chunks with a dedicated base branch. Please tag the PR's that are merging into your base branch with the `epic` tag.
* If possible self-review your PR and **add comments** where additional clarification is needed.

Create a [draft PR](https://github.blog/2019-02-14-introducing-draft-pull-requests/) as soon as possible so we can view your ongoing progress.

**Thanks your for helping us making Pancake even more awesome** ❤
