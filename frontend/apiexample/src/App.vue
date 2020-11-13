<template>
  <div id="app">
    <upload-car></upload-car>
    <view-cars></view-cars>
  </div>
</template>

<script>
import ViewCars from "./components/ViewCars.vue";
import UploadCar from "./components/UploadCar.vue";
export default {
  name: "App",
  components: {
    ViewCars,
    UploadCar,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
