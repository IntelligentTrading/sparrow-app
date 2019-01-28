<template>
  <div>
    <el-row style="padding:20px">
      <label class="investment-label">One Time</label>
    </el-row>
    <el-row>
      <el-input class="biginput" placeholder="0.00">
        <template slot="prepend">$</template>
      </el-input>
    </el-row>
    <el-row style="padding:20px">
      <el-button
        class="suggestion"
        round
        v-for="suggestion in suggestions"
        :key="suggestion"
      >$ {{suggestion}}</el-button>
    </el-row>
    <el-button class="invest" round>Invest</el-button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      suggestions: [5, 25, 50, 100]
    };
  }
};
</script>

<style>
.suggestion {
  background: lightgray;
  width: 80px;
}

.biginput .el-input__inner {
  border: transparent;
  height: 100px !important;
  font-weight: 100;
  font-size: 72px;
  color: cornflowerblue;
  text-align: left;
}
.biginput .el-input-group__prepend {
  border: transparent;
  font-size: 42px;
  background: transparent;
  vertical-align: middle;
  color: cornflowerblue;
}

.biginput {
  width: 300px;
}
</style>