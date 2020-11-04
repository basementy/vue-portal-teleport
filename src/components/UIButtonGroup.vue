<template>
  <div class="ui-button-group">
    <button
      class="ui-button-group__item"
      v-for="(button, index) in buttons"
      :class="{ 'ui-button-group__item--active': selectedIndex === index}"
      :key="index"
      @click="onButtonClick(index)"
    >
      {{ button.label }}
    </button>
  </div>
</template>

<script>
import { defineComponent, ref } from 'vue';

export default defineComponent({
  name: 'UIButtonGroup',

  props: {
    buttons: Array,
  },

  setup(props, ctx) {
    const selectedIndex = ref(0);
    const onButtonClick = (index) => {
      selectedIndex.value = index;
      ctx.emit('change', props.buttons[index].value);
    };

    return { selectedIndex, onButtonClick };
  },
});
</script>

<style scoped lang="scss">
.ui-button-group {
  width: fit-content;
  display: flex;
  align-items: center;

  &__item {
    background: unset;
    border-radius: 0px;
    border: 0px;
    padding: 8px 16px;
    border: 1px solid #070707;
    outline: 0px;
    transition: 0.15s;
    cursor: pointer;

    &--active {
      background: #070707;
      color: #fff;
    }

    &:hover {
      background: #070707;
      color: #fff;
    }
  }
}
</style>
