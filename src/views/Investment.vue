<template>
  <div style="padding: 20px 200px">
    <back></back>
    <el-card header="Choose the investment you want to make:">
      <el-carousel
        trigger="click"
        indicator-position="none"
        arrow="always"
        :autoplay="false"
        style="height:450px"
      >
        <el-carousel-item
          class="investment-choice"
          v-for="item in investmentComponents"
          :key="item.id"
        >
          <component :is="item.component"></component>
        </el-carousel-item>
      </el-carousel>
    </el-card>
  </div>
</template>

<script>
import Back from "../components/Back";
import OneTime from "../components/OneTime";
import Recurring from "../components/Recurring";
// @ is an alias to /src
export default {
  name: "investment",
  components: { Back, OneTime, Recurring },
  data() {
    return {
      investmentComponents: [
        { id: 1, component: "OneTime" },
        { id: 2, component: "Recurring" }
      ]
    };
  }
};
</script>
<style>
.investment-choice {
  font-size: 20px;
  color: cornflowerblue;
  padding: 20px;
}

.investment-label {
  font-size: 21px;
  letter-spacing: 1px;
  font-weight: 500;
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

