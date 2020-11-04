<template>
  <div class="ui-block">
    <slot />
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'UIBlock',
});
</script>

<style scoped lang="scss">
.ui-block {
  width: 100px;
  height: 100px;
  margin: 4px;
  display: flex;
  justify-content: center;
  align-items: center;
  background: #363636;
  color: #fff;
}
</style>
