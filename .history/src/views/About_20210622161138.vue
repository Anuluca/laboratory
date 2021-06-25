<template>
  321
</template>

<script lang="ts">
import { defineComponent, reactive, ref, toRefs,onMounted } from "vue";

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
    // onMounted(()=>{
      data.addQa()
    // })
    return {
      ...toRefs(data)
    };
  }
});
</script>
