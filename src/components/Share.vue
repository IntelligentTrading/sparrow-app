<template>
  <el-card header="Share the Wealth" class="share">
    <el-row style="margin-top:30px">
      <i class="fab fa-facebook-square share-icon" style="color:#4A68ad;"></i>
      <i class="fab fa-twitter share-icon" style="color:#4A9ee8;background:white;"></i>
      <i class="far fa-envelope share-icon" style="color:#4A68ad;"></i>
      <i class="fab fa-reddit share-icon" style="color:#ec5428;background:white;"></i>
    </el-row>
    <el-row style="margin:40px">
      <label>Invite friends and get $5
        <br>when they invest with Sparrow
      </label>
    </el-row>
    <el-row>
      <el-button type="primary" round style="background:cornflowerblue;margin-bottom:7px">Learn More</el-button>
    </el-row>
  </el-card>
</template>

<script>
export default {};
</script>

<style scoped>
.el-card.share {
  box-shadow: none;
  margin-top: 30px;
}

.share-icon {
  font-size: 32px;
  margin: 10px;
}
</style>