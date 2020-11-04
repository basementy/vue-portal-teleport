<template>
  <div class="ui-gallery">
    <slot />
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'UIGallery',
});
</script>

<style scoped lang="scss">
.ui-gallery {
  width: 100%;
  height: 100%;
  padding: 32px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  overflow: auto;
}
</style>
