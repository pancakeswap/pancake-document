# Piyango SSS

## Kazanan çıkmazsa ne olur?

Ödül havuzundaki CAKE kazanılmazsa boşa gitmez! Talep edilmeyen CAKE bir sonraki Piyango turuna aktarılır.

## Biletim birkaç sayıyı eşleştiriyor ama ödül talep edemiyorum

Biletler yalnızca soldan sağa doğru sayıları eşleştirirse ödüle hak kazanır. Kapsamlı bir açıklama için [Piyango v2 belgelerine](./){.}bakabilirsin.

## Piyango v2, Piyango v1'den nasıl farklı?

Piyango v2, ödülleri Piyango v1'e göre daha geniş bir kitleye dağıtır. Her bilete ilk sayıyı eşleştirmek için 10'da 1 şans tanır; bu da daha fazla biletin en azından küçük bir ödül kazanmasını sağlar. Ayrıca en büyük ödülü kazanmak için sırayla eşleştirilmesi gereken 6 sayı vardır (v1'de 4'tü).

Genel olarak bu durum daha fazla biletin ödül kazanabileceği anlamına gelir, ancak en büyük ikramiye daha seyrek kazanılacağından muazzam büyüklükte en iyi ödül havuzları oluşacaktır!

**Piyango v2 şunları sunar:**

* CAKE'in fiyatıyla aşırı dalgalanmayan daha ucuz bilet fiyatları (bilet başına CAKE cinsinden yaklaşık 5 USD)
* toplu bilet indirimleri
* eşleşen sayı arttıkça büyüyen ödül havuzlarıyla 6 kademeli ödül dilimi
* manuel numara seçimi (isteğe bağlı), böylece kullanıcılar şanslı numaralarını kullanabilir
* gerçek ve güvenli rastgelelik için [Chainlink'in VRF uygulaması](https://docs.chain.link/docs/chainlink-vrf/)
* genel olarak daha düşük ücretler (daha fazla bilgi için [bu sayfanın aşağısına bakabilirsin](lottery-faq.md#what-transaction-fee-will-i-pay-for-buying-tickets))

[Piyango v2 özellikleri, oynanışı ve ödülleri hakkında daha fazla bilgi al](./)

## Ödüller dilimler arasında nasıl bölüştürülür?

Her dilimin ödül havuzu, her Piyango turundaki toplam CAKE'in bir bölümüdür.

* | Dilim (sırayla eşleşen sayı sayısı) | CAKE Tahsisi |
  | ----------------------------------- | ------------ |
  | İlk 1 sayı                          | %2           |
  | İlk 2 sayı                          | %3           |
  | İlk 3 sayı                          | %5           |
  | İlk 4 sayı                          | %10          |
  | İlk 5 sayı                          | %20          |
  | İlk 6 sayı                          | %40          |
  | Yakma                               | %20          |

## Biletlerimi CAKE'e geri çevirebilir miyim?

Hayır, satın aldıktan sonra biletini CAKE'e dönüştüremezsin.

## Kazanırsam ödülü manuel olarak talep etmem gerekir mi?

Evet, Piyango sayfasındaki "Kazanan mısın?" bölümünün altındaki **Şimdi Kontrol Et** düğmesine tıklaman gerekir.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2868%29.png)

## Piyango ne sıklıkla düzenlenir?

Her 12 veya 36 saatte bir Piyango çekilişi gerçekleşir. Her gün bir çekiliş yapılır; 0:00 UTC ve 12:00 UTC arasında dönüşümlü olarak gerçekleşir. 0:00 UTC turlarından sonraki turlar 36 saat sonra, 12:00 UTC turlarından sonraki turlar ise 12 saat sonra başlar.

![Lottery injection schedule](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Lottery%20Schedule%20Update%20Feb%204.png)

## Bilet satın almak için hangi işlem ücretini öderim?

Her bilet satın alman bir işlem sayılır. Bir Piyango alımında tek bir bilet satın almak normal işlem ücreti kadar tutar.

Ancak o alımda daha fazla bilet almak ücreti artırır. 1 yerine 100 bilet almak ücreti 100 katına çıkarmaz ama yaklaşık 5-6 kat artırabilir (bu durum değişkenlik gösterir).

## Toplu indirim nasıl çalışır?

Toplu indirim, daha fazla bilet satın almayı kademeli bir indirimle ödüllendirir. Yalnızca 2 bilet alıyorsan indirim ihmal edilebilir düzeydedir, ancak tek işlemde satın aldığın bilet sayısını artırdıkça hızla birikir.

İndirim yalnızca 100 bilete kadar olan her işlem için geçerlidir. İndirim bir sonraki işleme veya tura taşınmaz.

## Neden yalnızca 100 bilet satın alabiliyorum?

Tek bir alımda en fazla 100 bilet satın alabilirsin, ancak birden fazla alım yapabilirsin. İlk 100 biletten sonra daha fazla bilet almana engel olan hiçbir şey yok.

## Aynı numaralara sahip iki veya daha fazla bilet manuel olarak oluşturursan ve kazanırlarsa, her bilet için ödüle hak kazanır mısın?

Evet, her bilet Piyango'ya ayrı bir giriş olarak değerlendirilir. Ancak ödüllerin 1:1 olmayacağını unutma; zira sahip olduğun her kazanan bilet, dilimin toplam ödülündeki her payı düşürür.

## Enjeksiyon takvimi: Piyango'ya CAKE ne zaman eklenir?

Kullanıcılar bilet satın aldığında, harcadıkları CAKE Piyango havuzuna eklenir. Bunun yanı sıra, yukarıdaki Piyango takvim şeklinde gösterildiği gibi haftada yedi tur boyunca düzenli bir takvimde her iki turda bir Piyango havuzuna 8.000 CAKE daha eklenir (enjekte edilir).
