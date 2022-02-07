<script>
  import { cart } from '../stores'
  import IconCart from './IconCart.svelte'

  let itemsCount = 0

  const incrementItemsCount = () => {
    return itemsCount++
  }

  const decrementItemsCount = () => {
    if (itemsCount > 0) {
      return itemsCount--
    }
  }

  const addItemsToCart = () => {
    if (itemsCount > 0) {
      const item = {
        id: Date.now(),
        name: 'Fall Limited Edition Sneakers',
        price: 125,
        quantity: itemsCount,
      }

      $cart = [...$cart, item]
    }
  }
</script>

<div>
  <div class="p-5">
    <p
      class="text-cstm-primary-orange text-xs font-bold uppercase tracking-widest"
    >
      Sneaker Company
    </p>
    <p class="py-3 text-2xl font-bold md:text-5xl">
      Fall Limited Edition Sneakers
    </p>
    <p class="text-cstm-neutral-dark-grayish-blue">
      These low-profile sneakers are your perfect casual wear companion.
      Featuring a durable rubber outer sole, they’ll withstand everything the
      weather can offer.
    </p>
    <div class="flex items-center justify-between py-5 md:my-3 md:block">
      <div class="flex items-center gap-5">
        <p class="text-2xl font-bold md:text-3xl">$125.00</p>
        <p
          class="bg-cstm-primary-pale-orange text-cstm-primary-orange rounded-md px-2 font-bold"
        >
          50%
        </p>
      </div>
      <p class="text-cstm-neutral-grayish-blue font-bold line-through">
        $250.00
      </p>
    </div>
    <div class="md:flex md:items-center md:gap-5">
      <div
        class="bg-cstm-neutral-light-grayish-blue mb-5 flex items-center justify-between rounded-md p-4 md:mb-0 md:w-2/5"
      >
        <button on:click|preventDefault={decrementItemsCount}
          ><img
            src="/assets/icon-minus.svg"
            alt="minus icon"
            class="hover:opacity-50"
          /></button
        >
        <p class="font-bold">{itemsCount}</p>
        <button on:click|preventDefault={incrementItemsCount}
          ><img
            src="/assets/icon-plus.svg"
            alt="plus icon"
            class="hover:opacity-50"
          /></button
        >
      </div>
      <button
        on:click|preventDefault={addItemsToCart}
        class="bg-cstm-primary-orange flex w-full items-center justify-center gap-3 rounded-md py-3 font-bold text-white shadow-lg hover:opacity-75 md:flex-1 md:py-4"
        ><span><IconCart fillColor="white" /></span> Add to cart</button
      >
    </div>
  </div>
</div>
