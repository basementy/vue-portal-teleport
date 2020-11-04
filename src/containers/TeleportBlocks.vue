<template>
  <UICard isFullWidth isPlaceholder title="Teleport Blocks">
    <template v-slot:header-right>
      <div class="portal-blocks__icon" @click="isTeleportActive = !isTeleportActive">
        <i class="fas fa-eye" v-if="!isTeleportActive" />
        <i class="fas fa-eye-slash" v-else />
      </div>
    </template>
    <template v-slot:default>
      <teleport to="#teleport-1" :disabled="!isTeleportActive">
        <UIBlock>
          Block 1
        </UIBlock>
      </teleport>
      <teleport to="#teleport-2" :disabled="!isTeleportActive">
        <UIBlock>
          Block 2
        </UIBlock>
      </teleport>
      <teleport to="#teleport-3" :disabled="!isTeleportActive">
        <UIBlock>
          Block 3
        </UIBlock>
      </teleport>
      <teleport to="#teleport-4" :disabled="!isTeleportActive">
        <UIBlock>
          Block 4
        </UIBlock>
      </teleport>
      <p v-if="isTeleportActive">Os blocos entraram no teleport!</p>
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
    const isTeleportActive = ref(false);
    return { isTeleportActive };
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
