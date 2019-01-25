<script>
import { Doughnut } from "vue-chartjs";
export default {
  extends: Doughnut,
  props: ["collection"],
  mounted() {
    this.renderChart(this.$props.collection, {
      legend: {
        display: false,
        maintainAspectRatio: true
      }
    });
  }
};
</script>

<style scoped>
</style>