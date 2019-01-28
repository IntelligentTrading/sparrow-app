<template>
  <div class="back">
    <el-button circle @click="goBack">
      <i class="fas fa-arrow-left arrow"></i>
    </el-button>
    <label class="location">{{this.location}}</label>
  </div>
</template>

<script>
export default {
  props: ["to"],
  computed:{
      location:function(){
          if(this.$props.to == null){
              return 'Back'
          }
          return this.$props.to
      }
  },
  methods: {
    goBack: function(){
        this.$router.go(-1)
    }
  }
};
</script>

<style scoped>
.back {
  margin: 10px;
  text-align: left;
}
.arrow {
  color: cornflowerblue;
}

.location {
  margin: 10px;
  font-weight: 500px;
}
</style>