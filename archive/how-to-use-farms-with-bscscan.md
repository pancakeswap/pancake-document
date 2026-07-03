# BscScanを使ったFarmの利用方法

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-yield-farms-bscscan-header.png)

PancakeSwapでFarmを使用するには複数の手順があり、最初は難しく感じるかもしれません。このガイドでは、BscScanを通じてFarmのコントラクトを直接操作する方法を説明します。

{% hint style="warning" %}
BscScanを使用してコントラクトと直接やり取りすることは、初心者にはお勧めしません。自信がない場合は、代わりに[Farmの使い方ガイド](https://docs.pancakeswap.finance/products/yield-farming/how-to-use-farms)をお使いください。
{% endhint %}

## FarmのプロセスID（PID）を見つける

Farmのスマートコントラクトと正しくやり取りするためには、LPペアに対応するプロセスID（PID）が必要です。現時点では、GitHubで確認するのが最も簡単な方法です。

1\. [GithubのPancakeSwapウェブサイトのFarmコード](https://github.com/pancakeswap/pancake-frontend/blob/master/src/config/constants/farms.ts)を開きます。

2\. **Ctrl/Command** + **F**でティッカー（プロジェクト名ではなく）でペアを検索します。例：「CAKE-BUSD」。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2871%29.png)

3\. PID番号（この場合は389）を書き留めるかコピーして、後で簡単にアクセスできる場所に保存してください。後で必要になります。

## BscScanを通じてLPトークンをデポジットする

BscScanを使用してLPトークンをデポジットするにはいくつかの手順があります。わかりやすいようにステップに分けて説明します。

### メインステーキングコントラクトのアドレスを取得する

メインステーキングコントラクトのアドレスは：**0x73feaa1eE314F8c655E354234017bE2193C9E24E**

確認したい場合は、[PancakeSwap: Main Staking Contract BscScanページ](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract)にアクセスしてください。左上にアドレスが表示されます。**ページアイコン**をクリックしてクリップボードにコピーしてください。後で必要になります。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2877%29.png)

### LPトークンのコントラクトを開く

FarmにコミットしたいLPトークンのスマートコントラクトを承認してから使用する必要があります。

### ソースコードから

1\. まず、[GithubでFarms.tsを開きます](https://github.com/pancakeswap/pancake-frontend/blob/master/src/config/constants/farms.ts)。

2\. **Ctrl/Command** + **F**でティッカー（プロジェクト名ではなく）でペアを検索します。例：「CAKE-BNB」

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28175%29.png)

3\. 探しているLPペアのコードが見つかったら、「56:」の後のアドレスを見つけてください。これがコントラクトアドレスになります。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2849%29.png)

### UIから

1\. まず、[PancakeSwap Farmsページ](https://pancakeswap.finance/farms)にアクセスし、右上の「SEARCH」フィールドで選択したペアを検索します。この例ではCAKE-BUSDを使用しています。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2882%29.png)

2\. **詳細**をクリックして行を展開し、詳細情報を表示します。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28236%29.png)

3\. **View Contract**をクリックしてBscScanでスマートコントラクトを開きます。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28145%29.png)

### LPトークンコントラクトへの許可を付与する

BscScanでLPトークンのコントラクトを開いたら、FarmへのLPトークンの使用を承認します。

1\. LPトークンのコントラクトページで、**Contract**、次に**Write Contract**に移動します。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. MetaMaskに接続するには**Connect to Web3**をクリックします。

![](https://lh4.googleusercontent.com/IRXfcKBWmlH8o7gDE9ThGrKuc2DHZSNb-SxF93VSTkCdv2JjtdvKciPb5jom4Uv-ngpPMrrGQI1XuM6H2SuN81NMxGLzoHAye5YgvUzR9YSM6ElZs6e3A-fpnMT21PKyJmV2F1IZ)

接続を確認してください。

3\. 関数1「approve」の下に「spender:address」があります。先ほどクリップボードにコピーしたMain Staking Contractのアドレスを貼り付けてください。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28225%29.png)

