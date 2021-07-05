<template src="./index.html" />

<script lang="ts">
import { defineComponent, reactive, ref, toRefs, onMounted } from "vue";

export default defineComponent({
  name: "watchKokinggu",
  setup() {
    const data: any = reactive({
      ifAnimation: false,

      //点击硬币
      roll: () => {
        data.ifAnimation = true
        setTimeout(() => {
          data.ifAnimation = false
        }, 1000);
      },

    });
    return {
      ...toRefs(data),
    };
  },
});
</script>

<style lang="scss" src="./index.scss"></style>
