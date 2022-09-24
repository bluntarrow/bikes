<template>
  <div class="w-full relative">
    <!--  picture -->

    <!-- :autoplay="{
        delay: 5000,
        disableOnInteraction: false,
      }" -->
    <swiper
      :slides-per-view="'auto'"
      :modules="modules"
      class="relative rounded-md py-5"
      effect="coverflow"
      :loop="true"
      :grab-cursor="true"
      :centered-slides="true"
      @swiper="getSwiper"
      @slide-change="getColor"
      :coverflow-effect="{
        rotate: 50,
        stretch: 0,
        depth: 100,
        modifier: 1,
        slideShadows: true,
      }"
    >
      <swiper-slide v-for="i in 5" class="w-3/4">
        <img
          :src="getImg(`img${i}`)"
          class="bg-cover bg-fixed object-cover rounded-md shadow-xl aspect-[2/1]"
          alt=""
          ref="img"
        />
      </swiper-slide>
    </swiper>

    <!-- controls -->
    <button
      class="text-lg absolute z-50 left-4 top-0 bottom-0 my-auto"
      v-if="swipe"
      @click="swipe.slidePrev(500)"
    >
      <div class="p-2 bg-gray-200/40 backdrop-blur-sm rounded-full shadow-xl">
        <ChevronLeftIcon class="h-5 text-gray-200"></ChevronLeftIcon>
      </div>
    </button>
    <button
      class="text-lg absolute z-50 right-4 top-0 bottom-0 my-auto"
      v-if="swipe"
      @click="swipe.slideNext(500)"
    >
      <div class="p-2 bg-gray-200/40 backdrop-blur-sm rounded-full shadow-xl">
        <ChevronRightIcon class="h-5 text-gray-200"></ChevronRightIcon>
      </div>
    </button>
  </div>
</template>
<script setup>
import { ref } from "vue";
import { FastAverageColor } from "fast-average-color";
import { Autoplay, EffectCoverflow } from "swiper";
import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/css";
import "swiper/css/effect-coverflow";
import { ChevronRightIcon, ChevronLeftIcon } from "@heroicons/vue/20/solid";

const modules = [Autoplay, EffectCoverflow];
const emit = defineEmits(["colorChange"]);

const img = ref(null);
const bg = ref(null);

const getImg = (imgurl) => {
  return new URL(`../../assets/img/${imgurl}.jpg`, import.meta.url);
};

// swiper controls
const swipe = ref(null);
const getSwiper = (swiper) => {
  swipe.value = swiper;
  const fac = new FastAverageColor();
  bg.value = fac.getColor(img.value[swiper.activeIndex]).rgba;
};
const getColor = (swiper) => {
  const fac = new FastAverageColor();
  bg.value = fac.getColor(img.value[swiper.activeIndex]).rgba;
  emit("colorChange", bg.value);
};
</script>
