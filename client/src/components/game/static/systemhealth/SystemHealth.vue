<template>
  <div class="c-system-health tour-system-health">
    <p class="title">System Health</p>
    <StatusBar class="statusbar" :setWidth="`${systemHealthStatus}`" />
    <p class="status">{{ systemHealthStatus }}<span>%</span></p>
  </div>
</template>

<script lang="ts">
import { Vue, Component } from 'vue-property-decorator';
import StatusBar from './StatusBar.vue';

@Component({
  components: {
    StatusBar,
  },
})
export default class SystemHealth extends Vue {
  get systemHealthStatus() {
    return this.$tstore.state.systemHealth;
  }
}
</script>

<style lang="scss" scoped>
@import '@port-of-mars/client/stylesheets/game/static/systemhealth/SystemHealth.scss';
</style>
