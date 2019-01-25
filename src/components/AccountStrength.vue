<template>
  <el-card header="Account Strength" class="account-strength">
    <el-row style="margin-top:30px"></el-row>
    <el-row style="margin:40px 80px">
      <el-progress :text-inside="true" :stroke-width="18" :percentage="90" color="cornflowerblue"></el-progress>
    </el-row>
    <el-row style="margin:40px">
      <label style="color:lightgrey">1 step remaining</label>
    </el-row>
    <hr style="opacity:0.3">
    <el-row class="step" v-for="step in steps" :key="step.index">
      <i class="fas fa-check-circle" :class="step.completed ? 'complete' : 'incomplete'"></i>
      <label style="margin-left:80px">{{step.label}}</label>
    </el-row>
  </el-card>
</template>

<script>
export default {
  data() {
    return {
      steps: [
        { index: 1, label: "Registration Complete", completed: true },
        { index: 2, label: "Set Recurring Investment", completed: true },
        { index: 3, label: "Link Funding Source", completed: true },
        { index: 4, label: "Get Your Account to $10", completed: true },
        { index: 5, label: "Get Your Account to $100", completed: false }
      ]
    };
  }
};
</script>

<style scoped>
.el-card.account-strength {
  box-shadow: none;
  margin-top: 10px;
}

.fa-check-circle {
  font-size: 20px;
}

.step {
  padding: 10px;
  text-align: left;
  margin-left: 80px;
}

.complete {
  color: cornflowerblue;
}

.incomplete {
  color: grey;
  opacity: 0.5;
}
</style>