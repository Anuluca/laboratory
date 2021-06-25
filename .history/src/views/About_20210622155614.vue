<template>
  321
</template>

<script lang="ts">
import { defineComponent, reactive, ref, toRefs } from "vue";

export default defineComponent({
  name: "Home",
  // components: {
  //   HelloWorld,
  //   QaModel
  // },
  setup() {
    const data = reactive({
      temp:'1',

      addQa: () => {
        alert(1)
      },
    });
    return {
      ...toRefs(data)
    };
      }
});
</script>
