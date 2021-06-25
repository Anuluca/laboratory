<template>
  <div class="poke-watch">
    <div class="out-box" :class="nowType">
      <div class="black-plas">
        <div class="top-black" :class="{ 'close-black': ifCloseAnim }"></div>
        <div class="screen">
          <div v-if="nowPageNum == 1" class="page-one"><span>12:30</span></div>
          <div v-else-if="nowPageNum == 2" class="page-two"></div>
        </div>
        <div class="bottom-black" :class="{ 'close-black': ifCloseAnim }"></div>
      </div>
      <div class="button-back">
        <div class="button" @Click="changePage('Next')"></div>
      </div>
    </div>
    <div style="margin-top:100px">
      <div @Click="changeType('blue-type')">切换到蓝色款</div>
      <div @Click="changeType('red-type')">切换到红色款</div>
      <div @Click="changeType('orange-type')">切换到橙色款</div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive, ref, toRefs, onMounted } from "vue";

export default defineComponent({
  name: "pokeWatch",
  // components: {
  //   HelloWorld,
  // },
  setup() {
    const data = reactive({
      ifCloseAnim: false,
      nowPageNum: 1,
      pageMax: 2,
      nowType: "red-type",

      //翻页
      changePage: (position: any) => {
        if (position == "Next") {
          setTimeout(() => {
            if (data.nowPageNum != data.pageMax) {
              data.nowPageNum++;
            } else {
              data.nowPageNum = 1;
            }
          }, 500);
        }
        data.ifCloseAnim = true;
        setTimeout(() => {
          data.ifCloseAnim = false;
        }, 500);
      },

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

<style lang="scss" src="./index.scss"></style>
