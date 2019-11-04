<template>
  <div>
    <h1>{{ state.message }}</h1>
    <ChildComponent
      :message="state.message"
      @change-message="changeMessage"
    ></ChildComponent>
  </div>
</template>

<script lang="ts">
import ChildComponent from "@/components/ChildComponent.vue";
import { createComponent, reactive } from "@vue/composition-api";

export default createComponent({
  components: {
    ChildComponent
  },
  setup() {
    const state = reactive({
      message: "Hello"
    });

    const changeMessage = (message: string) => {
      state.message = message;
    };

    return {
      state,
      changeMessage
    };
  }
});
</script>
