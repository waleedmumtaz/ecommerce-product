<script>
  import IconCart from './IconCart.svelte'
</script>

<div>
  <div class="p-5">
    <p
      class="text-xs font-bold uppercase tracking-widest text-cstm-primary-orange"
    >
      Sneaker Company
    </p>
    <p class="py-3 text-2xl font-bold">Fall Limited Edition Sneakers</p>
    <p class="text-cstm-neutral-dark-grayish-blue">
      These low-profile sneakers are your perfect casual wear companion.
      Featuring a durable rubber outer sole, they’ll withstand everything the
      weather can offer.
    </p>
    <div class="flex items-center justify-between py-5">
      <div class="flex items-center gap-5">
        <p class="text-2xl font-bold">$125.00</p>
        <p
          class="rounded-md bg-cstm-primary-pale-orange px-2 font-bold text-cstm-primary-orange"
        >
          50%
        </p>
      </div>
      <p class="font-bold text-cstm-neutral-grayish-blue line-through">
        $250.00
      </p>
    </div>
    <div
      class="mb-5 flex items-center justify-between rounded-md bg-cstm-neutral-light-grayish-blue p-4"
    >
      <button><img src="/assets/icon-minus.svg" alt="minus icon" /></button>
      <p>0</p>
      <button><img src="/assets/icon-plus.svg" alt="plus icon" /></button>
    </div>
    <button
      class="flex w-full items-center justify-center gap-3 rounded-md bg-cstm-primary-orange py-3 font-bold text-white shadow-lg"
      ><span><IconCart fillColor="white" /></span> Add to cart</button
    >
  </div>
</div>
