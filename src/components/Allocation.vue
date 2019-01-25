<template>
  <div>
    <el-row>
      <allocation-chart style="padding:60px" :collection="this.$props.datacollection"></allocation-chart>
    </el-row>
    <el-row>
      <div class="legend">
        <div class="legend-label" v-for="(symbol,index) in partitions.labels" :key="symbol">
          <i class="fas fa-circle" :style="'color:'+partitions.datasets[0].backgroundColor[index]"></i>
          <label style="margin:0px 5px">{{symbol}}</label>
          <label
            style="margin:0px 10px 0px 0px; font-weight:500"
          >{{partitions.datasets[0].data[index]}}%</label>
        </div>
      </div>
    </el-row>
  </div>
</template>

<script>
import AllocationChart from "./AllocationChart";
export default {
  props: ["datacollection"],
  data() {
    return {
      partitions: this.datacollection
    };
  },
  components: { AllocationChart }
};
</script>

<style scoped>
.legend {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  text-align: left;
  margin-left: 80px;
}
</style>