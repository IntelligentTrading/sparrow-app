<template>
  <div style="padding:20px;border-bottom: 1px solid whitesmoke;">
    <el-row>
      <el-col :span="2" :class="this.$props.transactionData.status" style="text-align:left">
        <i class="fas fa-circle"></i>
      </el-col>
      <el-col :span="16" style="display: flex;flex-direction: column; text-align:left">
        <label class="timestamp">{{this.$props.transactionData.timestamp}}</label>
        <label class="type">{{this.$props.transactionData.type}}</label>
      </el-col>
      <el-col :span="6" class="amount">$ {{this.$props.transactionData.amount}}</el-col>
    </el-row>
  </div>
</template>

<script>
export default {
  props: ["transaction-data"]
};
</script>

<style scoped>
.amount {
  color: grey;
  text-align: right;
}

.type {
  color: lightslategray;
}

.success {
  color: green;
}

.error {
  color: red;
}

.pending {
  color: gray;
}
</style>