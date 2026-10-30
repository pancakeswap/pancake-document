---
description: PancakeSwap에 기여하는 데 관심을 가져 주셔서 감사합니다!
---

# 기여하기

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/developers-header.png)

PancakeSwap은 오픈 소스 프로젝트입니다. 프로젝트에 기여하고 싶으시다면 이 섹션이 PancakeSwap 팀과 함께하는 첫걸음을 안내해 드립니다 🥞

개발을 시작하기 전에 Github에 이슈를 제출하여 문제와 해결책에 대해 팀과 논의하시기를 강력히 권장합니다.

## 개발 환경 설정

[yarn](https://classic.yarnpkg.com/lang/en/docs/install/)이 설치되어 있지 않다면 설치하세요.

1.  [저장소](https://github.com/pancakeswap/pancake-frontend)를 포크하고 클론합니다.

    ```bash
    $ git clone [fork_repo_url]
    ```
2.  [upstream](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/configuring-a-remote-for-a-fork) 리모트를 추가합니다. 예:

    ```bash
    $ git remote add upstream git@github.com:pancakeswap/pancake-frontend.git
    ```
3.  기본 브랜치( `develop` )의 최신 버전인지 확인합니다.

    ```bash
    $ git checkout develop
    $ git pull upstream develop
    ```
4.  자신의 브랜치를 만들고 의존성을 설치합니다.

    ```bash
    $ git checkout -b branch-name
    $ yarn
    ```
5. 즐거운 코딩 되세요 🎉

## 코딩 규칙

저희는 각 저장소 간에 최대한 일관성을 유지하려고 노력합니다. 다음 규칙을 따르고 고품질 코드를 작성하면 풀 리퀘스트가 승인될 가능성이 더 높아집니다. **시작해 봅시다** 💪

### UIKit 사용하기

{% hint style="warning" %}
무언가를 시작하기 전에 [UI Kit](https://github.com/pancakeswap/pancake-frontend/tree/master/packages/uikit)를 확인하세요. 많은 컴포넌트가 이미 만들어져 있으며, 바퀴를 다시 발명하느라 시간을 낭비하지 않으셨으면 합니다 😉
{% endhint %}

컴포넌트의 변형을 만들어야 한다면 UI Kit의 해당 컴포넌트를 기반으로 사용하세요. 예:

```javascript
import styled from 'styled-components'
import { Button } from '@pancakeswap/uikit'

const NewButtonVariant = styled(Button)`
  // custom styles here
`
```

### 도구를 활용하세요!

대부분의 저장소는 [Typescript](https://www.typescriptlang.org/docs), [ESLint](https://eslint.org/docs/user-guide/getting-started), [Prettier](https://prettier.io)를 사용합니다. Typescript의 모범 사례에 익숙해지고 IDE에서 ESLint 및 Prettier 플러그인을 활성화하세요.

{% hint style="warning" %}
풀 리퀘스트를 제출하기 전에 코드가 Prettier로 포맷되어 있고 ESLint 오류가 없는지 확인하세요.
{% endhint %}

### 몇 가지 좋은 습관

* 컴포넌트는 가능한 한 작고 ["단순하게"](https://en.wikipedia.org/wiki/Pure_function) 유지하세요.
* [상속보다 합성](https://reactjs.org/docs/composition-vs-inheritance.html)을 사용하세요.
* 여러분의 코드는 다른 여러 개발자가 읽고 유지 관리한다는 점을 염두에 두세요. 가능한 한 명확하고 업데이트하기 쉽게 작성하세요._​_

## 풀 리퀘스트 만들기

코드를 검토용으로 제출할 준비가 되었습니다. 축하합니다🥳

* 모든 풀 리퀘스트에는 PR이 달성하려는 목표에 대한 설명이 **반드시** 있어야 합니다.
* 풀 리퀘스트는 **가능한 한 작게** 유지하세요. 더 큰 풀 리퀘스트는 전용 베이스 브랜치를 사용하여 더 작은 단위로 나누어야 합니다. 베이스 브랜치로 병합되는 PR에는 `epic` 태그를 붙여 주세요.
* 가능하다면 PR을 직접 검토하고 추가 설명이 필요한 곳에 **댓글을 추가**하세요.

{% hint style="info" %}
진행 상황을 확인할 수 있도록 가능한 한 빨리 [드래프트 PR](https://github.blog/2019-02-14-introducing-draft-pull-requests/)을 만들어 주세요.
{% endhint %}

### 풀 리퀘스트 제목

PancakeSwap의 풀 리퀘스트 제목은 [commitlint](https://commitlint.js.org/#/)를 사용하여 [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/)를 따릅니다.‌

_자세한 내용은_ [_Angular 가이드라인_](https://github.com/angular/angular/blob/22b96b9/CONTRIBUTING.md#type)_을 참조하세요_

| 유형           | 설명                                                                  |
| ------------ | ------------------------------------------------------------------- |
| **build**    | 빌드 시스템 또는 외부 의존성에 영향을 주는 변경 (예시 범위: gulp, broccoli, npm)            |
| **ci**       | CI 구성 파일 및 스크립트 변경 (예시 범위: Travis, Circle, BrowserStack, SauceLabs) |
| **docs**     | 문서만 변경                                                              |
| **feat**     | 새로운 기능                                                              |
| **fix**      | 버그 수정                                                               |
| **perf**     | 성능을 개선하는 코드 변경                                                      |
| **refactor** | 버그를 수정하거나 기능을 추가하지 않는 코드 변경                                         |
| **style**    | 코드의 의미에 영향을 주지 않는 변경 (공백, 포맷팅, 누락된 세미콜론 등)                          |
| **test**     | 누락된 테스트 추가 또는 기존 테스트 수정                                             |

**PancakeSwap을 더욱 멋지게 만드는 데 도움을 주셔서 감사합니다** ❤
