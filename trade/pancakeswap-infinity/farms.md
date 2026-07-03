# Farm'lar

PancakeSwap Infinity farming, kullanıcıların LP token'larını stake etmelerine gerek kalmadan likidite ödülleri kazanmalarının basit ve gaz tasarruflu bir yoludur. Uygun bir havuza likidite eklendikten sonra ödüller otomatik olarak birikimeye başlar.

#### ⚙️ Nasıl Çalışır

Sistemin ödülleri nasıl takip ettiğine ve dağıttığına dair hızlı bir özet:<br>

**✅ Staking Gerekmiyor**

* LP pozisyonunu cüzdanında tutman yeterli.
* Varlıklarını kilitlemen veya ek akıllı sözleşmelerle etkileşime girmen gerekmiyor.
* Likidite eklediğinde ödüller otomatik olarak kazanılmaya başlar.

#### 📈 Ödül Dağıtımı

* Yalnızca aralık içindeki pozisyonlar (aktif likidite sağlayanlar) ödül alır.
* Ödüller, dönem olarak adlandırılan her dönemde pozisyonun kazandığı ücretlerle orantılıdır.

#### ⏳ Dönem Nedir?

* Dönem, sabit bir zaman dilimidir; şu anda 8 saat olarak ayarlanmıştır.
* Ödüller her dönemin ardından hesaplanır ve dağıtılır.
* Dönemler şu anda UTC 00:00, 08:00 ve 16:00'de planlanmıştır.

***

#### 🔄 Farming ve Talep Süreci

1. **Pozisyonların Takibi:** Arka uç sistemi tüm farm'lardaki LP pozisyonlarını izler.
2. **Ödül Hesaplama:** Her dönemin sonunda,
   1. Sistem, likiditene ve elde edilen ücretlere göre ödüllerini hesaplar.
   2. Ödülleri bir Merkle ağacında işler ve bir akıllı sözleşmeye Merkle kökü gönderir.
3. **İtiraz Süreci:**
   1. Merkle kökü yayınlandıktan sonra 1 saatlik itiraz süresi başlar.
   2. İtiraz süresi boyunca:
      1. Yeni hesaplanan ödüller talep edilemez.
      2. Önceki dönemlere ait ödüller talep için kullanılabilir kalmaya devam eder.
      3. Otomatik ve topluluk tarafından işletilen doğrulama araçları, yayınlanan verilerin doğruluğunu kontrol eder. Tutarsızlıklar tespit edilirse, hatalı dağıtımları önlemek amacıyla bir itiraz kaldırılabilir.
4. **Ödüllerin Talep Edilmesi:**
   1. İtiraz süresi sona erdiğinde, en son dönem için ödüllerini talep edebilirsin.
   2. Tüm farm'lardaki bekleyen ödüller tek, gaz tasarruflu bir işlemde talep edilebilir.
5. **Talep Edilmeyen Ödüller Sonraki Döneme Devredilir:**
   1. Talep edilmemiş ödüller sonraki dönemlere devredilir. Her güncelleme önceki ödülleri kapsar; böylece hiçbir kazanç kaybolmaz veya sona ermez.

{% hint style="info" %}
Daha dar likidite aralıkları genellikle daha yüksek kazanç sağlar, ancak pozisyonun aralık dışına çıkma ve ödüller için uygun olmama ihtimalini artırır.
{% endhint %}

#### 🌱 Özet

✅ Staking yok\
✅ Gaz tasarruflu talep\
✅ Düzenli ödül güncellemeleri\
✅ Adil ve şeffaf itiraz süreci\
✅ Ödüller talep etmeye hazır olana kadar birikir
