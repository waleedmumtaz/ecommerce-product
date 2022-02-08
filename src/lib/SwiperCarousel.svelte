<script>
  // import required modules
  import { Navigation } from 'swiper'
  // Import Swiper styles
  import 'swiper/css'
  import 'swiper/css/navigation'
  import { Swiper, SwiperSlide } from 'swiper/svelte'
</script>

<Swiper navigation={true} modules={[Navigation]}>
  {#each Array(4) as _, i}
    <SwiperSlide>
      <img
        src={`/assets/image-product-${i + 1}.jpg`}
        alt={`product ${i + 1}`}
      />
    </SwiperSlide>
  {/each}
</Swiper>

<style>
  :root {
    --swiper-navigation-color: black;
    --swiper-navigation-size: 24px;
  }
</style>
