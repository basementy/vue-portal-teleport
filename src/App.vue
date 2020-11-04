<template>
  <div class="app-wrapper">
    <UIHeader>
      <UIButtonGroup
        :buttons="getButtonItems"
        @change="selectedComponent = $event"
      />
    </UIHeader>
    <UIGallery>
      <PortalBlocks v-if="selectedComponent == 'PORTAL'" />
      <TeleportBlocks v-else />
      <PortalCards />
      <TeleportCards />
    </UIGallery>
  </div>
</template>

<script>
import { defineComponent, ref } from 'vue';
import { UIButtonGroup, UIGallery, UIHeader } from '@/components';

import PortalBlocks from './containers/PortalBlocks.vue';
import TeleportBlocks from './containers/TeleportBlocks.vue';

import PortalCards from './containers/PortalCards.vue';
import TeleportCards from './containers/TeleportCards.vue';

export default defineComponent({
  name: 'App',

  components: {
    UIButtonGroup,
    UIGallery,
    UIHeader,
    PortalBlocks,
    PortalCards,
    TeleportBlocks,
    TeleportCards,
  },

  setup() {
    const selectedComponent = ref('PORTAL');

    const getButtonItems = [
      { label: 'Vue Portal', value: 'PORTAL' },
      { label: 'Vue Teleport', value: 'TELEPORT' },
    ];

    return { getButtonItems, selectedComponent };
  },
});
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800&display=swap');

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Poppins', sans-serif;
}

body {
  width: 100vw;
  height: 100vh;
}

.app-wrapper {
  height: 100vh;
  display: flex;
  flex-direction: column;
}
</style>
