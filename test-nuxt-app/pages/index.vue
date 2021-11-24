<template>
  <div class="bg-main py-20 h-screen overflow-y-scroll">
    <Topbar />
    <Banner />
    <Navbar @tabSelected="selectTab" />
    <JobOptions v-if="selectedTab" :selectedTab="selectedTab" />
    <Bottombar />
  </div>
</template>

<script>
export default {
  data() {
    return {
      selectedTab: null,
    }
  },
  methods: {
    selectTab(tab) {
      this.selectedTab = tab
    },
  },
}
</script>
