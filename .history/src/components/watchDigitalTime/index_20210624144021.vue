<template src = "./index.html"/>

<script lang="ts">
import { defineComponent, reactive, ref, toRefs, onMounted } from "vue";

export default defineComponent({
  name: "watchDigitalTime",
  setup() {
    const data = reactive({
      ifCloseAnim: false,
      nowPageNum: 2,
      pageMax: 2,
      nowType: "red-type",
      value1:null,

      //切换颜色
      changeType: (type: any) => {
        data.nowType = type;
      },
    });

    return {
      ...toRefs(data),
    };
  },
});
</script>

<style lang="scss" src = "./index/scss"></style>