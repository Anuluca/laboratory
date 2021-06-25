<template>
  <div class="out-box">
    <div class="black-plas">
      <div class="top-black"></div>
      <div class="screen">
        <span>12:30</span>
      </div>
      <div class="bottom-black"></div>
    </div>
    <div class="button-back">
      <div class="button" @Click="changePage('Next')"></div>
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
      temp: "1",
      changePage:(position: any) => {
        if(position == 'Next'){

        }
      }
      // addQa: () => {

      // },
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
.out-box {
  width: 500px;
  height: 300px;
  margin: 0 auto;
  position: relative;
  border-radius: 10px;
  background-color: #f854a9;
  .black-plas {
    width: 440px;
    height: 350px;
    position: relative;
    background-color: #30302e;
    border-radius: 10px 10px 0 10px;
    float: left;
    .top-black{
        position:absolute
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
      span {
        display: block;
        margin-left: 13px;
        transform: scale(1, 2.7);
        font-size: 100px;
        text-align: center;
        line-height: 300px;
        color: #375030;
        font-family: "dpWatch";
        letter-spacing: 12px;
        -webkit-user-select: none;
        -moz-user-select: none;
        -ms-user-select: none;
        user-select: none;
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
</style>
