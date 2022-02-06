<script>
  import Carousel from './lib/Carousel.svelte'
  import Content from './lib/Content.svelte'
  import Header from './lib/Header.svelte'
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

<div class="font-kumbh-sans flex min-h-screen flex-col">
  <Header />
  <div
    class="md:mx-auto md:grid md:max-w-6xl md:flex-1 md:grid-cols-2 md:items-center md:gap-20 md:p-5"
  >
    <Carousel />
    <Content />
  </div>
</div>
