<template>
  <div class="flex items-end my-6">
    <p class="text-8xl text-gray-500">1.</p>
    <div class="flex flex-col justify-center align-center">
      <img :src="cardData.image" alt="" srcset="" />
      <p class="text-lg px-6 pt-3 text-gray-500">
        {{ cardData.label }}
      </p>
    </div>
  </div>
</template>

<script>
export default {
  props: ['cardData'],
}
</script>
