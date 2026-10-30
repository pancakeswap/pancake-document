---
description: MetaMaskで保留中のまま止まっているトランザクションを「解除」する方法
---

# MetaMaskで保留中のまま止まっているトランザクションの解決方法

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-fix-a-stuck-transaction-header.png)

MetaMaskでトランザクションが保留中のまま止まっており、「Cancel」ボタンを押しても解決しない場合は、この方法で滞留を解消する必要があるかもしれません。

この方法は、止まっているトランザクションを、より優先度の高い別のトランザクションで実質的に上書きするものです。

### **1. カスタムトランザクションNonceを有効にする**

1\. MetaMaskのプラグインを開きます。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-1-MetaMask_plugin.png)

2\. 右上のカラフルな丸いアイコンをクリックし、ドロップダウンメニューから**Settings**をクリックします。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-2-MetaMask_settings%20%281%29.png)

3\. Settingsメニューで**Advanced**を選択します。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-3-MetaMask_advanced.png)

4\. **Advanced gas controls**が表示されるまでスクロールし、ONに切り替えます。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-4-MetaMask_gas_control_on.png)

5\. 引き続きAdvanced設定の中で、**Customize transaction nonce**が表示されるまでスクロールし、ONに切り替えます。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-4-MetaMask_gas_control_on.png)

### **2. 止まっているトランザクションを探す**

ここでは、止まっているトランザクションを見つけ、その「nonce」を控えておきます。nonceは識別子のようなもので、後で再利用します。

![](https://lh4.googleusercontent.com/xKBEnt5a62c5Wzg_MCLIbVUWuL4fws1ohBAX9LAkGS71vslHk7QuMF24jAfkAdmsLunPVfT9c3FxCmGar5z7jNZnd4WMgzQsoxxbYw1Lp59Az5kG72COn0JblFXktHbmgMnF1LeY)

6\. MetaMaskのトップページに戻ります。「Assets」タブで、止まっているトランザクションのトークンの種類(この例ではCAKE)を探します。

![](https://lh5.googleusercontent.com/9qVjhK1kEKDL8l4TTdOFo4o547PDIIeQpCCY18gPyaUFJrpFbyYhMfBQ1CRzjjrllgrcqVbwkhxKCZBNlIad8J1yCpMVhsBKjIAcwfsQHQb7jnl2RD2ufQU-zNEn2Hn2g4LGvYDU)

7\. トークンのメニューで、Queue(待機中)の欄にある**Pending**のトランザクションを探します。トランザクションをクリックすると詳細が表示されます。

![](https://lh4.googleusercontent.com/HMd5iKjIvm-f7Xi7xtecTsq56x1i15GjUkwCm5Z_83xMfOXDd2jabcCDyUwELf51IHseEeCk2WnvWfHwTSUlFnLAJrmjkkOfm_fA5fimgdABnYfdjmBxxst8TOaUJUhc2iO_CN-k)

8\. **Nonce**の項目を探し、その番号を控えておきます。

### **3. 止まっているトランザクションを上書きする**

次に、止まっているトランザクションを置き換える新しいトランザクションを作成します。Nonceの番号をカスタマイズして、先ほど控えた番号と同じにします。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28176%29.png)

9\. 止まっているトランザクションを置き換える新しいトランザクションを作成します。今回は**Transaction Fee**を引き上げます。ここでは9から20に引き上げています。これにより、トランザクションがブロックに取り込まれやすくなります。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2834%29.png)

10\. 確認ページで、Gas Priceが新しく設定した高い金額になっていることを確認します。

11\. **CUSTOM NONCE**の項目を探し、ステップ8で控えた番号にnonceを変更します。その後Confirmをクリックします。

![](https://lh6.googleusercontent.com/PYhYm2ro0SVzerBo5qguFIPOYl0DjLSfl0JT8UdfN3T4i-0hjBq-CQvr-UA0bSyG-ZndrWmLGptfZUcnGBlvUk118GGZn7ciDNaC4hmfovH9v_M5XMIYmkAmB-Fr-6TTpYnnDX1p)

12\. 新しいトランザクションがブロックに取り込まれるはずです。確認するには、MetaMaskを開いて**Activity**タブをクリックします。

![](https://lh6.googleusercontent.com/Iw3e0YP4ORhPgw8-MNxvzlDlfgG5nD226P4ixiziPC_9j3_LfU3o1-_LA2yDmegbRw5x9Sgk3RACFJJkyJDrFJA1j2J93H21uGhhWabkdDQUHsU_oVdkZVQTTWaQPzXHAWClpsb4)

13\. 完了したトランザクションが、Activityリストの一番上に表示されます。オレンジ色で「Pending」と表示されたままの場合は、もう少し待つか、さらに高いトランザクション手数料(ガス価格)でもう一度この手順をお試しください。

ウォレットは同じnonceのトランザクションを2つ作成できないため、置き換えのトランザクションが成功すると、止まっていたトランザクションはキャンセルされます。<br>
