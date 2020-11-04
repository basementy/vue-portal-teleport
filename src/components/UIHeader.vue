<template>
  <header class="ui-header">
    <slot />
  </header>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'UIHeader',
});
</script>

<style scoped lang="scss">
.ui-header {
  width: 100%;
  padding: 12px 16px;
  border-bottom: 1px solid #dfdfdf;
}
</style>
