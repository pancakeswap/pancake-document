---
description: Terima kasih telah menyatakan minat Anda untuk berkontribusi pada PancakeSwap!
---

# Berkontribusi

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/developers-header.png)

PancakeSwap adalah proyek open-source. Jika Anda ingin berkontribusi pada proyek ini, bagian ini hadir untuk memandu Anda melalui langkah pertama bersama tim PancakeSwap 🥞

Sebelum memulai pengembangan apa pun, kami sangat menganjurkan Anda untuk mengajukan isu di Github guna mendiskusikan masalah dan solusinya bersama tim.

## Siapkan lingkungan pengembangan Anda

Instal [yarn](https://classic.yarnpkg.com/lang/en/docs/install/) jika belum terpasang.

1.  Fork dan kloning [repositori](https://github.com/pancakeswap/pancake-frontend)

    ```bash
    $ git clone [fork_repo_url]
    ```
2.  Tambahkan remote [upstream](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/configuring-a-remote-for-a-fork). Contoh:

    ```bash
    $ git remote add upstream git@github.com:pancakeswap/pancake-frontend.git
    ```
3.  Pastikan Anda memiliki versi terbaru dari branch default ( `develop` )

    ```bash
    $ git checkout develop
    $ git pull upstream develop
    ```
4.  Buat branch Anda sendiri dan instal dependensi

    ```bash
    $ git checkout -b branch-name
    $ yarn
    ```
5. Selamat coding 🎉

## Aturan coding

Kami berusaha menjaga konsistensi sebanyak mungkin di antara setiap repositori kami. Pull request Anda memiliki lebih banyak peluang untuk diterima jika Anda mengikuti aturan berikut dan menulis kode berkualitas tinggi. **Mari kita mulai** 💪

### Gunakan UIKit

{% hint style="warning" %}
Periksa [UI Kit](https://github.com/pancakeswap/pancake-frontend/tree/master/packages/uikit) sebelum Anda mulai melakukan apa pun. Banyak komponen sudah dibuat, dan kami tidak ingin Anda membuang waktu menciptakan ulang apa yang sudah ada 😉
{% endhint %}

Jika varian komponen perlu dibuat, gunakan komponen yang sesuai di UI Kit sebagai dasar. Contohnya:

```javascript
import styled from 'styled-components'
import { Button } from '@pancakeswap/uikit'

const NewButtonVariant = styled(Button)`
  // custom styles here
`
```

### Gunakan alat-alatnya!

Sebagian besar repo kami menggunakan [Typescript](https://www.typescriptlang.org/docs), [ESLint](https://eslint.org/docs/user-guide/getting-started), dan [Prettier](https://prettier.io). Pastikan Anda familiar dengan praktik terbaik Typescript dan aktifkan plugin ESLint dan Prettier untuk IDE Anda.

{% hint style="warning" %}
Pastikan kode Anda diformat dengan Prettier dan bebas dari kesalahan ESLint sebelum mengajukan pull request.
{% endhint %}

### Beberapa praktik yang baik

* Jaga komponen agar sekecil dan ["sederhana"](https://en.wikipedia.org/wiki/Pure_function) mungkin.
* Gunakan [Komposisi daripada Pewarisan](https://reactjs.org/docs/composition-vs-inheritance.html).
* Ingat bahwa kode Anda akan dibaca dan dipelihara oleh beberapa pengembang lain. Buat kode sejelas dan semudah mungkin untuk diperbarui._​_

## Membuat pull request Anda

Kode Anda siap untuk dikaji, selamat 🥳

* Semua pull request **wajib** memiliki deskripsi tentang apa yang ingin dicapai oleh PR tersebut.
* Jaga pull request **sekecil mungkin**. Pull request yang lebih besar harus dipecah menjadi potongan-potongan kecil dengan branch dasar yang khusus. Mohon tandai PR yang digabungkan ke branch dasar Anda dengan tag `epic`.
* Jika memungkinkan, tinjau sendiri PR Anda dan **tambahkan komentar** di mana diperlukan klarifikasi tambahan.

{% hint style="info" %}
Buat [draft PR](https://github.blog/2019-02-14-introducing-draft-pull-requests/) sesegera mungkin agar kami dapat melihat perkembangan Anda yang sedang berlangsung.
{% endhint %}

### Judul Pull Request

Judul Pull Request kami mengikuti [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) menggunakan [commitlint](https://commitlint.js.org/#/).‌

_Selengkapnya di_ [_panduan Angular_](https://github.com/angular/angular/blob/22b96b9/CONTRIBUTING.md#type)

| Tipe         | Deskripsi                                                                                                      |
| ------------ | -------------------------------------------------------------------------------------------------------------- |
| **build**    | Perubahan yang mempengaruhi sistem build atau dependensi eksternal (contoh cakupan: gulp, broccoli, npm)       |
| **ci**       | Perubahan pada file konfigurasi dan skrip CI kami (contoh cakupan: Travis, Circle, BrowserStack, SauceLabs)   |
| **docs**     | Perubahan dokumentasi saja                                                                                     |
| **feat**     | Fitur baru                                                                                                     |
| **fix**      | Perbaikan bug                                                                                                  |
| **perf**     | Perubahan kode yang meningkatkan performa                                                                      |
| **refactor** | Perubahan kode yang tidak memperbaiki bug maupun menambahkan fitur                                             |
| **style**    | Perubahan yang tidak mempengaruhi makna kode (spasi, pemformatan, titik koma yang hilang, dll)                 |
| **test**     | Menambahkan pengujian yang hilang atau memperbaiki pengujian yang ada                                          |

**Terima kasih telah membantu kami membuat PancakeSwap semakin luar biasa** ❤
