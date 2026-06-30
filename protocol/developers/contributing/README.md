---
description: Cảm ơn bạn đã bày tỏ sự quan tâm đến việc đóng góp cho PancakeSwap!
---

# Đóng góp

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/developers-header.png)

PancakeSwap là một dự án mã nguồn mở. Nếu bạn muốn đóng góp cho dự án, phần này sẽ hướng dẫn bạn qua những bước đầu tiên cùng với đội ngũ PancakeSwap 🥞

Trước khi bắt đầu phát triển bất kỳ điều gì, chúng tôi khuyến khích bạn nên gửi một issue trên Github để thảo luận về vấn đề và giải pháp với đội ngũ.

## Thiết lập môi trường phát triển

Cài đặt [yarn](https://classic.yarnpkg.com/lang/en/docs/install/) nếu bạn chưa có.

1.  Fork và clone [repository](https://github.com/pancakeswap/pancake-frontend)

    ```bash
    $ git clone [fork_repo_url]
    ```
2.  Thêm remote [upstream](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/configuring-a-remote-for-a-fork). Ví dụ:

    ```bash
    $ git remote add upstream git@github.com:pancakeswap/pancake-frontend.git
    ```
3.  Đảm bảo bạn có phiên bản mới nhất của nhánh mặc định ( `develop` )

    ```bash
    $ git checkout develop
    $ git pull upstream develop
    ```
4.  Tạo nhánh của riêng bạn và cài đặt các dependency

    ```bash
    $ git checkout -b branch-name
    $ yarn
    ```
5. Chúc bạn code vui 🎉

## Quy tắc code

Chúng tôi cố gắng duy trì sự nhất quán giữa các repository của mình. Pull request của bạn có nhiều khả năng được chấp nhận hơn nếu bạn tuân theo các quy tắc sau và viết code chất lượng cao. **Bắt đầu thôi** 💪

### Sử dụng UIKit

{% hint style="warning" %}
Hãy kiểm tra [UI Kit](https://github.com/pancakeswap/pancake-frontend/tree/master/packages/uikit) trước khi bạn bắt đầu làm bất cứ điều gì. Rất nhiều component đã được tạo sẵn, và chúng tôi không muốn bạn lãng phí thời gian tái tạo những thứ đã có 😉
{% endhint %}

Nếu cần tạo một biến thể của một component, hãy sử dụng component tương ứng trong UI Kit làm cơ sở. Ví dụ:

```javascript
import styled from 'styled-components'
import { Button } from '@pancakeswap/uikit'

const NewButtonVariant = styled(Button)`
  // custom styles here
`
```

### Sử dụng các công cụ!

Hầu hết các repo của chúng tôi sử dụng [Typescript](https://www.typescriptlang.org/docs), [ESLint](https://eslint.org/docs/user-guide/getting-started) và [Prettier](https://prettier.io). Hãy đảm bảo bạn quen thuộc với các phương pháp tốt nhất của Typescript và bật plugin ESLint và Prettier cho IDE của bạn.

{% hint style="warning" %}
Đảm bảo code của bạn được định dạng bằng Prettier và không có lỗi ESLint nào trước khi gửi pull request.
{% endhint %}

### Một số phương pháp thực hành tốt

* Giữ các component càng nhỏ và ["đơn giản"](https://en.wikipedia.org/wiki/Pure_function) càng tốt.
* Sử dụng [Composition thay vì Inheritance](https://reactjs.org/docs/composition-vs-inheritance.html).
* Hãy nhớ rằng code của bạn sẽ được đọc và duy trì bởi nhiều nhà phát triển khác. Hãy làm cho nó rõ ràng và dễ cập nhật nhất có thể._​_

## Tạo pull request của bạn

Code của bạn đã sẵn sàng để gửi đi review, chúc mừng 🥳

* Tất cả pull request **phải** có mô tả về những gì PR đang cố gắng thực hiện.
* Giữ pull request **nhỏ nhất có thể**. Các pull request lớn hơn nên được chia thành các phần nhỏ hơn với nhánh cơ sở riêng. Vui lòng gắn thẻ `epic` cho các PR đang merge vào nhánh cơ sở của bạn.
* Nếu có thể, hãy tự review PR của mình và **thêm comment** ở những nơi cần giải thích thêm.

{% hint style="info" %}
Tạo [draft PR](https://github.blog/2019-02-14-introducing-draft-pull-requests/) càng sớm càng tốt để chúng tôi có thể theo dõi tiến trình của bạn.
{% endhint %}

### Tiêu đề Pull Request

Tiêu đề Pull Request của chúng tôi tuân theo [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) sử dụng [commitlint](https://commitlint.js.org/#/).‌

_Xem thêm tại_ [_hướng dẫn của Angular_](https://github.com/angular/angular/blob/22b96b9/CONTRIBUTING.md#type)

| Loại         | Mô tả                                                                                                        |
| ------------ | ------------------------------------------------------------------------------------------------------------ |
| **build**    | Các thay đổi ảnh hưởng đến hệ thống build hoặc các dependency bên ngoài (ví dụ: gulp, broccoli, npm)         |
| **ci**       | Các thay đổi đối với file cấu hình và script CI (ví dụ: Travis, Circle, BrowserStack, SauceLabs)             |
| **docs**     | Chỉ thay đổi tài liệu                                                                                        |
| **feat**     | Một tính năng mới                                                                                            |
| **fix**      | Sửa lỗi                                                                                                      |
| **perf**     | Thay đổi code cải thiện hiệu suất                                                                            |
| **refactor** | Thay đổi code không sửa lỗi cũng không thêm tính năng                                                       |
| **style**    | Các thay đổi không ảnh hưởng đến ý nghĩa của code (khoảng trắng, định dạng, thiếu dấu chấm phẩy, v.v.)      |
| **test**     | Thêm test còn thiếu hoặc sửa các test hiện có                                                                |

**Cảm ơn bạn đã giúp chúng tôi làm PancakeSwap ngày càng tuyệt vời hơn** ❤
