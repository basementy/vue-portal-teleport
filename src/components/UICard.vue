<template>
  <div
    class="ui-card"
    :class="{
      'ui-card--full': isFullWidth,
      'ui-card--placeholder': isPlaceholder
      }"
  >
    <div class="ui-card__header">
      <div class="ui-card__header__left" v-text="title" />
      <div class="ui-card__header__right">
        <slot name="header-right" />
      </div>
    </div>
    <div class="ui-card__content">
      <slot />
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'UICard',

  props: {
    title: String,
    isFullWidth: Boolean,
    isPlaceholder: Boolean,
  },
});
</script>

<style scoped lang="scss">
.ui-card {
  margin: 8px;
  width: fit-content;
  min-width: 300px;
  height: 250px;
  padding: 16px;
  border: 1px solid #c4c4c4;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  color: #7c7c7c;

  &__header {
    display: flex;
    align-items: center;
    justify-content: space-between;

    &__right {
      display: flex;
      align-items: center;
      justify-content: flex-end;
    }
  }

  &__content {
    flex: 2;
    padding: 8px 0px;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
  }

  &--full {
    width: 100%;
  }

  &--placeholder {
    margin-bottom: 32px;
    background: #f3f3f3;
    border: 1px solid #e7e7e7;
  }
}
</style>
