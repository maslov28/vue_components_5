<template>
  <app-tabs 
    :activeTab="activeTab"
    :tabs="tabs"
    @activeTabChange="activeTabChange"
  ></app-tabs>
</template>

<script>
import AppTabs from './components/AppTabs.vue'

export default {
  data() {
    return {
      tabs: [
        {
          name: 'Все',
          key: 'all'
        },
        { 
          name: 'Новые',
          key: 'new'
        },
        {
          name: 'Старые',
          key: 'old'
        }
      ],
      activeTab: 'all'
    }
  },
  methods: {
    activeTabChange(value) {
      this.activeTab = value
    }
  },
  components: {AppTabs}
}
</script>
