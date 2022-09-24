<template>
  <div class="w-full relative">
    <!--  picture -->

    <!-- :autoplay="{
        delay: 5000,
        disableOnInteraction: false,
      }" -->

    <Swiper
      :slides-per-view="'auto'"
      class="rounded-md py-5 pl-5 relative z-10"
      :loop="true"
      :space-between="20"
      :centered-slides="true"
      @swiper="getSwiper"
    >
      <swiper-slide
        v-for="i in 5"
        class="w-2/3 grid grid-cols-2 bg-gray-200 rounded-md shadow-md"
      >
        <img
          v-if="swipe"
          :class="
            i + 4 == swipe.activeIndex || swipe.activeIndex > 9
              ? '-translate-y-3 -translate-x-3 shadow-sm'
              : ''
          "
          :src="getImg(`img${i + 1}`)"
          class="bg-cover transition-all duration-300 bg-fixed object-cover shadow-gray-400/50 z-20 rounded-md aspect-square cursor-pointer"
          alt=""
        />
        <div class="p-5 flex flex-col z-10 justify-around">
          <div>
            <h3 class="text-3xl text-gray-600 font-medium">Simple</h3>
            <ul class="flex gap-2">
              <li class="flex items-center gap-1 text-gray-400">
                <MegaphoneIcon class="h-3"></MegaphoneIcon>
                <h4 class="text-xs">50%</h4>
              </li>
              <li class="flex items-center gap-1 text-gray-400">
                <BanknotesIcon class="h-3"></BanknotesIcon>
                <h4 class="text-xs">15,000</h4>
              </li>
            </ul>
          </div>
          <button
            class="w-full py-2 bg-gray-800 text-gray-100 hover:bg-gray-700 rounded-md mt-3"
          >
            Browse All
          </button>
          <div class="grid grid-cols-2 gap-3 pt-3">
            <img
              src="../../assets/img/img1.jpg"
              class="aspect-square bg-cover object-cover rounded-md shadow-lg hover:-translate-y-1 cursor-pointer transition-all"
              v-for="i in 2"
              alt=""
            />
          </div>
        </div>
      </swiper-slide>
    </Swiper>

    <!-- control buttons -->
    
      <button class="text-lg absolute z-50  left-4 top-0 bottom-0 my-auto" v-if="swipe" @click="swipe.slidePrev(500)">
        <div class="p-2 bg-gray-200/40 backdrop-blur-sm rounded-full shadow-xl">
          <ChevronLeftIcon class="h-5 text-gray-200"></ChevronLeftIcon>
        </div>
      </button>
      <button class="text-lg absolute z-50  right-4 top-0 bottom-0 my-auto" v-if="swipe" @click="swipe.slideNext(500)">
        <div class="p-2 bg-gray-200/40 backdrop-blur-sm rounded-full shadow-xl">
          <ChevronRightIcon class="h-5 text-gray-200"></ChevronRightIcon>
        </div>
      </button>
  </div>
</template>
<script setup>
import { ref } from "vue";
import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/css";
import { ChevronRightIcon, ChevronLeftIcon } from "@heroicons/vue/20/solid";
import { MegaphoneIcon, BanknotesIcon } from "@heroicons/vue/24/outline";

const img = ref(null);

const getImg = (imgurl) => {
  return new URL(`../../assets/img/${imgurl}.jpg`, import.meta.url);
};

// swiper controls
const swipe = ref(null);
const getSwiper = (swiper) => {
  swipe.value = swiper;
};
</script>
