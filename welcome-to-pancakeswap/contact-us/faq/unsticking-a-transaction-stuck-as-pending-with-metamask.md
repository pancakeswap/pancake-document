---
description: MetaMask'inde takılı kalan bekleyen işlemlerin nasıl "çözüleceği"
---

# MetaMask'te Takılı Kalan Bekleyen İşlemleri Düzeltme

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-fix-a-stuck-transaction-header.png)

İşlemin MetaMask'te beklemede takılı kaldıysa ve “Cancel” düğmesi işe yaramıyorsa, birikmiş işlemlerini temizlemek için bu yöntemi kullanman gerekebilir.

Bu yöntem, takılı kalan işlemin üzerine daha yüksek öncelikli başka bir işlem yazarak çalışır.

### **1. Özelleştirilmiş İşlem Nonce'unu Etkinleştir**

1\. MetaMask eklentini aç.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-1-MetaMask_plugin.png)

2\. Sağ üstteki renkli daire simgesine tıkla ve açılır menüden **Settings**'i seç.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-2-MetaMask_settings%20%281%29.png)

3\. Settings menüsünde **Advanced**'i seç.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-3-MetaMask_advanced.png)

4\. **Advanced gas controls** seçeneğini görene kadar aşağı kaydır. Bunu ON konumuna getir.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-4-MetaMask_gas_control_on.png)

5\. Hâlâ Advanced ayarlarındayken, **Customize transaction nonce** seçeneğini görene kadar kaydırmaya devam et. Bunu ON konumuna getir.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-4-MetaMask_gas_control_on.png)

### **2. Takılı Kalan İşlemini Bul**

Şimdi takılı kalan işlemi bulacak ve “nonce” değerini not edeceğiz. Bu, daha sonra yeniden kullanacağımız bir tür tanımlayıcıdır.

![](https://lh4.googleusercontent.com/xKBEnt5a62c5Wzg_MCLIbVUWuL4fws1ohBAX9LAkGS71vslHk7QuMF24jAfkAdmsLunPVfT9c3FxCmGar5z7jNZnd4WMgzQsoxxbYw1Lp59Az5kG72COn0JblFXktHbmgMnF1LeY)

6\. MetaMask'in ana sayfasına geri dön. “Assets” sekmesinde, takılı kalan işleminin token türünü bul (bu örnekte CAKE).

![](https://lh5.googleusercontent.com/9qVjhK1kEKDL8l4TTdOFo4o547PDIIeQpCCY18gPyaUFJrpFbyYhMfBQ1CRzjjrllgrcqVbwkhxKCZBNlIad8J1yCpMVhsBKjIAcwfsQHQb7jnl2RD2ufQU-zNEn2Hn2g4LGvYDU)

7\. Tokenın menüsünde, Queue alanında **Pending** durumundaki işlemini bul. Daha fazla ayrıntı için işlemine tıkla.

![](https://lh4.googleusercontent.com/HMd5iKjIvm-f7Xi7xtecTsq56x1i15GjUkwCm5Z_83xMfOXDd2jabcCDyUwELf51IHseEeCk2WnvWfHwTSUlFnLAJrmjkkOfm_fA5fimgdABnYfdjmBxxst8TOaUJUhc2iO_CN-k)

8\. **Nonce** girdisini bul ve bu numarayı not et.

### **3. Takılı Kalan İşlemin Üzerine Yaz**

Şimdi takılı kalanın yerini alacak yeni bir işlem yapacağız. Nonce numarasını, az önce not ettiğinle aynı olacak şekilde özelleştireceğiz.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28176%29.png)

9\. Takılı kalan işlemin yerine geçecek yeni bir işlem oluştur. Bu sefer **Transaction Fee** değerini artır. Burada 9'dan 20'ye çıkardık. Bu, işleminin bir bloğa eklenme olasılığını artırır.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2834%29.png)

10\. Onay sayfasında Gas Price değerinin artık yeni, daha yüksek miktarda olduğundan emin ol.

11\. **CUSTOM NONCE** girdisini bul ve nonce'u 8. adımda not ettiğin numarayla değiştir. Şimdi Confirm'e tıkla.

![](https://lh6.googleusercontent.com/PYhYm2ro0SVzerBo5qguFIPOYl0DjLSfl0JT8UdfN3T4i-0hjBq-CQvr-UA0bSyG-ZndrWmLGptfZUcnGBlvUk118GGZn7ciDNaC4hmfovH9v_M5XMIYmkAmB-Fr-6TTpYnnDX1p)

12\. Yeni işlemin artık bir bloğa kabul edilmiş olmalı. Kontrol etmek için MetaMask'i aç ve **Activity** sekmesine tıkla.

![](https://lh6.googleusercontent.com/Iw3e0YP4ORhPgw8-MNxvzlDlfgG5nD226P4ixiziPC_9j3_LfU3o1-_LA2yDmegbRw5x9Sgk3RACFJJkyJDrFJA1j2J93H21uGhhWabkdDQUHsU_oVdkZVQTTWaQPzXHAWClpsb4)

13\. Tamamlanan işlemin Activity listenin en üstünde görünmeli. Hâlâ turuncu renkte “Pending” yazıyorsa biraz daha beklemen veya süreci daha da yüksek bir işlem ücretiyle (gas price) yeniden denemen gerekir.

Hiçbir cüzdan aynı nonce'a sahip iki işlem oluşturamayacağı için, yaptığın yedek işlem başarılı olursa takılı kalan işlemin iptal edilir.<br>
