<script lang="ts">
import { defineComponent } from 'vue';
import UIFormItem from './UIFormItem.vue';

export default defineComponent({
  components: {
    DummyComponent: () => 'dummy',
    UIFormItem,
  },
});
</script>

<template>
  <UIFormItem>
    <ul>
      <li
        v-for="item in 1"
        :key="item"
      >
        <DummyComponent></DummyComponent>
      </li>
    </ul>
  </UIFormItem>
</template>
