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
  name: "Home",
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

<style lang="scss">
@font-face {
  font-family: "dpWatch";
  src: url("../assets/font/PlatinumBeatBTN.woff2");
}
.poke-watch {
  .red-type {
    background-color: #f854a9;
  }
  .blue-type {
    background-color: #3457f3;
  }
  .orange-type {
    background-color: #eb935a;
  }
  .out-box {
    width: 500px;
    height: 300px;
    margin: 0 auto;
    position: relative;
    border-radius: 10px;
    .black-plas {
      width: 440px;
      height: 350px;
      position: relative;
      background-color: #30302e;
      border-radius: 10px 10px 0 10px;
      float: left;
      .top-black,
      .bottom-black {
        position: absolute;
        width: 391px;
        height: 0;
        transition: all 0.5s;
        left: 26px;
        background-color: #0f281e;
        z-index: 1;
      }
      .close-black {
        height: 160px;
      }
      .top-black {
        top: 27px;
      }
      .bottom-black {
        bottom: 23px;
      }
      .screen {
        width: 390px;
        height: 300px;
        position: absolute;
        background-color: #72b073;
        border: 5px solid #0f281e;
        border-radius: 5px;
        top: 22px;
        left: 21px;
        box-shadow: 1px 1px 2px 2px #212322;
        .page-one {
          display: block;
          margin-left: 13px;
          font-size: 100px;
          text-align: center;
          color: #375030;
          overflow: hidden;
          height:300px;
          font-family: "dpWatch";
          letter-spacing: 12px;
          -webkit-user-select: none;
          -moz-user-select: none;
          -ms-user-select: none;
          user-select: none;
          span{
            display: block;
          transform: scale(1, 2.7);
          line-height: 300px;
          }
        }
        .page-two {
        }
      }
    }
    .button-back {
      width: 60px;
      height: 200px;
      background-color: #30302e;
      border-radius: 0 30px 30px 0;
      margin-top: 150px;
      position: relative;
      float: left;
      z-index: 2;
      .button {
        position: absolute;
        width: 50px;
        height: 150px;
        top: 25px;
        left: -5px;
        background-color: #f53a3f;
        border-radius: 23px;
        box-shadow: inset 0px -8px 0px 0px #f47a78;
        cursor: pointer;
        transition: all 0.08s;
      }
      .button:active {
        background-color: #ca3237;
        box-shadow: inset 0px 8px 0px 0px #df4a4f;
      }
    }
  }
}
</style>
