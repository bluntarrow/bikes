<template>
  <div
    class="bg-gray-200 h-[100vh] hidden sm:flex col-span-3 flex-col text-gray-500 border-r shadow-lg z-20 relative"
  >
    <TopBar @openProfile="profile=true"></TopBar>
    <div class="p-2 pb-0 flex flex-col">
      <SearchBar></SearchBar>
      <div class="h-full">
        <ul class="grid grid-cols-2 gap-4 mb-6">
          <li class="flex gap-4 items-center mx-2" v-for="i in 4">
            <img src="../../assets/img/img6.jpg" class="aspect-square rounded-md object-cover h-12" alt="">
            <h2>Lorem</h2>
          </li>
        </ul>
        <div class="grid grid-cols-2 px-2 gap-4 mr-6">
          <img src="../../assets/img/img5.jpg" alt="" class=" aspect-square rounded-md object-cover shadow-gray-400 hover:shadow-sm hover:-translate-y-1" v-for="i in 4">
        </div>

      </div>
    </div>
  </div>
</template>
<script setup>
import TopBar from "./leftNav/TopBar.vue";
import SearchBar from "./leftNav/SearchBar.vue";
import { useRoute } from "vue-router";
import { ref, watch } from "vue";

const route = useRoute();
const status = ref(false);
const profile = ref(false);

const setStatus = () => {
  if (route.name == "status") {
    status.value = true;
  } else {
    status.value = false;
  }
};

setStatus()
watch(() => route.name, setStatus);
</script>

<style>
.slide-enter-active,
.slide-leave-active {
  transition: all 0.3s ease;
}

.slide-enter-from,
.slide-leave-to {
  transform: translateX(-100%);
}
</style>
