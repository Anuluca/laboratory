<template src="./index.html" />

<script lang="ts">
import { defineComponent, reactive, ref, toRefs, onMounted } from "vue";

export default defineComponent({
  name: "watchDigitalTime",
  displayNone:false,
  setup() {
    const data = reactive({
      nowHour: (new Date().getHours() < 10
              ? "0" + new Date().getHours()
              : new Date().getHours()) + "",
      nowMinute: (new Date().getMinutes() < 10
              ? "0" + new Date().getMinutes()
              : new Date().getMinutes()) + "",
      changeTime: () => {
        setInterval(() => {
          data.nowHour =
            (new Date().getHours() < 10
              ? "0" + new Date().getHours()
              : new Date().getHours()) + "";
          data.nowMinute =
            (new Date().getMinutes() < 10
              ? "0" + new Date().getMinutes()
              : new Date().getMinutes()) + "";
            displaynone = true
        }, 1000);
      },
    });
    data.changeTime();
    return {
      ...toRefs(data),
    };
  },
});
</script>

<style lang="scss" src="./index.scss"></style>
