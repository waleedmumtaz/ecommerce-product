<script>
  import { fly } from 'svelte/transition'
  import IconCart from './IconCart.svelte'

  let navIsOpen = false

  const toggleNav = () => {
    navIsOpen = !navIsOpen
  }
</script>

<header>
  <!-- Mobile nav -->
  <nav class="relative">
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
        <IconCart />
        <img src="/assets/image-avatar.png" alt="avatar" class="w-6" />
      </div>
    </div>
  </nav>
</header>
