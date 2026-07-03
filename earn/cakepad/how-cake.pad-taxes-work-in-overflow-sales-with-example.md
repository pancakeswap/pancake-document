# CAKE.PAD Vergileri Taşma Satışlarında Nasıl Çalışır – Örnekle

1. Vergiler yalnızca **CAKE.PAD etkinliği aşırı talep gördüğünde** alınır
   1. Aşırı talep = Tüm kullanıcıların toplam yatırımları > Hedef toplama miktarı.
   * Vergi yalnızca katılımcıların fazla taahhüt edilen fonlarından düşülür. CAKE.PAD ortak projesi herhangi bir ücret ödemez.
   * CAKE.PAD ortak projesi, hedeflenen toplama miktarının %100'ünü alır.
   * CAKE.PAD vergileri CAKE cinsinden toplanır ve %100'ü yakılır.
   * Ücretler **havuzun toplam abonelik oranına** göre belirlenir (toplama hedefinin yüzdesi):

**Aşırı Talep Oranı <> Ücret Kademesi**&#x20;

<table data-full-width="false"><thead><tr><th>Aşırı Talep Oranı</th><th>Ücret Kademesi</th></tr></thead><tbody><tr><td>≥ 0x</td><td>%1,00</td></tr><tr><td>≥ 50x</td><td>%0,80</td></tr><tr><td>≥ 100x</td><td>%0,60</td></tr><tr><td>≥ 150x</td><td>%0,50</td></tr><tr><td>≥ 200x</td><td>%0,40</td></tr><tr><td>≥ 250x</td><td>%0,30</td></tr><tr><td>≥ 300x</td><td>%0,25</td></tr><tr><td>≥ 400x</td><td>%0,20</td></tr><tr><td>≥ 500x</td><td>%0,15</td></tr><tr><td>≥ 650x</td><td>%0,12</td></tr><tr><td>≥ 800x</td><td>%0,10</td></tr><tr><td>≥ 1500x</td><td>%0,05</td></tr></tbody></table>



2. **Zaman dilimi – Vergi ne zaman alınır**

* Vergi, kullanıcı tahsisini talep ettiğinde **CAKE.PAD etkinliğinin sonunda** alınır.
* Bir kullanıcı erken abone olsa bile (örneğin abonelik toplama hedefinin %30'undayken), nihai vergi **havuzun nihai aşırı talep seviyesine** göre hesaplanır.
  * Örnek: Havuz 50x aşırı talep gördüğünde uygulanan vergi 50x kademesidir (%0,8).

#### Hesaplama Adımları

1.  **Kullanıcı tahsisi** = Kullanıcının aldığı toplam CAKE.PAD ortak token havuzunun yüzdesi

    ```jsx
    user_allocation = user_deposit_amount / totalAmountPool
    ```
2.  **Kullanıcı ödeme miktarı** = Kullanıcının CAKE.PAD ortak token'larını talep etmek için kullandığı yatırım kısmı

    ```jsx
    user_pay_amount = raisingAmountPool * user_allocation
    ```
3.  **İade miktarı** = Kullanıcının CAKE.PAD ortak token satın alımı için kullanılmayan yatırım fazlası

    ```jsx
    refund_amount = user_deposit_amount - user_pay_amount
    ```
4.  **Vergi miktarı** = Kullanıcının iade edilen miktarına uygulanan kesinti

    * Ücret kademesi, toplama hedefinin yüzdesine göre belirlenir (yukarıdaki tabloya bak).

    ```jsx
    tax_amount = fee tier * refund_amount
    ```
5.  **Kullanıcı için nihai çıktı**

    ```jsx
    1. Token tahsisi = user_allocation * totalTokensOffered
    2. Kullanıcı vergi miktarı = tax_amount
    3. final_refund = refund_amount - tax_amount (uygulanabilirse, aksi hâlde = refund_amount)
    ```

#### Sayısal Örnek

* **Hedef toplama (raisingAmountPool):** 100 CAKE
* **Yatırımın (user\_deposit\_amount):** 10 CAKE
* **Yatırımın dahil olduğu toplam yatırımlar (totalAmountPool):** 5.100 CAKE (51x abone = toplama hedefinin %5.100'ü, 50x aşırı talep anlamına gelir)
  * Karşılık gelen ücret kademesi = %0,80 (yukarıdaki vergi oranı tablosuna göre)

**Adımlar:**

1. `user_allocation = 10 / 5.100 = 0,00196 (%0,196 havuz tahsisi)`
2. `user_pay_amount = 100 × 0,00196 = 0,196 CAKE`
3. `refund_amount = 10 − 0,196 = 9,804 CAKE`
4. `tax_amount = 9,804 × 0,008 = 0,0784 CAKE`
5. `final_refund = 9,804 − 0,0784 = ~9,72 CAKE`

**Kullanıcının nihai aldıkları**

1. **Token tahsisi:** 0,196 CAKE değerinde CAKE.PAD ortak token'ları
2. **Nihai iade:** ~9,72 CAKE (10 CAKE yatırımından − 0,196 CAKE token tahsisi için − 0,0784 CAKE vergi)
