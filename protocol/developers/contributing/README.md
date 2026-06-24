---
description: 感谢你对为 PancakeSwap 做出贡献表现出的兴趣！
---

# 贡献指南

![](../../../.gitbook/assets/developers-header.png)

PancakeSwap 是一个开源项目。如果你想为该项目做出贡献，本节内容将引导你完成与 PancakeSwap 团队合作的第一步 🥞

在开始任何开发之前，我们强烈建议你在 Github 上提交一个 issue，以便与团队讨论问题及解决方案。

## 搭建你的开发环境

如果尚未安装，请先安装 [yarn](https://classic.yarnpkg.com/lang/en/docs/install/)。

1.  Fork 并克隆[代码仓库](https://github.com/pancakeswap/pancake-frontend)

    ```bash
    $ git clone [fork_repo_url]
    ```
2.  添加 [upstream](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/configuring-a-remote-for-a-fork) 远程仓库。例如：

    ```bash
    $ git remote add upstream git@github.com:pancakeswap/pancake-frontend.git
    ```
3.  确保你拥有默认分支（ `develop` ）的最新版本

    ```bash
    $ git checkout develop
    $ git pull upstream develop
    ```
4.  创建你自己的分支并安装依赖

    ```bash
    $ git checkout -b branch-name
    $ yarn
    ```
5. 开始愉快地编码吧 🎉

## 编码规则

我们尽力在各个代码仓库之间保持尽可能多的一致性。如果你遵循以下规则并编写高质量的代码，你的 pull request 被接受的机会会更大。**让我们开始吧** 💪

### 使用 UIKit

{% hint style="warning" %}
在你开始做任何事情之前，请先查看 [UI Kit](https://github.com/pancakeswap/pancake-frontend/tree/master/packages/uikit)。许多组件已经创建好了，我们不希望你浪费时间重复造轮子 😉
{% endhint %}

如果需要创建某个组件的变体，请以 UI Kit 中的相应组件为基础。例如：

```javascript
import styled from 'styled-components'
import { Button } from '@pancakeswap/uikit'

const NewButtonVariant = styled(Button)`
  // custom styles here
`
```

### 善用工具！

我们的大多数仓库都使用 [Typescript](https://www.typescriptlang.org/docs)、[ESLint](https://eslint.org/docs/user-guide/getting-started) 和 [Prettier](https://prettier.io)。请确保你熟悉 Typescript 的最佳实践，并为你的 IDE 启用 ESLint 和 Prettier 插件。

{% hint style="warning" %}
在提交 pull request 之前，请确保你的代码已使用 Prettier 格式化，并且没有任何 ESLint 错误。
{% endhint %}

### 一些良好实践

* 让组件尽可能小且["简单"](https://en.wikipedia.org/wiki/Pure_function)。
* 使用[组合优于继承](https://reactjs.org/docs/composition-vs-inheritance.html)。
* 请记住，你的代码将被其他几位开发者阅读和维护。请让它尽可能清晰、易于更新。_​_

## 创建你的 pull request

你的代码已准备好提交审核，恭喜🥳

* 所有 pull request **必须**包含对该 PR 试图实现目标的描述。
* 让 pull request **尽可能小**。较大的 pull request 应拆分为更小的部分，并使用专门的基础分支。请为合并到你基础分支的 PR 打上 `epic` 标签。
* 如有可能，请自我审查你的 PR，并在需要进一步说明的地方**添加注释**。

{% hint style="info" %}
请尽快创建[草稿 PR](https://github.blog/2019-02-14-introducing-draft-pull-requests/)，以便我们查看你的实时进度。
{% endhint %}

### Pull Request 标题

我们的 Pull Request 标题遵循 [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) 规范，并使用 [commitlint](https://commitlint.js.org/#/)。‌

_更多内容请见_ [_Angular 的指南_](https://github.com/angular/angular/blob/22b96b9/CONTRIBUTING.md#type)

| 类型         | 描述                                                                                                 |
| ------------ | ----------------------------------------------------------------------------------------------------------- |
| **build**    | 影响构建系统或外部依赖的更改（示例范围：gulp、broccoli、npm）         |
| **ci**       | 对我们 CI 配置文件和脚本的更改（示例范围：Travis、Circle、BrowserStack、SauceLabs） |
| **docs**     | 仅文档相关的更改                                                                                  |
| **feat**     | 新功能                                                                                               |
| **fix**      | 错误修复                                                                                                 |
| **perf**     | 提升性能的代码更改                                                                     |
| **refactor** | 既不修复错误也不添加功能的代码更改                                                   |
| **style**    | 不影响代码含义的更改（空格、格式、缺少分号等）      |
| **test**     | 添加缺失的测试或修正现有测试                                                           |

**感谢你帮助我们让 PancakeSwap 变得更加出色** ❤
