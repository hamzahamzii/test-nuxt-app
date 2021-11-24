<template>
  <div class="flex flex-col py-4 px-8">
    <transition>
      <div
        class="
          text-xl
          transition-all
          ease-in-out
          duration-1000
          text-gray-600 text-center
        "
        v-html="selectedTab.title"
      ></div>
    </transition>
    <cardOne :cardData="selectedTab.cards[0]" />
    <cardTwo :cardData="selectedTab.cards[1]" />
    <cardThree :cardData="selectedTab.cards[2]" />
  </div>
</template>

<script>
import cardOne from './cards/cardOne.vue'
import cardTwo from './cards/cardTwo.vue'
import cardThree from './cards/cardThree.vue'

export default {
  props: ['selectedTab'],
  components: {
    cardOne,
    cardTwo,
    cardThree,
  },
}
</script>

<style scoped>
.enter-from {
  opacity: 0;
}
.enter-to {
  opacity: 1;
}
.enter-active {
  transition: opacity 2s ease;
}
</style>
