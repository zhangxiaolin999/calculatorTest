<template>
  <div class="home">
    <div class="Box">
      <div class="navTop">
        <ul class="menu">
          <li id="x">
            <span>x</span>
          </li>
          <li id="minus">
            <span>-</span>
          </li>
          <li id="plus">
            <span>+</span>
          </li>
        </ul>
        <!--计算区域开始-->
        <div class="scope">
          <span class="numberCont">{{ num }}</span>
        </div>
        <!--计算区域结束-->
        <!--操作区域开始-->
        <div class="optionScope">
          <div v-if="operaStats" class="operations" @click="AC">AC</div>
          <div v-else class="operations" @click="C">C</div>
          <div class="operations" @click="addSubtract">+/-</div>
          <div class="operations" @click="percentEncoding">%</div>
          <div class="Conversion" @click="addition">
            <div class="symbol">÷</div>
          </div>
          <div class="Digital" @click="numSeven">7</div>
          <div class="Digital" @click="numEight">8</div>
          <div class="Digital" @click="numNine">9</div>
          <div class="Conversion" @click="ride">
            <div class="symbol">x</div>
          </div>
          <div class="Digital" @click="numFour">4</div>
          <div class="Digital" @click="numFive">5</div>
          <div class="Digital" @click="numSix">6</div>
          <div class="Conversion" @click="minus">
            <div class="symbol">-</div>
          </div>
          <div class="Digital" @click="numOne">1</div>
          <div class="Digital" @click="numTwo">2</div>
          <div class="Digital" @click="three">3</div>
          <div class="Conversion" @click="plus">
            <div class="symbol">+</div>
          </div>
          <div style="width:114px" class="Digital" @click="zero">0</div>
          <div class="Digital dot" @click="dot">.</div>
          <div class="Conversion" @click="equal">
            <div class="symbol">=</div>
          </div>
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
      num: 0,
      operator: null,
      numArr: []
    };
  },
  computed: {
    operaStats() {
      return this.num === 0 ? true : false;
    }
  },
  methods: {
    AC() {},
    C() {
      this.num = 0;
      this.operator = null;
      this.numArr = [];
    },
    addSubtract() {
      this.operator = "+/-";
    },
    percentEncoding() {
      this.operator = "%";
    },
    addition() {
      this.operator = "÷";
    },
    numSeven() {
      if (this.num.length >= 10 && this.operator === "") return;
      if (!this.operator) this.num = 7;
      if (!this.operator) {
        this.numArr.push(7);
        let temporary = this.numArr.join("");
        this.num = temporary;
      }
    },
    numEight() {
      if (this.num.length >= 10 && this.operator === "") return;
      if (!this.operator) this.num = 8;
      if (!this.operator) {
        this.numArr.push(8);
        let temporary = this.numArr.join("");
        this.num = temporary;
      }
    },
    numNine() {
      if (this.num.length >= 10 && this.operator === "") return;
      if (!this.operator) this.num = 9;
      if (!this.operator) {
        this.numArr.push(9);
        let temporary = this.numArr.join("");
        this.num = temporary;
      }
    },
    ride() {
      this.operator = "x";
    },
    numFour() {
      if (this.num.length >= 10 && this.operator === "") return;
      if (!this.operator) this.num = 4;
      if (!this.operator) {
        this.numArr.push(4);
        let temporary = this.numArr.join("");
        this.num = temporary;
      }
    },
    numFive() {
      if (this.num.length >= 10 && this.operator === "") return;
      if (!this.operator) this.num = 5;
      if (!this.operator) {
        this.numArr.push(5);
        let temporary = this.numArr.join("");
        this.num = temporary;
      }
    },
    numSix() {
      if (this.num.length >= 10 && this.operator === "") return;
      if (!this.operator) this.num = 6;
      if (!this.operator) {
        this.numArr.push(6);
        let temporary = this.numArr.join("");
        this.num = temporary;
      }
    },
    minus() {
      this.operator = "-";
    },
    numOne() {
      if (this.num.length >= 10 && this.operator === "") return;
      if (!this.operator) this.num = 1;
      if (!this.operator) {
        this.numArr.push(1);
        let temporary = this.numArr.join("");
        this.num = temporary;
      }
    },
    numTwo() {
      if (this.num.length >= 10 && this.operator === "") return;
      if (!this.operator) this.num = 2;
      if (!this.operator) {
        this.numArr.push(2);
        let temporary = this.numArr.join("");
        this.num = temporary;
      }
    },
    three() {
      if (this.num.length >= 10 && this.operator === "") return;
      if (!this.operator) this.num = 3;
      if (!this.operator) {
        this.numArr.push(3);
        let temporary = this.numArr.join("");
        this.num = temporary;
      }
    },
    plus() {
      this.operator = "+";
    },
    zero() {
      if (this.num.length >= 10 && this.operator === "") return;
      if (!this.operator) this.num = 0;
      if (!this.operator) {
        this.numArr.push(0);
        let temporary = this.numArr.join("");
        this.num = temporary;
      }
    },
    dot() {},
    equal() {}
  },
  beforeCreate() {
    document.onselectstart = () => {
      return false;
    };
  }
};
</script>
<style scoped>
.home {
  cursor: default;
}
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
  position: relative;
}

ul li span {
  position: absolute;
  top: -3px;
  left: 1px;
  font-size: 14px;
  font-weight: 300;
  color: #7c7d7f;
  display: none;
}
li span:hover {
  display: inline;
}

.dot {
  line-height: 50px;
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
  overflow: hidden;
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
  position: relative;
  background-color: #ff9a00;
}
.Digital {
  background-color: #7c7d7f;
}
.operations:active {
  background-color: #b3b4b6;
}
.Digital:active {
  background-color: #b5b5b7;
}
.Conversion:active {
  background-color: #d47900;
}
.Conversion .symbol {
  position: absolute;
}
</style>
