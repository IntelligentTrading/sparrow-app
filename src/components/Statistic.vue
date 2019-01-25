<template>
  <div style="display:flex;flex-direction:column;margin:10px;padding:20px">
    <label>{{this.$props.statLabel}}</label>
    <label class="amount-label">${{this.$props.amount}}</label>
  </div>
</template>

<script>
export default {
  props: ["statLabel", "amount"]
};
</script>

<style scoped>
.amount-label {
  color: cornflowerblue;
  padding: 20px;
  font-size: 20px;
  font-weight: 600;
}
</style>