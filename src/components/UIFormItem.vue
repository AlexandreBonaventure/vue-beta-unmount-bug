<script lang="ts">
import { defineComponent, h } from 'vue';

export default defineComponent({
  components: {
    RootOrNot: (props, { slots }) => {
      const children = slots.default?.();
      return props.root ? h('div', { class: 'ui-form-item' }, children) : children;
    },
  },
  props: {
    root: {
      type: Boolean,
      required: false,
    },
  },
});
</script>

<template>
  <RootOrNot :root="root">
    <slot />
  </RootOrNot>
</template>
