<template src = "./index.html"/>

<script lang="ts">
import { defineComponent, reactive, ref, toRefs, onMounted } from "vue";

export default defineComponent({
  name: "watchDigitalTime",
  setup() {
    const data = reactive({
      
    });

    return {
      ...toRefs(data),
    };
  },
});
</script>

<style lang="scss" src = "./index.scss"></style>