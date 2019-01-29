<template>
  <div id="app">
    <top-bar></top-bar>
    <transition name="fade">
      <router-view/>
    </transition>
    <footer style="margin:20px 200px;opacity:0.5">
      <hr>Legal Notes
    </footer>
  </div>
</template>
<script>
import TopBar from "./components/TopBar";

export default {
  components: { TopBar }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  height: 100vh;
}
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s;
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
}

.el-card {
  box-shadow: none !important;
}
</style>
