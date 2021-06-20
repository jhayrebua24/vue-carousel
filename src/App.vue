<template>
  <swiper
    :pagination="{ clickable: true }"
    :space-between="50"
    :breakpoints="{
      640: {
        slidesPerView: 2,
      },
      768: {
        slidesPerView: 3,
      },
      1024: {
        slidesPerView: 5,
      },
    }"
  >
    <swiper-slide v-for="val in list" :key="val.id"
      ><SlideInfo :details="val"
    /></swiper-slide>
  </swiper>
</template>

<script>
import SwiperCore, { Pagination } from "swiper";
import { Swiper, SwiperSlide } from "swiper/vue";
import SlideInfo from "./components/Slide.vue";
import "swiper/swiper-bundle.min.css";
import sampleData from "./components/data";

// install Swiper modules
SwiperCore.use([Pagination]);

// Import Swiper styles
export default {
  components: {
    Swiper,
    SwiperSlide,
    SlideInfo,
  },
  data: function() {
    return {
      list: sampleData,
    };
  },
  methods: {
    onSwiper(swiper) {
      console.log(swiper);
    },
    onSlideChange() {
      console.log("slide change");
    },
  },
};
</script>

<style scoped>
.swiper-slide {
  width: auto !important;
}
</style>
