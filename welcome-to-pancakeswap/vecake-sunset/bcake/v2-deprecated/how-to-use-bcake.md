# Как использовать bCAKE?

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-use-bCAKE.png)

Как и iCAKE и vCAKE, bCAKE — это также преимущество, разработанное для пользователей, блокирующих CAKE в фиксированном пуле стейкинга CAKE. Мультипликатор буста рассчитывается на основе количества стейканого CAKE, срока стейкинга, а также количества токенов LP в ферме, которую ты хочешь забустить.

## Подготовка

### Создай фиксированную позицию стейкинга CAKE

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bCAKE-no-cake-locked.png)

Если ты ещё не заблокировал CAKE в пуле стейкинга CAKE, нажми «Go to Pool» и следуй инструкциям для создания фиксированной позиции стейкинга.

Чтобы узнать больше о фиксированном стейкинге CAKE, читай [здесь](../../../../archive/legacy-products/new-cake-pool/#fixed-term-staking).

### Включи farm boosters

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bCAKE-enable-booster.png)

Для включения farm boosters необходимо пройти одноразовую настройку. Просто нажми «Enable» и подтверди транзакцию в кошельке.

### Мигрируй свои стейкинги

{% hint style="info" %}
Если ты в данный момент не стейкаешь в ферме, для которой хочешь активировать bCAKE, этот шаг можно пропустить и начать со стейкинга токенов LP в ферме.
{% endhint %}

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bCAKE-staking-migration-needed.png)

Если ты стейкаешь в ферме, для которой хочешь активировать farm booster, также требуется одноразовая миграция стейкинга.

Нажми «Migrate» и следуй пошаговому руководству для завершения миграции. Твои вознаграждения CAKE будут автоматически собраны и отправлены в твой кошелёк.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bCAKE-migration-inprogress.png)

## Активируй бустеры

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bCAKE-pending-activation%20%281%29.png)

После готовности ты увидишь доступный мультипликатор буста и забустенный APR для фермы, в которой сейчас стейкаешь. Чтобы узнать больше о том, как рассчитывается мультипликатор bCAKE, читай [здесь](../faq.md#how-are-the-bcake-multipliers-calculated).

Для активации буста нажми кнопку «Boost» и подтверди транзакцию в кошельке.

{% hint style="info" %}
Обрати внимание, что любые действия пользователя с фермами или пулом стейкинга CAKE автоматически обновят твой мультипликатор буста на основе актуальных данных и статистики ферм и пула стейкинга CAKE.

Узнай больше [здесь](../faq.md#why-do-my-multipliers-change-even-after-activation).
{% endhint %}

### ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bCAKE-farm-number-limit.png)

Существует ограничение на количество ферм, которые можно бустить одновременно. Для проверки количества оставшихся бустеров обратись к панели вверху.

Необходимо отключить активный бустер, чтобы активировать бустеры на других фермах.

## Отключи бустеры

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bCAKE-pending-unset%20%281%29.png)

Для отключения farm booster просто нажми кнопку «Unset» и подтверди транзакцию в кошельке.

Обрати внимание: при отключении заработанный CAKE будет собран в контракт farm booster и автоматически отправлен в твой кошелёк при следующем сборе, депозите или выводе. Узнай больше [здесь](../faq.md#where-are-my-cake-rewards-after-activating-or-unsetting-the-booster).
