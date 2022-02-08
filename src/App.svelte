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
  <title>E-commerce Product Page</title>
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

<div>
  <Header on:toggleNav={setNavIsOpen} on:toggleCart={setCartIsOpen} />
  <div
    class={`${
      navIsOpen || cartIsOpen ? 'opacity-25' : ''
    } md:mx-auto md:grid md:max-w-6xl md:flex-1 md:grid-cols-2 md:items-center md:gap-20 md:p-5`}
  >
    <!-- Mobile carousel -->
    <SwiperCarousel />

    <!-- Tablet and desktop thumbs gallery -->
    <ThumbsGallery />

    <Content />
  </div>
</div>
