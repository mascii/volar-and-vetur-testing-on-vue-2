<template>
  <div>
    <MyComponent>
      <template v-if="user" #header>
        Hello, {{ user.name }}!
      </template>
      <template v-if="user">
        Hello, {{ user.name }}.
      </template>
    </MyComponent>
  </div>
</template>

<script lang="ts">
import { defineComponent } from '@vue/composition-api';
import MyComponent from './components/MyComponent.vue';

type User = { name: string };

const getUser = (): User | undefined => {
  if (Math.random() < 0.5) {
    return undefined;
  }
  return {
    name: 'Bob',
  };
}

export default defineComponent({
  name: 'App',
  components: {
    MyComponent,
  },
  setup() {
    const user = getUser();

    return {
      user,
    };
  }
});
</script>
