<template src="./index.html" />

<script lang="ts">
import { defineComponent, reactive, ref, toRefs, onMounted } from "vue";

export default defineComponent({
  name: "watchKokinggu",
  setup() {
    const data: any = reactive({
      numbers: 'n',

      //点击数字
      chooseNumber: (number: any) => {

      },

    });
    return {
      ...toRefs(data),
    };
  },
});
</script>

<style lang="scss" src="./index.scss"></style>
