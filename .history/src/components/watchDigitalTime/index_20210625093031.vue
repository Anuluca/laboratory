<template src="./index.html" />

<script lang="ts">
import { defineComponent, reactive, ref, toRefs, onMounted } from "vue";

export default defineComponent({
  name: "watchDigitalTime",
  setup() {
    const data = reactive({
      nowTime:'',
      changeTime: () => {
        // setInterval(() => {
          data.nowTime = '123'
        // }, 1000);
      },
    });
data.changeTime()
    return {
      ...toRefs(data),
    };
  },
});
</script>

<style lang="scss" src="./index.scss"></style>
