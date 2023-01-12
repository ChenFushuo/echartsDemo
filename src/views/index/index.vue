<template>
  <div class="echsrtsContain">
    <first-echarts :pieData="pieData"></first-echarts>
  </div>
</template>

<script>
import FirstEcharts from "./components/FirstEcharts.vue";
export default {
  name: "App",
  components: {
    FirstEcharts,
  },
  data() {
    return {
      pieData: [
        { value: 1048, name: "Search Engine" },
        { value: 735, name: "Direct" },
        { value: 580, name: "Email" },
        { value: 484, name: "Union Ads" },
        { value: 300, name: "Video Ads" },
      ],
    };
  },
  created() {
    this.changeOptions()
  },
  methods: {
    changeOptions() {
      setInterval(() => {
        let randomNum = Math.random().toFixed(3);
        this.pieData = [
          { value: randomNum * 100 + 100, name: "Search Engine" },
          { value: randomNum * 200 + 230, name: "Direct" },
          { value: randomNum * 10 + 158, name: "Email" },
          { value: randomNum * 1000 + 355, name: "Union Ads" },
          { value: randomNum * 500 + 498, name: "Video Ads" },
        ];
      }, 2000);
    },
  },
};
</script>

<style lang="scss" scoped>
.echsrtsContain {
  width: 800px;
  height: 600px;
  margin: 80px auto;
  // box-shadow: 2px 5px 4px 3px #eeeeee;
  box-shadow: 1px 2px 3px 4px rgba(0, 0, 0, 0.4);
}
</style>