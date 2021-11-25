<template>
  <div class="flex flex-col py-4 px-8">
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
    <transition name="fade">
      <div v-if="show">
        <cardOne :cardData="selectedTab.cards[0]" />
        <cardTwo :cardData="selectedTab.cards[1]" />
        <cardThree :cardData="selectedTab.cards[2]" />
      </div>
    </transition>
  </div>
</template>

<script>
import cardOne from './cards/cardOne.vue'
import cardTwo from './cards/cardTwo.vue'
import cardThree from './cards/cardThree.vue'

export default {
  props: ['selectedTab'],
  data() {
    return {
      show: true,
    }
  },
  components: {
    cardOne,
    cardTwo,
    cardThree,
  },
  watch: {
    selectedTab() {
      this.show = false
      setTimeout(() => (this.show = true), 50)
    },
  },
}
</script>

<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease-in-out;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0.5;
}
</style>
