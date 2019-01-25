<template>
  <el-card class="section">
    <el-row>
      <el-col :span="12" style="text-align:left">{{this.optionLabel}}</el-col>
      <el-col :span="10" class="ptype">{{this.optionValue}}</el-col>
      <el-col :span="2" class="ptype">
        <i class="fas fa-chevron-right"></i>
      </el-col>
    </el-row>
  </el-card>
</template>

<script>
export default {
  name: "Option",
  props: ["label", "to", "value"],
  data() {
    return {
      optionLabel: this.label,
      optionValue: this.value,
    };
  }
};
</script>

<style scoped>
.ptype {
  color: cornflowerblue;
  font-weight: 500;
  text-align: right;
}

.el-card.section {
  box-shadow: none;
  margin-top: 10px;
}
</style>