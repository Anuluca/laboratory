<template src="./index.html" />

<script lang="ts">
import { defineComponent, reactive, ref, toRefs, onMounted } from "vue";

export default defineComponent({
  name: "watchCaculator",
  setup() {
    const data = reactive({
      numbers: [1, 2, 3, 4, 5, 6, 7, 8, 9],
      screenNumber: "",
      lastNumber:"",
      hasColor: false,

      //点击数字
      chooseNumber: (number: any) => {
        data.screenNumber += number;

        if (data.screenNumber != "") {
          data.hasColor = true;
        }
      },

      //点击清空
      clear:()=>{
        data.screenNumber = ''
      },

      //计算
      sym:(name:any)=>{
        if(name == 'plus'){
          data.lastNumber = JSON.parse(JSON.stringify(data.screenNumber))
          data.screenNumber = ''
        }
      }

    });
    return {
      ...toRefs(data),
    };
  },
});
</script>

<style lang="scss" src="./index.scss"></style>
