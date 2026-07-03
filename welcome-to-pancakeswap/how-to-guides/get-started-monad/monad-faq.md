# Monad SSS

#### 1. PancakeSwap likidite havuzlarında hangi ücret kademeleri mevcut?

**Desteklenen Ücret Kademeleri:**

* V3 (yoğunlaştırılmış likidite) havuzları için aşağıdaki ücret kademeleri mevcuttur: `0.01%, 0.05%, 0.25%, 1%`&#x20;
* V2 havuzları için yalnızca %0,25 ücret kademeli havuzlar desteklenmektedir

#### 2. Herkes havuz oluşturabilir mi?

Evet. Havuz oluşturma birkaç istisna dışında izinsizdir:

* Belirli bir **token çifti + ücret kademesi** kombinasyonu için yalnızca bir havuz var olabilir (örn. aynı anda yalnızca bir WMON <> USDC %0,05 havuzu olabilir)

#### 3. Yeni oluşturulan bir havuzun görünmesi ne kadar sürer?

* Havuzlar genellikle oluşturulduktan yaklaşık **5 dakika** sonra havuz listesinde görünür.
* Görünmezse:
  * Manüel olarak bulmak için **arama çubuğunu** kullan.
  * Havuzlar **düşük TVL** nedeniyle listeden filtrelenmiş olabilir.

#### 4. Havuzumun APR veya TVL'si neden hâlâ sıfır gösteriyor?

Bu, yeni bir havuz oluşturulduğunda beklenen bir durumdur:

* APR ve TVL verileri yalnızca havuzda **en az bir Swap** gerçekleştikten sonra görünecektir.
* Bir Swap gerçekleştikten sonra bu metrikler yaklaşık **15 dakika** içinde gösterilmeye başlar.

#### **5. Cüzdanımda 10 MON'dan az varsa işlemlerim neden bazen başarısız oluyor?**

Monad'ın her hesabın **minimum 10 MON güvenlik tamponu** tutması gerektiğine dair bir kuralı var. Bakiyen düşükse ve çok kısa sürede çok fazla işlem gönderirsen, ağ **yenilerini kabul etmeyi durdurabilir**.

#### **6. İlk 1-2 işlem neden çalışıyor, ama sonrakiler neden başarısız oluyor?**

Monad, blokları bakiyenin biraz "gerisinde" kalan bir görünümle işler. Yani:

* **İlk** işlemin genellikle sorunsuz geçer.
* **İkinci** işlemin de geçebilir.
* Ancak **kısa süre içinde birden fazla işlem** gönderirsen, ağ tüm gas ücretlerini karşılayacak kadar MON'unun olmayabileceğini düşünür.

Bu nedenle bir sonraki işlemi **engeller**. Bu normaldir ve güvenlik sisteminin bir parçasıdır.

#### **7. Akıllı hesaplarda (kontrat cüzdanları) neden daha kısıtlayıcı hissettiriyor?**

Akıllı hesaplar **daha katı kurallara** tabidir:

* Kontrat kodu çalışırken **her zaman** en az **10 MON** tutmaları gerekir.
* Akıllı hesabın 10 MON'un altındaysa, EOA'lar hâlâ birkaç işlem için çalışsa bile işlem **anında geri alınabilir**.

Bu nedenle akıllı hesap kullanıcıları başarısızlıklarla daha erken karşılaşır.

#### **8. Bu, Monad'ı 10 MON'dan az ile kullanamayacağım anlamına mı geliyor?**

Normal bir EOA ile _kullanabilirsin_ — ancak:

* Arka arkaya birden fazla işlem gönderme.
* İşlemler arasında birkaç blok bekle.
* Sorunlardan kaçınmak için cüzdanında biraz MON bulundur.

#### **9. Bu başarısızlıklardan nasıl kaçınabilirim?**

Basit ipuçları:

* Mümkünse cüzdanında **10 MON veya daha fazlasını** tut.
* MON'un azsa, **işlemleri aralıklı olarak gönder** (spam yapma).
* Akıllı hesap kullanıcıları kontrat çağrıları ekstra gas kullandığından **10 MON'dan biraz fazlasını** tutmalıdır.