5\. コントラクトが使用できるLPトークンの量も承認する必要があります。値フィールドにはWei単位で金額を入力してください。[BscScan Unit Converter](https://www.bscscan.com/unitconverter)を使用すると、金額を簡単にWeiに変換できます。ここでは5 CAKE-BUSD LPトークンを使用します。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28158%29.png)

{% hint style="warning" %}
値として`-1`を使用すると、無制限の使用承認を付与できます。これはデフォルトですべてを使用するという意味ではなく、このコントラクトを使用したいかなるサイズのトランザクションもウォレットによって許可されることを意味します。
{% endhint %}

6\. **Write**をクリックしてMetaMaskウォレットのアクションを承認します。これで承認した量までFarmにLPトークンをコミットできるようになります。

### Main Staking Contractスマートコントラクトを使ってLPトークンをデポジットする

Main Staking Contractがお客様のLPトークンを使用できるように承認されたので、次はデポジットを行います。

1\. [PancakeSwap: Main Staking Contract BscScanページ](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract)に戻り、**Contract**、次に**Write Contract**に移動します。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. **Connect to Web3**をクリックしてMetaMaskに接続します。

3\. 関数2「deposit」までスクロールし、「\_pid」フィールドにPIDを入力します。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2884%29.png)

先ほどPIDを書き留めなかった場合は、このページの上部にある**FarmのプロセスIDを見つける**セクションで取得方法を確認できます。

4\. \_pidの下にある「\_amount」が表示されます。先ほど承認したLPコントラクトが使用できる金額を入力してください。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28257%29.png)

5\. 情報を確認して**Write**をクリックします。MetaMaskでアクションを確認してください。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2857%29.png)

6\. **View your transaction**をクリックしてデポジットが成功したことを確認できます。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28190%29.png)

## プールから引き出す

プールからLPトークンを引き出す方法は、デポジットと非常に似ています。違いは操作する関数です。

1\. [PancakeSwap: Main Staking Contract BscScanページ](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract)に戻り、**Contract**、次に**Write Contract**に移動します。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. **Connect to Web3**をクリックしてMetaMaskに接続します。

3\. 関数15「withdraw」までスクロールし、「\_pid」フィールドにPIDを入力します。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28166%29.png)

先ほどPIDを書き留めなかった場合は、このページの上部にある**FarmのプロセスIDを見つける**セクションで取得方法を確認できます。

4\. \_pidの下にある「\_amount」が表示されます。プールから引き出したいLPの金額を入力してください。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2837%29.png)

5\. 情報を確認して**Write**をクリックします。MetaMaskでアクションを確認してください。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2857%29.png)

6\. **View your transaction**をクリックして引き出しが成功したことを確認できます。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28190%29.png)

## **緊急引き出しを行う**

‌緊急引き出し機能を使用すると、他の方法が機能しない場合にプールからすべての資金を引き出すことができます。

{% hint style="danger" %}
**緊急引き出し機能を使用すると、CAKEの報酬が失われます！**

PancakeSwapチームは、PancakeSwapチームから公式に指示された場合や、スマートコントラクトとのやり取りに十分な経験があり基盤となるコードを理解している場合を除き、この機能を使用しないことを強くお勧めします。
{% endhint %}

‌1. [PancakeSwap: Main Staking Contract BscScanページ](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract)で、**Contract**、次に**Write Contract**に移動します。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. **Connect to Web3**をクリックしてMetaMaskに接続します。

![](https://lh4.googleusercontent.com/IRXfcKBWmlH8o7gDE9ThGrKuc2DHZSNb-SxF93VSTkCdv2JjtdvKciPb5jom4Uv-ngpPMrrGQI1XuM6H2SuN81NMxGLzoHAye5YgvUzR9YSM6ElZs6e3A-fpnMT21PKyJmV2F1IZ)

‌3. 関数4「emergencyWithdraw」までスクロールし、「\_pid」フィールドにPIDを入力します。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28275%29.png)

先ほどPIDを書き留めなかった場合は、このページの上部にある**FarmのプロセスIDを見つける**セクションで取得方法を確認できます。

5\. 情報を確認して**Write**をクリックします。MetaMaskでアクションを確認してください。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2857%29.png)

6\. **View your transaction**をクリックして引き出しが成功したことを確認できます。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28190%29.png)
