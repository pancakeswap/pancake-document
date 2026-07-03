---
description: PancakeSwapへの貢献に興味を持っていただきありがとうございます！
---

# コントリビューション

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/developers-header.png)

PancakeSwapはオープンソースプロジェクトです。プロジェクトに貢献したい方のために、このセクションではPancakeSwapチームとの最初のステップをガイドします 🥞

開発を始める前に、問題と解決策についてチームと議論するためにGithubでIssueを提出されることを強くお勧めします。

## 開発環境のセットアップ

[yarn](https://classic.yarnpkg.com/lang/en/docs/install/)がインストールされていない場合はインストールしてください。

1.  [リポジトリ](https://github.com/pancakeswap/pancake-frontend)をForkしてクローンします

    ```bash
    $ git clone [fork_repo_url]
    ```
2.  [upstream](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/configuring-a-remote-for-a-fork)リモートを追加します。例：

    ```bash
    $ git remote add upstream git@github.com:pancakeswap/pancake-frontend.git
    ```
3.  デフォルトブランチ（`develop`）の最新版を取得します

    ```bash
    $ git checkout develop
    $ git pull upstream develop
    ```
4.  自分のブランチを作成して依存関係をインストールします

    ```bash
    $ git checkout -b branch-name
    $ yarn
    ```
5. コーディングをお楽しみください 🎉

## コーディングルール

各リポジトリ間でできる限り一貫性を保つよう努めています。以下のルールに従い、高品質なコードを書くことでプルリクエストが承認される可能性が高まります。**始めましょう** 💪

### UIKitを使用する

{% hint style="warning" %}
作業を始める前に[UI Kit](https://github.com/pancakeswap/pancake-frontend/tree/master/packages/uikit)を確認してください。多くのコンポーネントがすでに作成されており、車輪の再発明に時間を無駄にしてほしくありません 😉
{% endhint %}

コンポーネントのバリアントを作成する必要がある場合は、UI Kitの対応するコンポーネントをベースとして使用してください。例：

```javascript
import styled from 'styled-components'
import { Button } from '@pancakeswap/uikit'

const NewButtonVariant = styled(Button)`
  // custom styles here
`
```

### ツールを使おう！

ほとんどのリポジトリでは[Typescript](https://www.typescriptlang.org/docs)、[ESLint](https://eslint.org/docs/user-guide/getting-started)、[Prettier](https://prettier.io)を使用しています。Typescriptのベストプラクティスに精通し、IDEにESLintとPrettierのプラグインを有効化してください。

{% hint style="warning" %}
プルリクエストを提出する前に、コードがPrettierでフォーマットされており、ESLintエラーがないことを確認してください。
{% endhint %}

### 良いプラクティス

* コンポーネントはできる限り小さく["ダム"](https://en.wikipedia.org/wiki/Pure_function)に保ってください。
* [継承より合成](https://reactjs.org/docs/composition-vs-inheritance.html)を使用してください。
* 自分のコードが他の複数の開発者に読まれ、メンテナンスされることを念頭に置いてください。できる限り明確でアップデートしやすいコードにしましょう。_​_

## プルリクエストの作成

コードのレビュー提出準備ができました、おめでとうございます 🥳

* すべてのプルリクエストには**PRが達成しようとしていることの説明**が必要です。
* プルリクエストはできる限り**小さく**保ってください。大きなプルリクエストは専用のベースブランチを持つ小さなチャンクに分割してください。ベースブランチへマージするPRには`epic`タグを付けてください。
* 可能であれば自分でPRをレビューし、追加の説明が必要な箇所には**コメントを追加**してください。

{% hint style="info" %}
できるだけ早く[ドラフトPR](https://github.blog/2019-02-14-introducing-draft-pull-requests/)を作成して、進行状況を確認できるようにしてください。
{% endhint %}

### プルリクエストのタイトル

プルリクエストのタイトルは[commitlint](https://commitlint.js.org/#/)を使用した[Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/)に従います。‌

_詳細は_ [_Angularのガイドライン_](https://github.com/angular/angular/blob/22b96b9/CONTRIBUTING.md#type)_を参照してください_

| タイプ          | 説明                                                                                                 |
| ------------ | ----------------------------------------------------------------------------------------------------------- |
| **build**    | ビルドシステムまたは外部依存関係に影響する変更（スコープの例：gulp、broccoli、npm）         |
| **ci**       | CIの設定ファイルやスクリプトの変更（スコープの例：Travis、Circle、BrowserStack、SauceLabs） |
| **docs**     | ドキュメントのみの変更                                                                                  |
| **feat**     | 新機能                                                                                               |
| **fix**      | バグ修正                                                                                                   |
| **perf**     | パフォーマンスを改善するコード変更                                                                     |
| **refactor** | バグの修正でも新機能の追加でもないコード変更                                                   |
| **style**    | コードの意味に影響しない変更（空白、フォーマット、セミコロンの欠落など）      |
| **test**     | テストの追加または既存のテストの修正                                                           |

**PancakeSwapをさらに素晴らしいものにするためにご協力いただきありがとうございます** ❤
