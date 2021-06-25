<template src="./index.html" />

<script lang="ts">
import { defineComponent, reactive, ref, toRefs, onMounted } from "vue";

export default defineComponent({
  name: "watchCaculator",
  setup() {
    const data = reactive({
      numbers:[1,2,3,4,5,6,7,8,9],
      screenNumber:'',
      chooseNumber:()=>{

      }
    });
    return {
      ...toRefs(data),
    };
  },
});
</script>

<style lang="scss" src="./index.scss"></style>
