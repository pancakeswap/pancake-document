---
description: PancakeSwap'a katkıda bulunmak için başvurduğunuz için teşekkürler!
---

# Katkıda Bulunma

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/developers-header.png)

PancakeSwap açık kaynaklı bir projedir. Projeye katkıda bulunmak istiyorsan bu bölüm, PancakeSwap ekibiyle ilk adımlarında sana rehberlik etmek için burada 🥞

Herhangi bir geliştirmeye başlamadan önce, sorunu ve çözümü ekiple tartışmak için Github'da bir issue açmanı şiddetle tavsiye ederiz.

## Geliştirme ortamını kur

[yarn](https://classic.yarnpkg.com/lang/en/docs/install/) yüklü değilse yükle.

1.  [Repoyu](https://github.com/pancakeswap/pancake-frontend) fork'la ve klonla

    ```bash
    $ git clone [fork_repo_url]
    ```
2.  [upstream](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/configuring-a-remote-for-a-fork) remote'unu ekle. Örneğin:

    ```bash
    $ git remote add upstream git@github.com:pancakeswap/pancake-frontend.git
    ```
3.  Varsayılan branch'in ( `develop` ) en güncel sürümünde olduğundan emin ol

    ```bash
    $ git checkout develop
    $ git pull upstream develop
    ```
4.  Kendi branch'ini oluştur ve bağımlılıkları yükle

    ```bash
    $ git checkout -b branch-name
    $ yarn
    ```
5. Keyifli kodlamalar 🎉

## Kodlama kuralları

Repolarımız arasında mümkün olduğunca tutarlılığı korumaya çalışıyoruz. Aşağıdaki kurallara uyarsan ve yüksek kaliteli kod yazarsan pull request'inin kabul edilme şansı artar. **Başlayalım** 💪

### UIKit'i Kullan

{% hint style="warning" %}
Herhangi bir şeye başlamadan önce [UI Kit'i](https://github.com/pancakeswap/pancake-frontend/tree/master/packages/uikit) incele. Pek çok bileşen zaten oluşturulmuş durumda ve tekerleği yeniden icat etmene gerek olmamasını istiyoruz 😉
{% endhint %}

Bir bileşenin varyantının oluşturulması gerekiyorsa, ilgili bileşeni UI Kit'ten temel olarak kullan. Örneğin:

```javascript
import styled from 'styled-components'
import { Button } from '@pancakeswap/uikit'

const NewButtonVariant = styled(Button)`
  // custom styles here
`
```

### Araçları Kullan!

Repolarımızın çoğu [Typescript](https://www.typescriptlang.org/docs), [ESLint](https://eslint.org/docs/user-guide/getting-started) ve [Prettier](https://prettier.io) kullanır. Typescript'in en iyi uygulamalarına hakim olduğundan emin ol ve IDE'n için bir ESLint ve Prettier eklentisi etkinleştir.

{% hint style="warning" %}
Pull request göndermeden önce kodunun Prettier ile biçimlendirildiğinden ve ESLint hatasından arınmış olduğundan emin ol.
{% endhint %}

### İyi uygulamalar

* Bileşenleri mümkün olduğunca küçük ve ["dumb"](https://en.wikipedia.org/wiki/Pure_function) tut.
* [Kalıtım yerine Kompozisyon](https://reactjs.org/docs/composition-vs-inheritance.html) kullan.
* Kodunun birden fazla geliştirici tarafından okunacağını ve bakımının yapılacağını aklında tut. Mümkün olduğunca anlaşılır ve güncellemesi kolay yaz._​_

## Pull request oluştur

Kodun inceleme için hazır, tebrikler🥳

* Tüm pull request'lerin **PR'ın ne yapmaya çalıştığına dair bir açıklama içermesi zorunludur**.
* Pull request'leri **mümkün olduğunca küçük tut**. Daha büyük pull request'ler, özel bir temel branch ile daha küçük parçalara bölünmelidir. Temel branch'ine birleşecek PR'ları `epic` etiketiyle işaretle.
* Mümkünse PR'ını kendi kendine incele ve ek açıklama gereken yerlere **yorumlar ekle**.

{% hint style="info" %}
İlerlememizi izleyebilmemiz için en kısa sürede [taslak PR](https://github.blog/2019-02-14-introducing-draft-pull-requests/) oluştur.
{% endhint %}

### Pull Request Başlığı

Pull Request Başlıklarımız [commitlint](https://commitlint.js.org/#/) kullanan [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) standardını takip eder.‌

_Daha fazlası için_ [_Angular'ın yönergeleri_](https://github.com/angular/angular/blob/22b96b9/CONTRIBUTING.md#type)

| Tür          | Açıklama                                                                                                          |
| ------------ | ----------------------------------------------------------------------------------------------------------------- |
| **build**    | Derleme sistemini veya harici bağımlılıkları etkileyen değişiklikler (örnek kapsamlar: gulp, broccoli, npm)       |
| **ci**       | CI yapılandırma dosyaları ve script'lerindeki değişiklikler (örnek kapsamlar: Travis, Circle, BrowserStack, SauceLabs) |
| **docs**     | Yalnızca dokümantasyon değişiklikleri                                                                             |
| **feat**     | Yeni bir özellik                                                                                                  |
| **fix**      | Hata düzeltmesi                                                                                                   |
| **perf**     | Performansı iyileştiren kod değişikliği                                                                           |
| **refactor** | Ne hata düzelten ne de özellik ekleyen kod değişikliği                                                            |
| **style**    | Kodun anlamını etkilemeyen değişiklikler (boşluk, biçimlendirme, eksik noktalı virgüller vb.)                     |
| **test**     | Eksik testlerin eklenmesi veya mevcut testlerin düzeltilmesi                                                      |

**PancakeSwap'ı daha da harika yapmanamıza yardımcı olduğun için teşekkürler** ❤
