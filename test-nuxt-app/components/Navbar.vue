<template>
  <div
    class="
      text-main
      flex
      align-center
      transition-all
      hide-scrollbar
      overflow-x-auto
    "
  >
    <div
      v-for="(tab, index) in tabs"
      :id="tab.label"
      :key="index"
      class="border-2 bg-white py-2 px-10"
      :class="{
        'mr-5 rounded-r-2xl': index == tabs.length - 1,
        'ml-5 rounded-l-2xl': index == 0,
        'transition bg-white bg-selected duration-1000 ease-in-out text-white':
          selectedTab && tab.label == selectedTab.label,
      }"
      @click="selectTab(tab)"
    >
      {{ tab.label }}
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      tabs: [
        {
          label: 'Arbeitnehmer',
          title: 'Drei einfache Schritte zu deinem neuen Job',
          cards: [
            {
              label: 'Erstellen dein Lebenslauf',
              image: require('../assets/images/1.png'),
            },
            {
              label: 'Erstellen dein Lebenslauf',
              image: require('../assets/images/2.png'),
            },
            {
              label: 'Mit nur einem Klick bewerben',
              image: require('../assets/images/3.png'),
            },
          ],
        },
        {
          label: 'Arbeitgeber',
          title: 'Drei einfache Schritte zu deinem neuen Mitarbeiter',
          cards: [
            {
              label: 'Erstellen dein Unternehmensprofil',
              image: require('../assets/images/1.png'),
            },
            {
              label: 'Erstellen ein Jobinserat',
              image: require('../assets/images/4.png'),
            },
            {
              label: 'Wähle deinen neuen Mitarbeiter aus',
              image: require('../assets/images/5.png'),
            },
          ],
        },
        {
          label: 'Temporärbüro',
          title: 'Drei einfache Schritte zur Vermittlung neuer Mitarbeiter',
          cards: [
            {
              label: 'Erstellen dein Unternehmensprofil',
              image: require('../assets/images/1.png'),
            },
            {
              label: 'Erhalte Vermittlungs- angebot von Arbeitgeber',
              image: require('../assets/images/6.png'),
            },
            {
              label: 'Vermittlung nach Provision oder Stundenlohn',
              image: require('../assets/images/7.png'),
            },
          ],
        },
      ],
      selectedTab: null,
    }
  },
  mounted() {
    this.selectTab(this.tabs[1])
  },
  methods: {
    selectTab(tab) {
      this.selectedTab = tab
      document.getElementById(tab.label).scrollIntoView({
        inline: 'center',
        block: 'nearest',
        behavior: 'smooth',
      })
      this.$emit('tabSelected', tab)
    },
  },
}
</script>

<style scoped>
.bg-selected {
  background-color: #81e6d9;
}
</style>
