<template>
  <div class="text-gray-500">
    <nav class="flex justify-between px-10 py-5 items-baseline text-gray-600">
      <h1 class="font-medium text-lg">Bikes</h1>
      <ul class="flex capitalize gap-8 font-semibold text-sm">
        <li class="cursor-pointer hover:text-gray-400">home</li>
        <li class="cursor-pointer hover:text-gray-400">products</li>
        <li class="cursor-pointer hover:text-gray-400">about</li>
      </ul>
      <UserIcon class="h-4"></UserIcon>
    </nav>
    <div class="flex justify-center">
      <img src="../assets/img/img (5).png" class="w-7/12" alt="" />
    </div>

    <div class="flex justify-between mx-4 my-2">
      <h2 class="font-medium text-xl">Products</h2>
      <small class="text-sm ">See more</small>
    </div>

    <div class="grid grid-cols-3 px-4 gap-4 pb-4 text-gray-600">
      <div class="shadow hover:shadow-xl hover:-translate-y-2 transition-all border border-gray-50 cursor-pointer rounded relative">
        <h4 class="absolute text-sm top-4 left-4">$79</h4>
        <img src="../assets/img/img (4).png" class="w-full" alt="" />
      </div>
      <div class="shadow hover:shadow-xl hover:-translate-y-2 transition-all border border-gray-50 cursor-pointer rounded relative">
        <h4 class="absolute text-sm top-4 left-4">$73</h4>
        <img src="../assets/img/img (1).png" class="w-full" alt="" />
      </div>
      <div class="shadow hover:shadow-xl hover:-translate-y-2 transition-all border border-gray-50 cursor-pointer rounded relative">
        <h4 class="absolute text-sm top-4 left-4">$56</h4>
        <img src="../assets/img/img (2).png" class="w-full" alt="" />
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
import { UserIcon } from "@heroicons/vue/24/solid";
</script>
