---
description: PancakeSwap में योगदान देने में अपनी रुचि व्यक्त करने के लिए धन्यवाद!
---

# Contributing

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/developers-header.png)

PancakeSwap एक open-source project है। यदि आप project में योगदान करना चाहते हैं, तो यह section PancakeSwap team के साथ आपके पहले कदमों के माध्यम से आपका मार्गदर्शन करने के लिए यहाँ है 🥞

कोई भी development शुरू करने से पहले, हम आपको Github पर एक issue submit करने के लिए प्रोत्साहित करते हैं ताकि team के साथ समस्या और समाधान पर चर्चा की जा सके।

## अपना dev environment सेटअप करें

यदि आपने नहीं किया है तो [yarn](https://classic.yarnpkg.com/lang/en/docs/install/) Install करें।

1.  [repository](https://github.com/pancakeswap/pancake-frontend) को Fork और clone करें

    ```bash
    $ git clone [fork_repo_url]
    ```
2.  [upstream](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/configuring-a-remote-for-a-fork) remote जोड़ें। उदाहरण के लिए

    ```bash
    $ git remote add upstream git@github.com:pancakeswap/pancake-frontend.git
    ```
3.  सुनिश्चित करें कि आपके पास default branch (`develop`) का नवीनतम version है

    ```bash
    $ git checkout develop
    $ git pull upstream develop
    ```
4.  अपनी own branch बनाएं और dependencies install करें

    ```bash
    $ git checkout -b branch-name
    $ yarn
    ```
5. Happy coding 🎉

## Coding rules

हम अपने प्रत्येक repository के बीच यथासंभव अधिक consistency बनाए रखने का प्रयास करते हैं। यदि आप निम्नलिखित rules का पालन करते हैं और उच्च गुणवत्ता का code लिखते हैं तो आपके pull request को accept होने की अधिक संभावना है। **आइए शुरू करते हैं** 💪

### UIKit उपयोग करें

{% hint style="warning" %}
कुछ भी शुरू करने से पहले [UI Kit](https://github.com/pancakeswap/pancake-frontend/tree/master/packages/uikit) देखें। बहुत सारे components पहले से बने हैं, और हम नहीं चाहते कि आप पहिया फिर से बनाने में अपना समय बर्बाद करें 😉
{% endhint %}

यदि किसी component का एक variant बनाना है, तो UI Kit में संबंधित component को base के रूप में उपयोग करें। उदाहरण के लिए:

```javascript
import styled from 'styled-components'
import { Button } from '@pancakeswap/uikit'

const NewButtonVariant = styled(Button)`
  // custom styles here
`
```

### Tools का उपयोग करें!

हमारे अधिकांश repos [Typescript](https://www.typescriptlang.org/docs), [ESLint](https://eslint.org/docs/user-guide/getting-started), और [Prettier](https://prettier.io) उपयोग करते हैं। सुनिश्चित करें कि आप Typescript की best practices से परिचित हैं और अपने IDE के लिए ESLint और Prettier plugin enable करें।

{% hint style="warning" %}
pull request submit करने से पहले सुनिश्चित करें कि आपका code Prettier के साथ formatted है और किसी भी ESLint error से मुक्त है।
{% endhint %}

### कुछ अच्छी practices

* Components को यथासंभव छोटा और ["dumb"](https://en.wikipedia.org/wiki/Pure_function) रखें।
* [Composition over Inheritance](https://reactjs.org/docs/composition-vs-inheritance.html) का उपयोग करें।
* ध्यान रखें कि आपका code कई अन्य developers द्वारा पढ़ा और maintain किया जाएगा। इसे यथासंभव clear और update करने में आसान बनाएं।

## अपना pull request बनाएं

आपका code review के लिए submit करने के लिए तैयार है, बधाई 🥳

* सभी pull requests में **PR क्या accomplish करने की कोशिश कर रहा है** इसका description होना **चाहिए**।
* Pull requests को **यथासंभव छोटा** रखें। बड़े pull requests को dedicated base branch के साथ छोटे chunks में तोड़ा जाना चाहिए। कृपया उन PRs को `epic` tag से tag करें जो आपकी base branch में merge हो रहे हैं।
* यदि संभव हो तो अपना PR self-review करें और **comments जोड़ें** जहाँ अतिरिक्त स्पष्टीकरण आवश्यक हो।

{% hint style="info" %}
जितनी जल्दी हो सके एक [draft PR](https://github.blog/2019-02-14-introducing-draft-pull-requests/) बनाएं ताकि हम आपकी ongoing progress देख सकें।
{% endhint %}

### Pull Request Title

हमारे Pull Request Title [commitlint](https://commitlint.js.org/#/) का उपयोग करके [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) का पालन करते हैं।

_अधिक जानकारी [Angular's guidelines](https://github.com/angular/angular/blob/22b96b9/CONTRIBUTING.md#type) पर_

| Type         | विवरण                                                                                                  |
| ------------ | ----------------------------------------------------------------------------------------------------- |
| **build**    | build system या external dependencies को प्रभावित करने वाले परिवर्तन (उदाहरण scopes: gulp, broccoli, npm) |
| **ci**       | हमारी CI configuration files और scripts में परिवर्तन (उदाहरण scopes: Travis, Circle, BrowserStack, SauceLabs) |
| **docs**     | केवल Documentation में परिवर्तन                                                                        |
| **feat**     | एक नई सुविधा                                                                                          |
| **fix**      | एक bug fix                                                                                            |
| **perf**     | एक code परिवर्तन जो performance में सुधार करता है                                                      |
| **refactor** | एक code परिवर्तन जो न तो bug fix करता है और न ही feature जोड़ता है                                    |
| **style**    | परिवर्तन जो code के अर्थ को प्रभावित नहीं करते (white-space, formatting, missing semi-colons, आदि)    |
| **test**     | missing tests जोड़ना या existing tests सही करना                                                       |

**PancakeSwap को और भी अधिक awesome बनाने में मदद करने के लिए धन्यवाद** ❤
