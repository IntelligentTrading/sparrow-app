<template>
  <div style="padding:20px 200px; height:100vh">
    <back></back>
    <el-card header="Portfolio Allocation">
      <el-carousel arrow="always">
        <el-carousel-item>
          <el-row>
            <label class="allocationTitle">{{allocationType}}</label>
          </el-row>
          <el-row style="display: flex;justify-content: center; margin:30px">
            <label style="width:600px">
              A conservative portfolio is most appropriate for those with a lower tolerance for risk
              (though, all cryptocurrencies are highly speculative and riskier than traditional financial assets).
              This portfolio has more exposure to Bitcoin than an aggressive portfolio. You can find the portfolio allocation below.
            </label>
          </el-row>
          <el-row style="display:flex;justify-content:center">
            <allocation style="width:400px" :datacollection="this.datacollection"></allocation>
          </el-row>
        </el-carousel-item>
      </el-carousel>
      <el-row style="display:flex;align-items:center;justify-content:center">
        <el-col :span="1">
          <i class="fas fa-info-circle" style="color:lightgrey"></i>
        </el-col>
        <el-col :span="4">
          <div style="display:flex; flex-direction:column; text-align:left">
            <label style="color:lightgrey;font-weight:500">Recommended</label>
            <label>Conservative</label>
          </div>
        </el-col>
        <el-col :span="4">
          <el-button class="invest" round>Update</el-button>
        </el-col>
      </el-row>
    </el-card>
  </div>
</template>

<script>
import Allocation from "../components/Allocation";
import Back from "../components/Back";
// @ is an alias to /src
export default {
  name: "portfolio",
  data() {
    return {
      allocationType: "Conservative",
      datacollection: {
        labels: ["BTC", "ETH", "BCH", "LTC", "EOS", "ADA"],
        datasets: [
          {
            label: "Coins",
            backgroundColor: [
              "rgb(20,131,199)",
              "rgb(77,159,221)",
              "rgb(145,225,242)",
              "rgb(88,195,192)",
              "rgb(19,89,152)",
              "cornflowerblue"
            ],
            borderWidth: 0,
            hoverBorderWidth: 0,
            data: [80, 10, 5, 2, 2, 1]
          }
        ]
      }
    };
  },
  components: { Allocation, Back }
};
</script>
<style>
.el-carousel {
  padding: 20px;
  height: 70vh;
}

.el-carousel__container {
  position: initial;
}

.allocationTitle {
  color: cornflowerblue;
  font-size: 18px;
  font-weight: 600;
}

.el-carousel__arrow {
  color: cornflowerblue;
  background: whitesmoke;
}

.invest {
  background-image: linear-gradient(#5a86d6, cornflowerblue);
  color: white;
  border: none;
  margin: 30px;
  width: 180px;
}

.invest:hover {
  background-image: linear-gradient(cornflowerblue, #5a86d6);
  color: white;
  border: none;
}

.invest:active {
  color: white;
}
.invest:focus {
  color: white;
}
</style>

