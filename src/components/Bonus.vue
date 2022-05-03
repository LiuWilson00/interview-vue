<template>
  <div>
    <table>
      <thead>
        <tr>
          <th>Name</th>
          <th>Price change</th>
          <th>Last price</th>
          <th>aggTrade price</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>BNB/BTC</td>
          <td>0.0015</td>
          <td>0.0025</td>
          <td>0.001</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>
<style></style>
<script>
// import axios from "axios";
/*
請利用binance api實作real-time的虛擬貨幣資料顯示小功能:
    文件連結:https://binance-docs.github.io/apidocs/spot/en/#aggregate-trade-streams

  基本題:
    1.在畫面上real-time顯示btcusdt的ticker data
  加分題:
    2.在畫面上同時real-time顯示btcusdt.ethusdt.bnbusdt.solusdt.dogeusdt.adausdt的ticker data
    3.額外顯示aggTrade data

  備註:
    1.原則上所有樣式都已經設定完畢,但不限制更改或調整樣式.
    2.專案內已經引入完成專案所需的套件,但若有需求可自行安裝新的套件.
    3.可自行上網查找完成題目需要的資源.

*/

// ticker

// {
//   "e": "24hrTicker",  // Event type
//   "E": 123456789,     // Event time
//   "s": "BNBBTC",      // Symbol
//   "p": "0.0015",      // Price change
//   "P": "250.00",      // Price change percent
//   "w": "0.0018",      // Weighted average price
//   "x": "0.0009",      // First trade(F)-1 price (first trade before the 24hr rolling window)
//   "c": "0.0025",      // Last price
//   "Q": "10",          // Last quantity
//   "b": "0.0024",      // Best bid price
//   "B": "10",          // Best bid quantity
//   "a": "0.0026",      // Best ask price
//   "A": "100",         // Best ask quantity
//   "o": "0.0010",      // Open price
//   "h": "0.0025",      // High price
//   "l": "0.0010",      // Low price
//   "v": "10000",       // Total traded base asset volume
//   "q": "18",          // Total traded quote asset volume
//   "O": 0,             // Statistics open time
//   "C": 86400000,      // Statistics close time
//   "F": 0,             // First trade ID
//   "L": 18150,         // Last trade Id
//   "n": 18151          // Total number of trades
// }

// aggTrade

// {
//   "e": "aggTrade",  // Event type
//   "E": 123456789,   // Event time
//   "s": "BNBBTC",    // Symbol
//   "a": 12345,       // Aggregate trade ID
//   "p": "0.001",     // Price
//   "q": "100",       // Quantity
//   "f": 100,         // First trade ID
//   "l": 105,         // Last trade ID
//   "T": 123456785,   // Trade time
//   "m": true,        // Is the buyer the market maker?
//   "M": true         // Ignore
// }
export default {
  name: "Bonus",
  data() {
    return {
      socket: "wss://stream.binance.com:9443/ws",
    };
  },
  mounted() {
    this.init();
  },
  methods: {
    async init() {
      //   const ws = new WebSocket(this.socket);
    },
  },
};
</script>
