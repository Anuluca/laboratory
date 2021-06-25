<template>
  <div class="out-box">
    <div class="black-plas">
      <div class="screen">
        12:30
      </div>
    </div>
    <div class="button-back">
      <div class="button"></div>
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
@font-face{
  font-family:'dpWatch';
  src:url('')
}
.out-box {
  width: 500px;
  height: 300px;
  margin: 0 auto;
  position: relative;
  border-radius: 10px;
  background-color: #f854a9;
  background-image: url('favicon.ico');
  .black-plas {
    width: 440px;
    height: 350px;
    position: relative;
    background-color: #30302e;
    border-radius: 10px 10px 0 10px;
    float: left;
    .screen {
      width: 390px;
      height: 300px;
      position: absolute;
      background-color: #72b073;
      border: 5px solid #0f281e;
      border-radius: 5px;
      top: 22px;
      left: 21px;
      font-size: 150px;
      text-align: center;
      line-height: 300px;
      color: #375030;
      box-shadow: 1px 1px 2px 2px #212322;
      -webkit-user-select: none;
      -moz-user-select: none;
      -ms-user-select: none;
      user-select: none;
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
