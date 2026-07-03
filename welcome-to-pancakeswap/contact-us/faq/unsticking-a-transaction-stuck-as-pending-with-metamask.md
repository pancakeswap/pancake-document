---
description: MetaMask'ta beklemede takılı kalan işlemleri nasıl "çözeceğin" anlatılmaktadır
---

# MetaMask'ta Takılı Kalan Bekleyen İşlemleri Düzeltme

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-fix-a-stuck-transaction-header.png)

MetaMask'ta işlemin beklemede takılı kalıyorsa ve "İptal" butonu işe yaramıyorsa, birikmiş işlemleri temizlemek için bu yöntemi kullanman gerekebilir.

Bu yöntem, takılı kalan işlemi daha yüksek öncelikli başka bir işlemle üzerine yazarak çalışır.

### **1. Özelleştirilmiş İşlem Nonce'unu Etkinleştir**

1\. MetaMask eklentini aç.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-1-MetaMask_plugin.png)

2\. Sağ üstteki renkli daire simgesine tıkla ve açılır menüden **Ayarlar**'ı seç.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-2-MetaMask_settings%20%281%29.png)

3\. Ayarlar menüsünde **Gelişmiş** seçeneğini seç.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-3-MetaMask_advanced.png)

4\. **Gelişmiş gaz kontrolleri** görünene kadar aşağı kaydır. Bunu AÇIK konuma getir.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-4-MetaMask_gas_control_on.png)

5\. Hâlâ Gelişmiş ayarlardayken, **İşlem nonce'unu özelleştir** görünene kadar kaydırmaya devam et. Bunu AÇIK konuma getir.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-4-MetaMask_gas_control_on.png)

### **2. Takılı Kalan İşlemini Bul**

Şimdi takılı kalan işlemi bulacak ve "nonce"u not edeceğiz. Bu, daha sonra yeniden kullanacağımız bir tür tanımlayıcı.

![](https://lh4.googleusercontent.com/xKBEnt5a62c5Wzg_MCLIbVUWuL4fws1ohBAX9LAkGS71vslHk7QuMF24jAfkAdmsLunPVfT9c3FxCmGar5z7jNZnd4WMgzQsoxxbYw1Lp59Az5kG72COn0JblFXktHbmgMnF1LeY)

6\. MetaMask'ın ana sayfasına geri dön. "Varlıklar" sekmesinde, takılı kalan işleminin token türünü bul (bu örnekte CAKE).

![](https://lh5.googleusercontent.com/9qVjhK1kEKDL8l4TTdOFo4o547PDIIeQpCCY18gPyaUFJrpFbyYhMfBQ1CRzjjrllgrcqVbwkhxKCZBNlIad8J1yCpMVhsBKjIAcwfsQHQb7jnl2RD2ufQU-zNEn2Hn2g4LGvYDU)

6\. Token menüsünde, Kuyruk alanında **Bekleyen** işlemini bul. Daha fazla ayrıntı için işlemine tıkla.

![](https://lh4.googleusercontent.com/HMd5iKjIvm-f7Xi7xtecTsq56x1i15GjUkwCm5Z_83xMfOXDd2jabcCDyUwELf51IHseEeCk2WnvWfHwTSUlFnLAJrmjkkOfm_fA5fimgdABnYfdjmBxxst8TOaUJUhc2iO_CN-k)

7\. **Nonce** girişini bul ve bu sayıyı not et.

### **3. Takılı Kalan İşlemi Üzerine Yaz**

Şimdi takılı kalan işlemin yerine geçecek yeni bir işlem oluşturacağız. Nonce numarasını az önce yazdığın sayıyla aynı olacak şekilde özelleştireceğiz.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28176%29.png)

8\. Takılı kalan işleminin yerine geçecek yeni bir işlem oluştur. Bu sefer **İşlem Ücretini** artır. Burada 9'dan 20'ye çıkardık. Bu, işleminin bir bloğa eklenmesini daha olası kılar.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2834%29.png)

9\. Onay sayfasında, Gaz Fiyatının artık yeni ve daha yüksek tutarında olduğundan emin ol.

10\. **ÖZEL NONCE** girişini bul ve nonce'u 7. adımda yazdığın sayıya değiştir. Şimdi Onayla'ya tıkla.

![](https://lh6.googleusercontent.com/PYhYm2ro0SVzerBo5qguFIPOYl0DjLSfl0JT8UdfN3T4i-0hjBq-CQvr-UA0bSyG-ZndrWmLGptfZUcnGBlvUk118GGZn7ciDNaC4hmfovH9v_M5XMIYmkAmB-Fr-6TTpYnnDX1p)

11\. Yeni işlemin artık bir bloğa kabul edilmesi gerekir. Kontrol etmek için MetaMask'ı aç ve **Etkinlik** sekmesine tıkla.

![](https://lh6.googleusercontent.com/Iw3e0YP4ORhPgw8-MNxvzlDlfgG5nD226P4ixiziPC_9j3_LfU3o1-_LA2yDmegbRw5x9Sgk3RACFJJkyJDrFJA1j2J93H21uGhhWabkdDQUHsU_oVdkZVQTTWaQPzXHAWClpsb4)

12\. Tamamlanan işlemin Etkinlik listenin en üstünde görünmesi gerekir. Hâlâ turuncu renkte "Bekleyen" yazıyorsa biraz daha beklemen ya da daha yüksek işlem ücreti (gaz fiyatı) ile işlemi tekrar denemen gerekir.

Hiçbir Cüzdan aynı nonce'dan iki işlem oluşturamayacağından, yaptığın yerine geçen işlem başarılı olursa takılı kalan işlemi otomatik olarak iptal edilecektir.<br>
