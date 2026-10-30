# 🧙 Page 1

## Cómo retirar tu NFT del PancakeSwap NFT Marketplace

Las páginas del PancakeSwap NFT Marketplace ya no están disponibles, pero el contrato inteligente del marketplace sigue activo. Si pusiste un NFT a la venta y nunca se vendió, sigue en poder del contrato del marketplace. Puedes recuperarlo tú mismo cancelando el listado directamente en BscScan.

Esto lleva unos minutos por NFT y solo cuesta una pequeña cantidad de BNB en gas.

### Antes de empezar

Necesitarás:

* **La misma billetera que usaste para listar el NFT.** Solo la billetera que creó un listado puede cancelarlo.
* **Una billetera de navegador** (por ejemplo, MetaMask, la extensión de Trust Wallet o la extensión de Binance Wallet) configurada en **BNB Smart Chain**.
* **Una pequeña cantidad de BNB** para pagar el gas. Cada NFT se retira en su propia transacción.

Ten a mano estas direcciones:

| Elemento                   | Dirección                                    |
| -------------------------- | -------------------------------------------- |
| Contrato del marketplace   | `0x17539cCa21C7933Df5c980172d22659B8C345C5A` |
| Colección Pancake Squad    | `0x0a8901b0E25DEb55A87524f0cC164E9644020EBA` |
| Colección Pancake Bunnies  | `0xDf7952B35f24aCF7fC0487D01c8d5690a60DBa07` |

> **Mantente seguro**
>
> * Interactúa únicamente con el contrato del marketplace `0x17539cCa21C7933Df5c980172d22659B8C345C5A`. Comprueba siempre la dirección en la URL de BscScan.
> * Retirar tu NFT **nunca** requiere enviar BNB ni tokens, ni firmar una aprobación (`approve` o `setApprovalForAll`). Si un sitio web o una persona te pide hacerlo, es una estafa.
> * PancakeSwap nunca te enviará mensajes directos ni te pedirá tu frase semilla.

### Paso 1: Encuentra los NFT que aún tienes listados

Para cada NFT que quieras retirar, necesitas dos datos: la **dirección de la colección** y el **ID del token**.

1. Abre la [página Read Contract](https://bscscan.com/address/0x17539cCa21C7933Df5c980172d22659B8C345C5A#readContract) del contrato del marketplace en BscScan.
2. Busca y expande **`viewAsksByCollectionAndSeller`**.
3. Rellena los campos:
   * `collection`: la dirección de la colección de la tabla anterior (por ejemplo, Pancake Squad es `0x0a8901b0E25DEb55A87524f0cC164E9644020EBA`)
   * `seller`: la dirección de tu billetera
   * `cursor`: `0`
   * `size`: `100`
4. Haz clic en **Query**.
5. Mira el resultado de `tokenIds`. Son los IDs de token que aún tienes listados en esa colección, y son los NFT que puedes retirar.
6. Si listaste NFT en más de una colección, repite los pasos 3 a 5 para cada colección.

**Si `tokenIds` está vacío (`[]`)**, no tienes listados activos en esa colección. Tu NFT se vendió (en cuyo caso ya recibiste los BNB) o cancelaste el listado antes (en cuyo caso ya está de vuelta en tu billetera).

**Si tienes más de 100 listados** en una colección, el último número del resultado es el siguiente cursor. Vuelve a consultar usando ese número como `cursor` para ver el resto.

**Si tu NFT es de una colección distinta de Pancake Squad o Pancake Bunnies**, expande **`viewCollections`** en la misma página, introduce `cursor = 0` y `size = 100`, y haz clic en **Query** para ver todas las colecciones que admite el marketplace.

### Paso 2: Retira tu NFT

1. Abre la [página Write Contract](https://bscscan.com/address/0x17539cCa21C7933Df5c980172d22659B8C345C5A#writeContract) del contrato del marketplace en BscScan.
2. Haz clic en **Connect to Web3** y conecta la misma billetera que listó el NFT. Asegúrate de que tu billetera esté en BNB Smart Chain.
3. Busca y expande **`cancelAskOrder`**.
4. Rellena los campos:
   * `_collection`: la dirección de la colección del Paso 1
   * `_tokenId`: el ID del token del Paso 1, como un número simple (por ejemplo `1234`)
5. Haz clic en **Write** y confirma la transacción en tu billetera. No envías ningún BNB; solo pagas el gas.
6. Cuando la transacción se complete, el NFT estará de vuelta en tu billetera.
7. Repite el proceso para cada NFT que quieras retirar.

Para confirmar que funcionó, ejecuta de nuevo el Paso 1. El ID del token ya no debería aparecer en la lista.

### Solución de problemas

| Problema                                                  | Qué significa y qué hacer                                                                                                                                                                                   |
| --------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Error: `Order: Token not listed`                          | La billetera conectada no listó este ID de token en esta colección, o el NFT ya se vendió o se retiró. Comprueba que usas la billetera original y la dirección de colección y el ID de token correctos. |
| El botón Write no hace nada                               | Probablemente tu billetera está en la red equivocada. Cambia a BNB Smart Chain y vuelve a conectar.                                                                                                         |
| Sin gas o fondos insuficientes                            | Añade una pequeña cantidad de BNB a tu billetera para cubrir el gas.                                                                                                                                        |
| Ya no tengo acceso a la billetera que listó el NFT        | Solo la billetera original puede cancelar el listado. Nadie, ni siquiera PancakeSwap, puede retirarlo en tu nombre.                                                                                         |
