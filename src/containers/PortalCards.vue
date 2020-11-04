<template>
  <UICard title="Portal 1">
    <PortalTarget name="portal-1" />
  </UICard>
  <UICard title="Portal 2">
    <PortalTarget name="portal-2" />
  </UICard>
  <UICard title="Portal 3">
    <PortalTarget name="portal-3" />
  </UICard>
  <UICard title="Portal 4">
    <PortalTarget name="portal-4" />
  </UICard>
</template>

<script lang="ts">
import { UICard } from '@/components';
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'PortalCards',

  components: {
    UICard,
  },
});
</script>
