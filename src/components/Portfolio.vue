<template>
  <div>
    <label class="portfolio-label">
      Your portfolio value is
      <b>$11500</b>
    </label>
    <el-row>
      <el-col :span="23">
        <trend
          :data="prices"
          :gradient="['#8d8dca', '#6262c5', 'cornflowerblue']"
          auto-draw
          :auto-draw-duration=1500
          auto-draw-easing="ease-in"
        ></trend>
      </el-col>
      <el-col :span="1" class="price-col">
        <label class="price-label">12K</label>
        <label class="price-label">10K</label>
        <label class="price-label">5K</label>
      </el-col>
    </el-row>
    <hr style="opacity:0.3">
    <el-row class="months">
      <el-col :span="2">JAN</el-col>
      <el-col :span="2">FEB</el-col>
      <el-col :span="2">MAR</el-col>
      <el-col :span="2">APR</el-col>
      <el-col :span="2">MAY</el-col>
      <el-col :span="2">JUN</el-col>
      <el-col :span="2">JUL</el-col>
      <el-col :span="2">AUG</el-col>
      <el-col :span="2">SEP</el-col>
      <el-col :span="2">OCT</el-col>
      <el-col :span="2">NOV</el-col>
      <el-col :span="2">DEC</el-col>
    </el-row>
  </div>
</template>
<script>
import Trend from "vuetrend";

export default {
  name: "Portfolio",
  components: { Trend },
  data() {
    return {
      prices: [0, 5, 4.5, 6, 7, 14, 12, 9, 10, 11, 14, 13, 15]
    };
  }
};
</script>
<style>
.months {
  font-size: 12px;
  color: lightgrey;
}

.price-label {
  font-size: 12px;
  color: lightgrey;
  height: 100%;
}

.price-col {
  display: flex;
  flex-direction: column;
  height: 250px;
}

.portfolio-label {
  font-size: 20px;
  color: cornflowerblue;
}
</style>
