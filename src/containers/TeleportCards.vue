<template>
  <UICard title="Teleport 1">
    <div id="teleport-1"></div>
  </UICard>
  <UICard title="Teleport 2">
    <div id="teleport-2"></div>
  </UICard>
  <UICard title="Teleport 3">
    <div id="teleport-3"></div>
  </UICard>
  <UICard title="Teleport 4">
    <div id="teleport-4"></div>
  </UICard>
</template>

<script lang="ts">
import { UICard } from '@/components';
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'TeleportCards',

  components: {
    UICard,
  },
});
</script>
