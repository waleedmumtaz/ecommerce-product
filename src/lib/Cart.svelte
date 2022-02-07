<script>
  import { cart } from '../stores'

  const handleDelete = (id) => {
    const filteredCartItems = $cart.filter((item) => item.id !== id)
    $cart = filteredCartItems
  }
</script>

<div>
  <div class="flex min-h-[16rem] w-full flex-col rounded-md bg-white shadow-xl">
    <p class="p-5 font-bold">Cart</p>
    <hr />

    {#if $cart.length === 0}
      <!-- Empty cart -->
      <div
        class="text-cstm-neutral-dark-grayish-blue m-5 flex flex-1 items-center justify-center font-bold"
      >
        <p>Your cart is empty.</p>
      </div>
    {:else}
      <!-- Non-empty cart -->
      {#each $cart as cartItem}
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
                <p>{cartItem.name}</p>
                <p>
                  ${cartItem.price.toFixed(2)} x {cartItem.quantity}
                  <span class="font-bold"
                    >${(cartItem.price * cartItem.quantity).toFixed(2)}</span
                  >
                </p>
              </div>
            </div>
            <button on:click|preventDefault={() => handleDelete(cartItem.id)}>
              <img src="/assets/icon-delete.svg" alt="delete icon" />
            </button>
          </div>
          <div class="mt-8 px-5">
            <button
              class="bg-cstm-primary-orange mb-5 w-full rounded-md py-4 font-bold text-white hover:opacity-75"
              >Checkout</button
            >
          </div>
        </div>
      {/each}
    {/if}
  </div>
</div>
