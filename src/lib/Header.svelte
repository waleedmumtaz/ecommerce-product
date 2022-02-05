<script>
  import IconCart from './IconCart.svelte'
</script>

<header>
  <!-- 
  -- Implement mobile nav --

  Collections
  Men
  Women
  About
  Contact
   -->
  <nav class="flex items-center justify-between p-5">
    <div class="flex items-center gap-4">
      <button>
        <img src="/assets/icon-menu.svg" alt="hamburger menu" />
      </button>
      <img src="/assets/logo.svg" alt="logo" />
    </div>
    <div class="flex items-center gap-6">
      <IconCart />
      <img src="/assets/image-avatar.png" alt="avatar" class="w-6" />
    </div>
  </nav>
</header>
