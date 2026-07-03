---
description: MetaMaskで保留中のまま止まっているトランザクションを解消する方法
---

# MetaMaskで保留中のトランザクションが止まった場合の対処法

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-fix-a-stuck-transaction-header.png)

MetaMaskでトランザクションが保留中のまま止まっており、「キャンセル」ボタンが機能しない場合は、この方法でバックログを解消できるかもしれません。

この方法は、止まっているトランザクションを優先度の高い別のトランザクションで上書きすることで機能します。

### **1. カスタムトランザクションNonceを有効にする**

1\. MetaMaskプラグインを開きます。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-1-MetaMask_plugin.png)

2\. 右上のカラーアイコンをクリックし、ドロップダウンメニューから**設定**をクリックします。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-2-MetaMask_settings%20%281%29.png)

3\. 設定メニューで**詳細設定**を選択します。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-3-MetaMask_advanced.png)

4\. スクロールして**高度なガス制御**を見つけます。これをONに切り替えます。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-4-MetaMask_gas_control_on.png)

5\. 詳細設定のまま引き続きスクロールして**トランザクションNonceのカスタマイズ**を見つけます。これをONに切り替えます。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-4-MetaMask_gas_control_on.png)

### **2. 止まっているトランザクションを見つける**

次に、止まっているトランザクションを見つけ、「Nonce」を記録します。これは一種の識別子で、後で再利用します。

![](https://lh4.googleusercontent.com/xKBEnt5a62c5Wzg_MCLIbVUWuL4fws1ohBAX9LAkGS71vslHk7QuMF24jAfkAdmsLunPVfT9c3FxCmGar5z7jNZnd4WMgzQsoxxbYw1Lp59Az5kG72COn0JblFXktHbmgMnF1LeY)

6\. MetaMaskのトップページに戻ります。「資産」タブで止まっているトランザクションのトークン種別（この例ではCAKE）を見つけます。

![](https://lh5.googleusercontent.com/9qVjhK1kEKDL8l4TTdOFo4o547PDIIeQpCCY18gPyaUFJrpFbyYhMfBQ1CRzjjrllgrcqVbwkhxKCZBNlIad8J1yCpMVhsBKjIAcwfsQHQb7jnl2RD2ufQU-zNEn2Hn2g4LGvYDU)

6\. トークンのメニューで、キュー内の**保留中**のトランザクションを見つけます。詳細を確認するためにトランザクションをクリックします。

![](https://lh4.googleusercontent.com/HMd5iKjIvm-f7Xi7xtecTsq56x1i15GjUkwCm5Z_83xMfOXDd2jabcCDyUwELf51IHseEeCk2WnvWfHwTSUlFnLAJrmjkkOfm_fA5fimgdABnYfdjmBxxst8TOaUJUhc2iO_CN-k)

7\. **Nonce**の項目を見つけ、この番号を記録しておきます。

### **3. 止まっているトランザクションを上書きする**

次に、止まっているトランザクションを置き換えるための新しいトランザクションを作成します。先ほど記録したNonce番号と同じ値にカスタマイズします。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28176%29.png)

8\. 止まっているトランザクションを置き換えるための新しいトランザクションを作成します。今回は**トランザクション手数料**を上げてください。この例では9から20に上げています。こうすることで、トランザクションがブロックに追加されやすくなります。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2834%29.png)

9\. 確認ページで、ガス価格が新たに設定した高い金額になっていることを確認します。

10\. **CUSTOM NONCE**の項目を見つけ、手順7で記録した番号に変更します。「確認」をクリックします。

![](https://lh6.googleusercontent.com/PYhYm2ro0SVzerBo5qguFIPOYl0DjLSfl0JT8UdfN3T4i-0hjBq-CQvr-UA0bSyG-ZndrWmLGptfZUcnGBlvUk118GGZn7ciDNaC4hmfovH9v_M5XMIYmkAmB-Fr-6TTpYnnDX1p)

11\. 新しいトランザクションがブロックに受け入れられるはずです。確認するには、MetaMaskを開いて**アクティビティ**タブをクリックします。

![](https://lh6.googleusercontent.com/Iw3e0YP4ORhPgw8-MNxvzlDlfgG5nD226P4ixiziPC_9j3_LfU3o1-_LA2yDmegbRw5x9Sgk3RACFJJkyJDrFJA1j2J93H21uGhhWabkdDQUHsU_oVdkZVQTTWaQPzXHAWClpsb4)

12\. 完了したトランザクションがアクティビティリストの上部に表示されるはずです。まだオレンジ色で「保留中」と表示されている場合は、もう少し待つか、さらに高いトランザクション手数料（ガス価格）でもう一度試してください。

どのウォレットも同じNonceを持つ2つのトランザクションを作成することはできないため、代替トランザクションが成功すれば、止まっているトランザクションはキャンセルされます。<br>
