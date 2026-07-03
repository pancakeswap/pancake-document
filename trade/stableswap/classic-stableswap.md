# Classic StableSwap

Classic StableSwap adalah implementasi AMM Curve Finance di PancakeSwap. Ini menambahkan kurva constant sum linier (x+y=k) di atas formula constant product (x\*y=k) untuk menjaga harga tetap lebih setara selama Pool Likuiditas tidak sangat tidak seimbang. Akibatnya, karena StableSwap dibatasi pada aset dengan harga serupa, impermanent loss tidak menjadi perhatian sebesar itu (kecuali dalam kasus depeg yang ekstrem) dan Slippage-nya lebih rendah dari AMM normal yang hanya menggunakan formula constant product.

Saat Anda melakukan Swap (perdagangan) di StableSwap, Anda akan membayar biaya trading yang lebih rendah, dibandingkan dengan 0,25% biasa pada AMM PancakeSwap normal. Pembagian biaya adalah sebagai berikut:

* 50% untuk LP sebagai hadiah&#x20;
* 40% untuk pembelian kembali dan pembakaran CAKE&#x20;
* 10% untuk Treasury PancakeSwap

## Biaya StableSwap

Biaya untuk pasangan dirinci dalam tabel di bawah ini:

<table><thead><tr><th width="150">Pasangan Stabil</th><th width="132">Biaya Trading</th><th width="118.33333333333331">Hadiah LP</th><th width="124">Pembelian Kembali CAKE</th><th>Treasury PancakeSwap</th></tr></thead><tbody><tr><td>USDT-BUSD</td><td>0,01%</td><td>0,005%</td><td>0,004%</td><td>0,001%</td></tr><tr><td>USDC-BUSD</td><td>0,01%</td><td>0,005%</td><td>0,004%</td><td>0,001%</td></tr><tr><td>USDC-USDT</td><td>0,01%</td><td>0,005%</td><td>0,004%</td><td>0,001%</td></tr><tr><td>HAY-BUSD</td><td>0,04%</td><td>0,02%</td><td>0,016%</td><td>0,004%</td></tr><tr><td>HAY-USDT</td><td>0,04%</td><td>0,02%</td><td>0,016%</td><td>0,004%</td></tr><tr><td>axlUSDC-USDT</td><td>0,04%</td><td>0,02%</td><td>0,016%</td><td>0,004%</td></tr><tr><td>BNBx-WBNB</td><td>0,04%</td><td>0,02%</td><td>0,016%</td><td>0,004%</td></tr><tr><td>stkBNB-WBNB</td><td>0,04%</td><td>0,02%</td><td>0,016%</td><td>0,004%</td></tr></tbody></table>

The Kitchen akan secara bertahap meluncurkan pasangan StableSwap dan merevisi biaya untuk menguji dan meningkatkan produk lebih lanjut.

## Mengapa saya harus menggunakan StableSwap alih-alih AMM Swap biasa?

* Swap stablecoin Anda atau pasangan lain dengan harga aset serupa secara lebih efisien dengan langkah perdagangan yang sama&#x20;
* Dengan fungsi StableSwap, Slippage trading lebih rendah dari AMM biasa&#x20;
* Biaya trading StableSwap lebih rendah dibandingkan AMM biasa

