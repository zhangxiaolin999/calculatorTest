<template>
  <div class="home">
    <div class="Box">
      <div class="navTop">
        <ul class="menu">
          <li id="x">
            <!-- <span>x</span> -->
          </li>
          <li id="minus">
            <!-- <span>-</span> -->
          </li>
          <li id="plus">
            <!-- <span>+</span> -->
          </li>
        </ul>
        <!--计算区域开始-->
        <div class="scope">
          <span class="numberCont">{{ num }}</span>
        </div>
        <!--计算区域结束-->
        <!--操作区域开始-->
        <div class="optionScope">
          <div v-if="true" class="operations">AC</div>
          <div v-else class="operations">C</div>
          <div class="operations">+/-</div>
          <div class="operations">%</div>
          <div class="Conversion">÷</div>
          <div class="Digital">7</div>
          <div class="Digital">8</div>
          <div class="Digital">9</div>
          <div class="Conversion">x</div>
          <div class="Digital">4</div>
          <div class="Digital">5</div>
          <div class="Digital">6</div>
          <div class="Conversion">-</div>
          <div class="Digital">1</div>
          <div class="Digital">2</div>
          <div class="Digital">3</div>
          <div class="Conversion">+</div>
          <div style="width:114px" class="Digital">0</div>
          <div class="Digital">.</div>
          <div class="Conversion">=</div>
        </div>
        <!--操作区域结束-->
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Home",
  data() {
    return {
      num: 0
    };
  }
};
</script>
<style scoped>
* {
  list-style: none;
  padding: 0px;
  margin: 0px;
}
.Box {
  width: 230px;
  height: 321px;
  border: 2px solid #333;
  border-radius: 4px;
}
.navTop {
  height: 80px;
  background-color: #57595b;
}
.menu {
  display: flex;
}
ul li {
  display: inline-block;
  height: 12px;
  width: 12px;
  margin-right: 5px;
  margin-top: 3px;
}
#x {
  margin-left: 5px;
  background-color: #ff223a;
  border-radius: 50%;
}
#minus {
  background-color: #ffdb00;
  border-radius: 50%;
}
#plus {
  background-color: #00d842;
  border-radius: 50%;
}
.scope {
  height: 63px;
  background-color: #57595b;
  position: relative;
}
.numberCont {
  font-size: 40px;
  color: #fff;
  position: absolute;
  bottom: -10px;
  right: 5px;
}

.optionScope div {
  width: 56.5px;
  height: 47.5px;
  border-right: 1px solid #56575a;
  border-top: 1px solid #56575a;
  line-height: 46px;
  font-size: 20px;
  float: left;
  color: #fff;
}
.operations {
  background-color: #646568;
}
.Conversion {
  background-color: #ff9a00;
}
.Digital {
  background-color: #7c7d7f;
}
</style>
