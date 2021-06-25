<template>
<div class="out-box">
  <div class="black-plas">
    <div class="screen">
    12:30
    </div>
  </div>
  <div class="button-back">
    <div class="button"></div>
  </div>
</div>
</template>

<script lang="ts">
import { defineComponent, reactive, ref, toRefs, onMounted } from "vue";

export default defineComponent({
  name: "Home",
  // components: {
  //   HelloWorld,
  //   QaModel
  // },
  setup() {
    const data = reactive({
      temp: "1",

      addQa: () => {
        alert(1);
      },
    });

    data.addQa();
    return {
      ...toRefs(data),
    };
  },
});
</script>
