<template src="./index.html"> </template>

<script lang="ts">
import { defineComponent, reactive, ref, toRefs, onMounted } from "vue";
import watchDigitalTime from "@/components/watchDigitalTime/index.vue";
import watchCaculator from "@/components/watchCaculator/index.vue";
import watchKokinggu from "@/components/watchKokinggu/index.vue";

export default defineComponent({
  name: "pokeWatch",
  components: {
    watchDigitalTime,
    watchCaculator
  },
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
