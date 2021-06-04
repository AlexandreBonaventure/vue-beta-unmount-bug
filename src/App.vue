<script lang="ts">
import { defineComponent, h, unref, ref } from 'vue';
import UIInputBox from './components/UIInputBox.vue';

export default defineComponent({
  components: {
    UIInputBox,
  },
  setup () {
    const noItems = ref(false);
    setInterval(() => { noItems.value = !noItems.value; }, 300);
    const FilterInputHOC = () => h(UIInputBox, {
      'whatever': unref(noItems),
    }, {
      default () {
        return 'test';
      },
    });
    return {
      FilterInputHOC,
      toggle: ref(true),
    };
  },
});
</script>

<template>
  <button @click="toggle = !toggle">Toggle</button>
  <component
    :is="FilterInputHOC"
    v-if="toggle"
  />
</template>
