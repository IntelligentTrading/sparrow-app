<template>
  <div class="home">
    <el-row style="display:flex; justify-content:flex-end">
      <router-link to="investment">
        <el-button class="payment">
          <i class="fas fa-hand-holding-usd"></i> Invest
        </el-button>
      </router-link>
      <router-link to="portfolio">
        <el-button class="payment">
          <i class="fas fa-wallet"></i> Portfolio Allocation
        </el-button>
      </router-link>
      <el-button class="payment">
        <i class="fas fa-piggy-bank"></i> Withdraw
      </el-button>
    </el-row>
    <el-row>
      <el-card class="chart">
        <portfolio></portfolio>
      </el-card>
    </el-row>
    <el-row :gutter="24">
      <el-col :span="12">
        <el-row>
          <portfolio-option label="Portfolio" value="Conservative" to="portfolio"/>
        </el-row>
        <el-row>
          <portfolio-option label="Recurring Investment" value="$50, Monthly" to="investment"/>
        </el-row>
        <el-row>
          <share></share>
        </el-row>
      </el-col>
      <el-col :span="12">
        <account-strength></account-strength>
      </el-col>
    </el-row>
  </div>
</template>

<script>
import Portfolio from "../components/Portfolio";
import PortfolioOption from "../components/Option";
import Share from "../components/Share";
import AccountStrength from "../components/AccountStrength";

export default {
  name: "home",
  components: { Portfolio, PortfolioOption, Share, AccountStrength },
  data() {
    return {
      prices: [0, 5, 4.5, 6, 7, 14, 12, 9, 10, 11, 14, 13, 15]
    };
  }
};
</script>
<style>
.home {
  padding: 20px 200px;
}

.el-card__header {
  text-align: left;
}

.el-card.chart {
  margin: 10px 0 20px;
  box-shadow: none !important;
  padding: 30px;
}

.el-button.payment {
  border-radius: 45px;
  background: white;
  color: cornflowerblue;
  font-weight: 100;
  margin: 5px
}
</style>

