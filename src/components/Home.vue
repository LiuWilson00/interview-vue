<template>
  <div class="clock">
    <form class="search-form">
      <input type="text" class="search" placeholder="City or State" />
      <ul class="suggestions">
        <li>Filter for a city</li>
        <li>or a state</li>
      </ul>
    </form>
  </div>
</template>
<style>
html {
  box-sizing: border-box;
  background: #ffc600;
  font-family: "helvetica neue";
  font-size: 20px;
  font-weight: 200;
}
*,
*:before,
*:after {
  box-sizing: inherit;
}
input {
  width: 100%;
  padding: 20px;
}

.search-form {
  max-width: 400px;
  margin: 50px auto;
}

input.search {
  margin: 0;
  text-align: center;
  outline: 0;
  border: 10px solid #f7f7f7;
  width: 120%;
  left: -10%;
  position: relative;
  top: 10px;
  z-index: 2;
  border-radius: 5px;
  font-size: 40px;
  box-shadow: 0 0 5px rgba(0, 0, 0, 0.12), inset 0 0 2px rgba(0, 0, 0, 0.19);
}

.suggestions {
  margin: 0;
  padding: 0;
  position: relative;
  /*perspective:20px;*/
}
.suggestions li {
  background: white;
  list-style: none;
  border-bottom: 1px solid #d8d8d8;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.14);
  margin: 0;
  padding: 20px;
  transition: background 0.2s;
  display: flex;
  justify-content: space-between;
  text-transform: capitalize;
}

.suggestions li:nth-child(even) {
  transform: perspective(100px) rotateX(3deg) translateY(2px) scale(1.001);
  background: linear-gradient(to bottom, #ffffff 0%, #efefef 100%);
}
.suggestions li:nth-child(odd) {
  transform: perspective(100px) rotateX(-3deg) translateY(3px);
  background: linear-gradient(to top, #ffffff 0%, #efefef 100%);
}

span.population {
  font-size: 15px;
}

.hl {
  background: #ffc600;
}

a {
  color: black;
  background: rgba(0, 0, 0, 0.1);
  text-decoration: none;
}
</style>
<script>
import axios from "axios";
/*
請實作以下連結之範例:
    範例連結:https://dustinhsiao21.github.io/Javascript30-dustin/06%20-%20Type%20Ahead/

  基本題:
    1.監聽input輸入之關鍵字,篩選API輸入之內容,並顯示於列表.
    2.列表中的欄位,請依照範例的格式顯示,包含數字的顯示方法.
  加分題:
    3.欄位的內容根據關鍵字加上標註,並給予背景顏色.
    4.輸入框清空後,顯示還原為初始狀態.
    5.用async/await 及 promise分別實作兩個呼叫api的methods.

  備註:
    1.原則上所有樣式都已經設定完畢,但不限制更改或調整樣式.
    2.專案內已經引入完成專案所需的套件,但若有需求可自行安裝新的套件.
    3.可自行上網查找完成題目需要的資源.

*/
export default {
  name: "HelloWorld",
  data() {
    return {
      endpoint:
        "https://gist.githubusercontent.com/Miserlou/c5cd8364bf9b2420bb29/raw/2bf258763cdddd704f8ffd3ea9a3e81d25e2c6f6/cities.json",
    };
  },
  mounted() {
    this.init();
  },
  methods: {
    async init() {
      const success = await axios(this.endpoint);
      console.log(success);
    },
  },
};
</script>
