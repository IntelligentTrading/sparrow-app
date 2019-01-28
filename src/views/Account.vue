<template>
  <div class="home">
    <el-row>
      <el-card class="chart">
        <el-row style="margin-bottom:80px">
          <label style="font-size:20px;color:cornflowerblue;">Your Account Activity</label>
        </el-row>
        <el-row :gutter="24">
          <el-col :span="6">
            <stat statLabel="Total Invested" :amount="this.account.invested"></stat>
          </el-col>
          <el-col :span="6">
            <stat statLabel="Total Gain/Loss" :amount="this.account.profit"></stat>
          </el-col>
          <el-col :span="6">
            <stat statLabel="Withdrawn" :amount="this.account.withdrawn"></stat>
          </el-col>
          <el-col :span="6">
            <stat statLabel="Referrals" :amount="this.account.referrals"></stat>
          </el-col>
        </el-row>
      </el-card>
    </el-row>
    <el-row :gutter="24">
      <el-col :span="12">
        <el-row style="margin-bottom:30px">
          <el-card header="Pending">
            <div style="padding:20px 0px;border-bottom: 1px solid whitesmoke;">
              <el-row>
                <el-col :span="2" style="color:lightgrey;text-align:left;padding-top:15px">
                  <i class="far fa-clock"></i>
                </el-col>
                <el-col :span="16" style="display: flex; flex-direction:column; text-align:left">
                  <el-row>Recurring Investment</el-row>
                  <el-row style="padding: 10px 0px;">
                    <i class="fas fa-circle step-done"></i>
                    <i class="fas fa-circle step-done"></i>
                    <i class="fas fa-circle step-done"></i>
                    <i class="fas fa-circle step-done"></i>
                    <i class="fas fa-circle step-pending"></i>
                    <label style="font-style: italic;color: gray;">Transferring</label>
                  </el-row>
                </el-col>
                <el-col
                  :span="6"
                  style="color:grey;text-align:right;padding-top: 15px;padding-right: 20px;"
                >$50.00</el-col>
              </el-row>
            </div>
            <div style="display: flex;margin: 20px 0px 0px 0px;font-size: 14px;">
              <label>Total Pending:</label>
              <label
                style="color: cornflowerblue;font-weight: 600;margin-left: auto;margin-right: 20px;"
              >$50.00</label>
            </div>
          </el-card>
        </el-row>
        <el-row>
          <el-card>
            <div slot="header" style="display:flex">
              <label>Portfolio Value</label>
              <label class="amount">${{this.account.portfolio}}</label>
            </div>
            <div>
              <allocation :datacollection="this.datacollection"></allocation>
            </div>
          </el-card>
        </el-row>
      </el-col>
      <el-col :span="12">
        <el-card header="Transactions History">
          <div style="padding:0px 30px">
            <el-row v-for="transaction in transactions" :key="transaction.id">
              <transaction :transaction-data="transaction"></transaction>
            </el-row>
          </div>
          <el-pagination background layout="prev, pager, next" :total="30" style="padding:10px"></el-pagination>
        </el-card>
      </el-col>
    </el-row>
  </div>
</template>

<script>
import Stat from "../components/Statistic";
import Allocation from "../components/Allocation";
import transactions from "../data/transactions";
import Transaction from "../components/Transaction";

export default {
  name: "account",
  components: { Stat, Allocation, Transaction },
  data() {
    return {
      account: {
        withdrawn: "200.00",
        referrals: "0.00",
        invested: "6,450.00",
        profit: "4,323.65",
        portfolio: "11,560.50"
      },
      transactions: transactions,
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
  }
};
</script>
<style scoped>
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
}

.amount {
  margin-left: auto;
  color: cornflowerblue;
  font-weight: 500;
}

.step-done {
  color: cornflowerblue;
  margin-right: 10px;
  font-size: 12px;
}

.step-pending {
  color: lightgrey;
  margin-right: 10px;
  font-size: 10px;
  padding-bottom: 1px;
  vertical-align: middle;
}
</style>

