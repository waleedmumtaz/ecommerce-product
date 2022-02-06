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

<div class="font-kumbh-sans min-h-screen">
  <Header />
  <Carousel />
  <Content />
</div>
