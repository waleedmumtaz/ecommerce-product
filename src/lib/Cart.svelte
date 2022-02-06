<script>
  const handleDelete = () => {
    console.log('Delete clicked')
  }
</script>

<div>
  <div class="flex min-h-[16rem] w-full flex-col rounded-md bg-white shadow-lg">
    <p class="p-5 font-bold">Cart</p>
    <hr />

    <!-- Empty cart -->
    <!-- <div
      class="text-cstm-neutral-dark-grayish-blue m-5 flex flex-1 items-center justify-center font-bold"
    >
      <p>Your cart is empty.</p>
    </div> -->

    <!-- Non-empty cart -->
    <div>
      <div class="m-5 flex items-center justify-between">
        <div class="flex items-center gap-4">
          <div>
            <img
              src="/assets/image-product-1-thumbnail.jpg"
              alt="product thumbnail"
              class="w-14 rounded-md"
            />
          </div>
          <div class="text-cstm-neutral-dark-grayish-blue">
            <p>Autumn Limited Edition...</p>
            <p>$125.00 x 3 <span class="font-bold">$375.00</span></p>
          </div>
        </div>
        <button on:click|preventDefault={handleDelete}>
          <img src="/assets/icon-delete.svg" alt="delete icon" />
        </button>
      </div>
      <div class="mt-8 px-5">
        <button
          class="bg-cstm-primary-orange w-full rounded-md py-4 font-bold text-white"
          >Checkout</button
        >
      </div>
    </div>
  </div>
</div>
