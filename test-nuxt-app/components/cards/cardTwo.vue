<template>
  <div class="flex items-start my-6">
    <p class="text-8xl text-gray-500">2.</p>
    <div class="flex flex-col justify-center align-center">
      <p class="text-lg px-6 pt-3 text-gray-500">
        {{ cardData.label }}
      </p>
      <img :src="cardData.image" alt="" srcset="" />
    </div>
  </div>
</template>

<script>
export default {
  props: ['cardData'],
}
</script>
