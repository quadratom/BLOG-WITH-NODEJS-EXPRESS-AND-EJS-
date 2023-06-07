<script setup>
  const city = ref("")

  const errorHandle = ref("false")

  const handleSearchbar = () => {
    if(!city.value)
    {
      return errorHandle = true
    }
    navigateTo(`/city/${city.value}/car`);

  };


</script>
<template>
    <!-- HOME SEARCH BAR -->
    <div
          class="font-serif w-[1000px] text-2xl rounded-full bg-white flex justify-between overflow-hidden drop-shadow-2xl mx-auto"
        >
          <input
          type="text"
          class="py-3 px-5 w-full text-2xl rounded-full focus:outline-none"
          placeholder="Search by city..." 
          v-model="city"
          :class="errorHandle ? 'border-red-500 border ': ''"
          />
          <button class="bg-sky-500 px-10 text-white" @click="handleSearchbar">Search</button>
        </div>
        <!-- HOME SEARCH BAR -->
</template>