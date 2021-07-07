<template src="./index.html" />

<script lang="ts">
import { defineComponent, reactive, ref, toRefs, onMounted } from "vue";

export default defineComponent({
  name: "watchKokinggu",
  setup() {
    const data: any = reactive({
      numbers: 'n',

      //点击硬币
      roll: () => {
        
      },

    });
    return {
      ...toRefs(data),
    };
  },
});
</script>

<style lang="scss" src="./index.scss"></style>
