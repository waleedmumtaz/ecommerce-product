<script>
  // import required modules
  import { FreeMode, Navigation, Thumbs } from 'swiper'
  // Import Swiper styles
  import 'swiper/css'
  import 'swiper/css/free-mode'
  import 'swiper/css/navigation'
  import 'swiper/css/thumbs'
  import { Swiper, SwiperSlide } from 'swiper/svelte'
  // import './style.css'

  let thumbsSwiper = null

  const setThumbsSwiper = (e) => {
    const [swiper] = e.detail
    // set Thumbs swiper instance
    setTimeout(() => {
      thumbsSwiper = swiper
    })
  }
</script>

<div class="hidden md:block">
  <div>
    <Swiper
      style="--swiper-navigation-color: #fff;--swiper-pagination-color: #fff"
      spaceBetween={10}
      navigation={false}
      thumbs={{ swiper: thumbsSwiper }}
      modules={[FreeMode, Navigation, Thumbs]}
    >
      {#each Array(4) as _, i}
        <SwiperSlide>
          <img
            src={`/assets/image-product-${i + 1}.jpg`}
            alt={`product ${i + 1}`}
            class="rounded-lg"
          />
        </SwiperSlide>
      {/each}
    </Swiper>
  </div>
  <div class="mt-4">
    <Swiper
      on:swiper={setThumbsSwiper}
      spaceBetween={16}
      slidesPerView={4}
      freeMode={true}
      watchSlidesProgress={true}
      modules={[FreeMode, Navigation, Thumbs]}
    >
      {#each Array(4) as _, i}
        <SwiperSlide>
          <img
            src={`/assets/image-product-${i + 1}.jpg`}
            alt={`product ${i + 1}`}
            class="cursor-pointer rounded-lg"
          />
        </SwiperSlide>
      {/each}
    </Swiper>
  </div>
</div>
