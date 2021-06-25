<template src="./index.html" />

<script lang="ts">
import { defineComponent, reactive, ref, toRefs, onMounted } from "vue";

export default defineComponent({
  name: "watchCaculator",
  setup() {
    const data = reactive({
      numbers: [1, 2, 3, 4, 5, 6, 7, 8, 9],
      hasColor: false,
      screenNumber: "", //屏幕上显示的数据
      lastNumber: "", //储存的数据
      nowSym: "", //当前计算符号

      //点击数字
      chooseNumber: (number: any) => {
        data.screenNumber += number;

        if (data.screenNumber != "") {
          data.hasColor = true;
        }
      },

      //点击清空
      clear: () => {
        data.screenNumber = "";
      },

      //计算
      sym: (name: any) => {
        if (name == "plus") {
          data.lastNumber = JSON.parse(JSON.stringify(data.screenNumber));
          data.screenNumber = "";
          data.nowSym = "plus";
        } else if (name == "minus") {
          data.lastNumber = JSON.parse(JSON.stringify(data.screenNumber));
          data.screenNumber = "";
          data.nowSym = "minus";
        } else if (name == "dengyu") {
          if (data.nowSym == "plus") {
            data.screenNumber = (parseFloat(data.lastNumber) + parseFloat(data.screenNumber)).toString();
          } else if (data.nowSym == "minus") {
            data.screenNumber = (parseFloat(data.lastNumber) - parseFloat(data.screenNumber)).toString();
          }
          data.lastNumber = "";
        }
      },
    });
    return {
      ...toRefs(data),
    };
  },
});
</script>

<style lang="scss" src="./index.scss"></style>
