<template>
  <div>
    <h2>
      <slot name="header">No #header</slot>
    </h2>
    <div>
      <slot>No #body</slot>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from '@vue/composition-api';

export default defineComponent({
  name: 'MyComponent',
});
</script>
