<template>
  <ul>
    <li 
      v-for="tab in tabs" 
      :key="tab.key"
      @click="$emit('activeTabChange', tab.key)"
    >
      {{ tab.name }}
    </li>
  </ul>

  <component :is="componentName"></component>

</template>

<script>
import AppAll from './AppAll.vue'
import AppNew from './AppNew.vue'
import AppOld from './AppOld.vue'

export default {
  props: {
    tabs: {
      type: Array,
      required: true
    },
    activeTab: {
      type: String,
      required: true
    }
  },
  emits: ['activeTabChange'],

  computed: {
    componentName() {
      return 'app-' + this.activeTab
    }
  },  
 
  components: {
    AppAll, AppNew, AppOld
  }
}
</script>

<style scoped>
  ul {
    display: flex;
    padding: 0;
  }
  li {
    list-style-type: none;
    margin-right: 10px;
    border: 1px solid black;
    padding: 10px;
    cursor: pointer;
  }
</style>