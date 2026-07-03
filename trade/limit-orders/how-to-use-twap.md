# TWAP Nasıl Kullanılır

## TWAP Nedir?

TWAP (Zaman Ağırlıklı Ortalama Fiyat), CeFi'de yaygın olarak kullanılan ve bir emri daha küçük işlem boyutlarına bölerek bunları düzenli aralıklarla gerçekleştiren bir emir türüdür. TWAP emrinin temel amacı emrin fiyat etkisini azaltmaktır. Ayrıca bir kullanıcının dolar-maliyet ortalaması (DCA) stratejisi uygulamak ve belirli bir tokeni tutarlı bir programa göre (ör. ayda bir) satın almak istemesi durumunda da faydalı olabilir.

Bu nedenle TWAP, emir boyutu mevcut likiditeyle kıyaslandığında büyük olduğunda ya da kullanıcı net bir yükseliş veya düşüş trendi olmaksızın yüksek fiyat oynaklığı beklediğinde en iyi şekilde kullanılır.

## TWAP emri nasıl kurulur?

1. Swap sayfasına git ve TWAP'a tıklayarak TWAP emri seçeneğini seç
2. "Kaynak" ve "Hedef" tokenları seç ve işlem yapmak istediğin miktarı gir.
3. Arayüz hem dTWAP-piyasa emirlerini (tüm işlemleri mevcut piyasa fiyatından gerçekleştiren) hem de dTWAP-limit emirlerini (yalnızca kullanıcının belirlediği fiyat sınırı dahilindeyse bireysel işlemleri gerçekleştiren) destekler. \
   Bu örnekte TWAP emirlerini piyasa fiyatından gerçekleştirmeyi seçtik.
4. Ardından TWAP parametrelerini belirliyoruz. dTWAP emrinin etkinliğini kontrol eden 3 temel parametre vardır:
   1. Toplam işlemler: Kullanıcının emrinin bölüneceği bireysel işlem sayısını belirlemesine olanak tanır. Arayüz kaydırıcısı 1 işlemle başlar ve kullanıcının bireysel işlem miktarını artırmasına ya da giriş alanına toplam işlemleri doğrudan manuel olarak girmesine olanak tanır.\
      Kullanıcılar bu parametreyi belirlerken belirli bir ödünleşim olduğunu unutmamalıdır: daha fazla işlem, daha küçük bireysel işlem boyutu anlamına gelir; bu da daha küçük fiyat etkisi demektir. Ancak daha fazla işlem aynı zamanda daha fazla işlem ve daha yüksek toplam gaz ücreti anlamına da gelir.&#x20;
   2. İşlem Aralığı: Her bireysel işlem arasındaki zaman boşluğunu belirler. Arayüz, her parça arasında alıcı açık artırması ve blok uzlaşması için gereken minimum süreye izin veren minimum izin verilen değerle (2 dakika) başlar. Kullanıcı bunu istenen herhangi bir süreye ayarlayabilir. Bir işlem, önceki işlemden sonra bu süre geçmeden asla gerçekleştirilmez.\
      Kullanıcılar bu parametreyi ayarlarken dikkatli olmalıdır: daha uzun aralıklar, arbitrajcılara etkilenen havuzlardaki fiyat farklılıklarını kapatmak ve rezervleri dengeye döndürmek (spot fiyatla aynı seviyeye getirmek) için daha uzun bir pencere tanır. Ancak bu, emrin doldurulmasının daha uzun sürmesi anlamına gelir ve özellikle yüksek oynaklık dönemlerinde nihai dolum fiyatına belirsizlik ekler
   3. Maksimum Süre: Tam dTWAP emrini oluşturan tüm bireysel işlemlerin toplam miktarının gerçekleştirilebileceği maksimum süre. Bu son tarihten sonra, gerçekleştirilen gerçek miktarlardan bağımsız olarak işlem sona erer.\
      Limit emirlerde fiyatın belirlenen parametreler dahilinde kalıp kalmadığına bağlı olarak tüm parçaların gerçekleştirilmeyebileceğini unutma. \
      Önerilen varsayılan süre, aralık sayısıyla işlem aralığının çarpılmasıyla hesaplanır ve ardından bu miktar iki katına çıkarılarak zincir üzerindeki aktivite için yeterli zaman tanıyan bir tampon olarak kullanılır. (Yukarıdaki varsayılandan daha kısa bir süre belirlemenin kısmen doldurulmuş bir emirle sonuçlanabileceğini unutma).

Görüldüğü gibi bu parametreler, piyasa koşulları, mevcut gaz ücretleri gibi faktörleri göz önünde bulundurarak her emrin özelleştirilmesinde önemli bir esneklik sağlar.

8. "Emri Ver"e bas. Emir ayrıntılarını iki kez kontrol et, yasal uyarıyı kabul et ve "Emri Onayla"ya bas.
9. İşlem gerçekleştirildikten sonra, emrinin durumunu "Açık emirler" altındaki emir geçmişi bölümünde görebileceksin.
10. Açık emirler, emri genişletip "Emri İptal Et" düğmesine tıklayarak her zaman iptal edilebilir.

Dikkate alınması gereken hususlar

* Emirler, belirli bir süre içinde daha küçük işlemler halinde gerçekleştirilir ve piyasa koşullarına ve diğer risklere tabidir.
* İşlemin, mevcut piyasa fiyatından önemli ölçüde farklı bir fiyattan gerçekleştirilmesi mümkündür (her ne kadar belirlediğin limit fiyatından kötü olmasa da); bu da önemli kayıplara yol açabilir. Mevcut piyasa fiyatı belirlediğin limit fiyatından kötüyse, emrinin bazı işlemleri gerçekleştirilmeyebilir; bu da kısmen doldurulmuş bir emirle sonuçlanır.
* İşlemler, emirleri doldurmak için rekabet eden zincir dışı alıcılar kullanan merkezi olmayan bir protokole dayanır. Bu alıcılar ücret talep etme hakkına sahiptir; protokol bu ücreti kazanan alıcı için çıktı tokenlarından düşer.&#x20;
* Alıcılar, ücretlerini belirlerken işlemlerin gaz ücretlerini de hesaba katabilir; bu da ücret miktarlarında dalgalanmalara yol açabilir.

<br>
