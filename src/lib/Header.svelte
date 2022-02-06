<script>
  import { fade, fly } from 'svelte/transition'
  import Cart from './Cart.svelte'
  import IconCart from './IconCart.svelte'

  let navIsOpen = false
  let cartIsOpen = false

  const toggleNav = () => {
    navIsOpen = !navIsOpen
  }

  const toggleCart = () => {
    cartIsOpen = !cartIsOpen
  }
</script>

<header>
  <div class="relative">
    <!-- Tablet and desktop nav -->
    <nav class="hidden py-8 md:mx-auto md:block md:max-w-6xl md:border-b">
      <div class="flex items-center">
        <div class="flex w-full items-center justify-between">
          <div class="flex items-center gap-14">
            <img src="/assets/logo.svg" alt="logo" />
            <ul
              class="text-cstm-neutral-dark-grayish-blue flex items-center gap-10"
            >
              <li class="hover:text-cstm-neutral-very-dark-blue relative">
                <a
                  href="/#"
                  class="after:hover:bg-cstm-primary-orange after:hover:absolute after:hover:-bottom-12 after:hover:left-0 after:hover:h-1 after:hover:w-full"
                  >Collections</a
                >
              </li>
              <li class="hover:text-cstm-neutral-very-dark-blue relative">
                <a
                  href="/#"
                  class="after:hover:bg-cstm-primary-orange after:hover:absolute after:hover:-bottom-12 after:hover:left-0 after:hover:h-1 after:hover:w-full"
                  >Men</a
                >
              </li>
              <li class="hover:text-cstm-neutral-very-dark-blue relative">
                <a
                  href="/#"
                  class="after:hover:bg-cstm-primary-orange after:hover:absolute after:hover:-bottom-12 after:hover:left-0 after:hover:h-1 after:hover:w-full"
                  >Women</a
                >
              </li>
              <li class="hover:text-cstm-neutral-very-dark-blue relative">
                <a
                  href="/#"
                  class="after:hover:bg-cstm-primary-orange after:hover:absolute after:hover:-bottom-12 after:hover:left-0 after:hover:h-1 after:hover:w-full"
                  >About</a
                >
              </li>
              <li class="hover:text-cstm-neutral-very-dark-blue relative">
                <a
                  href="/#"
                  class="after:hover:bg-cstm-primary-orange after:hover:absolute after:hover:-bottom-12 after:hover:left-0 after:hover:h-1 after:hover:w-full"
                  >Contact</a
                >
              </li>
            </ul>
          </div>
          <div class="flex items-center gap-10">
            <button on:click={toggleCart}>
              <IconCart />
            </button>
            <img
              src="/assets/image-avatar.png"
              alt="avatar"
              class="hover:outline-cstm-primary-orange w-14 cursor-pointer rounded-full hover:outline hover:outline-2"
            />
          </div>
        </div>
      </div>
    </nav>

    <!-- Mobile nav -->
    <nav class="relative md:hidden">
      {#if navIsOpen}
        <div
          transition:fly={{ x: -50, duration: 500 }}
          class={`${
            navIsOpen
              ? 'absolute left-0 top-0 min-h-screen w-2/3 bg-white p-6'
              : 'hidden'
          }`}
        >
          <button on:click|preventDefault={toggleNav}>
            <img src="/assets/icon-close.svg" alt="close icon" class="mb-10" />
          </button>
          <ul class="space-y-4 text-lg font-bold">
            <li><a href="/#">Collections</a></li>
            <li><a href="/#">Men</a></li>
            <li><a href="/#">Women</a></li>
            <li><a href="/#">About</a></li>
            <li><a href="/#">Contact</a></li>
          </ul>
        </div>
      {/if}
      <div class="flex items-center justify-between p-5">
        <div class="flex items-center gap-4">
          <button on:click|preventDefault={toggleNav}>
            <img src="/assets/icon-menu.svg" alt="hamburger menu" />
          </button>
          <img src="/assets/logo.svg" alt="logo" />
        </div>
        <div class="flex items-center gap-6">
          <button on:click={toggleCart}>
            <IconCart />
          </button>
          <img src="/assets/image-avatar.png" alt="avatar" class="w-6" />
        </div>
      </div>
    </nav>

    <!-- Cart -->
    {#if cartIsOpen}
      <div
        transition:fade={{ duration: 150 }}
        class={`${
          cartIsOpen
            ? 'absolute top-16 w-full p-2 md:top-24 md:right-10 md:max-w-sm'
            : 'hidden'
        }`}
      >
        <Cart />
      </div>
    {/if}
  </div>
</header>
