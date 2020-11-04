<template>
  <UICard isFullWidth isPlaceholder title="Portal Blocks">
    <template v-slot:header-right>
      <div class="portal-blocks__icon" @click="isPortalActive = !isPortalActive">
        <i class="fas fa-eye" v-if="!isPortalActive" />
        <i class="fas fa-eye-slash" v-else />
      </div>
    </template>
    <template v-slot:default>
      <Portal to="portal-1" :disabled="!isPortalActive" >
        <UIBlock>Block 1</UIBlock>
      </Portal>
      <Portal to="portal-2" :disabled="!isPortalActive">
        <UIBlock>Block 2</UIBlock>
      </Portal>
      <Portal to="portal-3" :disabled="!isPortalActive">
        <UIBlock>Block 3</UIBlock>
      </Portal>
      <Portal to="portal-4" :disabled="!isPortalActive">
        <UIBlock>Block 4</UIBlock>
      </Portal>
      <p v-if="isPortalActive">Os blocos entraram no portal!</p>
    </template>
  </UICard>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
import { UIBlock, UICard } from '@/components';

export default defineComponent({
  name: 'PortalBlocks',

  components: {
    UIBlock,
    UICard,
  },

  setup() {
    const isPortalActive = ref(false);
    return { isPortalActive };
  },
});
</script>

<style scoped lang="scss">
.portal-blocks {
  &__icon {
    color: #adadad;
    transition: 0.3s;
    cursor: pointer;

    &:hover {
      color: #9b9b9b;
    }
  }
}
</style>
