<style lang="scss">
.waterfall {
  .title {
    margin-left: 10px;
    font-size: 18px;
    line-height: 43px;
  }
  #outer-box {
    position: relative;
    * {
      margin: 0;
      padding: 0;
    }
    .box > img {
      width: 400px;
      margin: 10px;
      display: block;
      opacity: 0.8;
    }
    .box > div {
      font-size: 50px;
      position: absolute;
      left: 20px;
      z-index: 2;
    }
    .box {
      position: relative;
      float: left;
      left: 0;
      top: 0;
    }
  }
}
</style>
<template>
  <div class="waterfall">
    <div class="title">
      <b>需求：</b>使用原生js实现，从左到右，由上至下见缝插针，列数适应页面。
    </div>
    <div class="title">
      <b>代码：</b>见<a href="anuluca.icu" target="_blank">简易瀑布流实现</a>
    </div>
    <div class="title">
      <b>实现效果：</b>
    </div>
    <div id="outer-box">
      <div class="box">
        <div>1</div>
        <img src="/img/waterfall/1.jpg" />
      </div>
      <div class="box">
        <div>2</div>
        <img src="/img/waterfall/2.jpg" />
      </div>
      <div class="box">
        <div>3</div>
        <img src="/img/waterfall/3.jpg" />
      </div>
      <div class="box">
        <div>4</div>
        <img src="/img/waterfall/4.jpg" />
      </div>
      <div class="box">
        <div>5</div>
        <img src="/img/waterfall/5.jpg" />
      </div>
      <div class="box">
        <div>6</div>
        <img src="/img/waterfall/6.jpg" />
      </div>
      <div class="box">
        <div>7</div>
        <img src="/img/waterfall/7.jpg" />
      </div>
      <div class="box">
        <div>8</div>
        <img src="/img/waterfall/8.jpg" />
      </div>
      <div class="box">
        <div>9</div>
        <img src="/img/waterfall/9.jpg" />
      </div>
      <div class="box">
        <div>10</div>
        <img src="/img/waterfall/10.jpg" />
      </div>
      <div class="box">
        <div>11</div>
        <img src="/img/waterfall/11.jpg" />
      </div>
      <div class="box">
        <div>12</div>
        <img src="/img/waterfall/12.jpg" />
      </div>
      <div class="box">
        <div>13</div>
        <img src="/img/waterfall/13.jpg" />
      </div>
    </div>
  </div>
</template>

<script>
import { defineComponent, reactive, toRefs, onMounted } from "vue";

export default defineComponent({
  name: "waterfall",
  setup() {
    const data = reactive({
      waterfall: () => {
        let box = document.getElementsByClassName("box");
        let outerWidth = document.getElementById("outer-box").clientWidth; //屏幕宽度
        let boxWidth = box[0].clientWidth; //单张图片的宽度
        var heightArr = []; //所有图片高度
        //图片列数
        let cols = parseInt(outerWidth / boxWidth);

        //遍历所有图片
        [...box].forEach((element, index) => {
          let boxHeight = element.offsetHeight;
          //是不是第一排
          if (index < cols) {
            heightArr[index] = boxHeight;
          } else {
            //取出第一排图片中的最小高度
            let minHeight = Math.min(...heightArr);
            //最小高度图片的索引
            let minIndex = heightArr.indexOf(minHeight);
            box[index].setAttribute(
              "style",
              `position:absolute;left:${minIndex *
                boxWidth}px;top:${minHeight}px`
            );
            // 高度追加
            heightArr[minIndex] += boxHeight;
          }
        });
      },
    });
    setTimeout(() => {
      data.waterfall();
    }, 1000);

    return {
      ...toRefs(data),
    };
  },
});
</script>
