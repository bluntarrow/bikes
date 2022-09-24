<template>
<div class="flex bg-gray-100/25 z-30 bg-clip-padding backdrop-filter backdrop-blur-sm justify-between items-end px-8 py-4 sticky top-0 w-full ">

  <h1 class="text-lg uppercase sm:hidden font-semibold">logo</h1>
  <router-link to="/" class="sm:hidden">
    <div class="p-2 bg-gray-200/60 rounded-full">
      <Bars2Icon class="h-5"></Bars2Icon>
    </div>
  </router-link>
      <ul class="sm:flex gap-4 hidden">
        <li>
          <router-link to="/">
            <div class="p-2 bg-gray-200/60 rounded-full">
              <ChevronLeftIcon class="h-5"></ChevronLeftIcon>
            </div>
          </router-link>
        </li>
        <li>
          <router-link to="/">
            <div class="p-2 bg-gray-200/60 rounded-full">
              <ChevronRightIcon class="h-5"></ChevronRightIcon>
            </div>
          </router-link>
        </li>
      </ul>
      <ul class="sm:flex hidden gap-4">
        <li>
          <router-link to="/">
            <div class="p-2 bg-gray-200/60 rounded-full">
              <HeartIcon class="h-5"></HeartIcon>
            </div>
          </router-link>
        </li>
        <li>
          <router-link to="/">
            <div class="p-2 bg-gray-200/60 rounded-full">
              <ShoppingBagIcon class="h-5"></ShoppingBagIcon>
            </div>
          </router-link>
        </li>
      </ul>
    </div>
</template>
<script setup>
import {
  ShoppingBagIcon,
  HeartIcon,
  ChevronLeftIcon,
  ChevronRightIcon,
  Bars2Icon
} from "@heroicons/vue/24/outline";
</script>