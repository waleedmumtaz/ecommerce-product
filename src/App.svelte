<script>
  import Content from './lib/Content.svelte'
  import Header from './lib/Header.svelte'
  import SwiperCarousel from './lib/SwiperCarousel.svelte'
  import ThumbsGallery from './lib/ThumbsGallery.svelte'

  let navIsOpen = false
  let cartIsOpen = false

  const setNavIsOpen = (event) => {
    navIsOpen = event.detail
  }

  const setCartIsOpen = (event) => {
    cartIsOpen = event.detail
  }
</script>

<svelte:head>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link
    rel="preconnect"
    href="https://fonts.gstatic.com"
    crossorigin="anonymous"
  />
  <link
    href="https://fonts.googleapis.com/css2?family=Kumbh+Sans:wght@400;700&display=swap"
    rel="stylesheet"
  />
</svelte:head>

<div class="font-kumbh-sans md:flex md:min-h-screen md:flex-col">
  <Header on:toggleNav={setNavIsOpen} on:toggleCart={setCartIsOpen} />
  <main
    class={`${
      navIsOpen || cartIsOpen ? 'opacity-25' : ''
    } md:mx-auto md:grid md:max-w-6xl md:flex-1 md:grid-cols-2 md:items-center md:gap-20 md:p-5`}
  >
    <!-- Mobile carousel -->
    <SwiperCarousel />

    <!-- Tablet and desktop thumbs gallery -->
    <ThumbsGallery />

    <Content />
  </main>
  <footer class="pb-1 pt-5 text-center text-sm font-bold">
    Challenge by <a
      href="https://www.frontendmentor.io?ref=challenge"
      target="_blank"
      class="text-cstm-primary-orange underline">Frontend Mentor</a
    >. Coded by
    <a
      href="https://github.com/waleedmumtaz"
      class="text-cstm-primary-orange underline">Waleed Mumtaz</a
    >.
  </footer>
</div>
