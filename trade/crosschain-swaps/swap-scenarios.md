# 🔁 Swap Senaryoları

Cross-chain işlemler için 4 senaryo mevcuttur.

#### 1️⃣ Yalnızca Bridge

* Örnek: **Base'deki ETH'yi Arbitrum'daki ETH ile köprüle**
* Yalnızca desteklenen token'lar (USDC, USDT, WETH vb.) doğrudan köprülenebilir. Bu token'lar kaynak ve hedef zincire göre farklılık gösterir.

#### 2️⃣ Swap → Bridge

* Örnek: **BNB Chain'deki BNB'yi Arbitrum'daki USDC ile takas et**
* BNB Chain'deki PancakeSwap havuzlarını kullanarak BNB'yi desteklenen bir bridge token'ına (ör. USDC) takas et
* USDC'yi Across aracılığıyla Arbitrum'a köprüle

#### 3️⃣ Bridge → Swap

* Örnek: **BNB Chain'deki USDC'yi Arbitrum'daki ARB ile takas et**
* USDC'yi Across aracılığıyla köprüle
* Arbitrum'daki PancakeSwap havuzlarını kullanarak USDC'yi ARB ile takas et

#### 4️⃣ Swap → Bridge → Swap

* Örnek: **BNB Chain'deki BNB'yi Arbitrum'daki ARB ile takas et**
* BNB'yi bir bridge token'ına takas et (kullanıcı çıktısını maksimize ederek)
* Across aracılığıyla köprüle
* PancakeSwap havuzlarını kullanarak Arbitrum'da köprülenmiş token'ı ARB ile takas et

***

### ⚠️ Başarısız Durumlar

| Senaryo                                      | Sonuç                                                                                                                                                                                                                   |
| -------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Kaynak Zincirde Swap/İşlem Başarısızlığı** | Kullanıcı, kaynak zincirde orijinal token'ı anında geri alır                                                                                                                                                            |
| **Bridge İşlemi Başarısızlığı**              | Across, 90 dakika ile 2 saat içinde geri ödeme işlemi gerçekleştirir ve kullanıcı köprülenmiş varlığı kaynak zincirde geri alır. Relay ise SOL <> EVM arasındaki bu tür senaryolarda geri ödemeyi bir dakika içinde işler. |
| **Hedef Zincirde Swap Başarısızlığı**        | Kullanıcı, hedef zincirde köprülenmiş varlığı alır                                                                                                                                                                      |
