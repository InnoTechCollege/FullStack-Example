<template>
  <div>
    <h1 @click="getCars()">GET CARS</h1>
    <div class="car-container" v-for="car in cars" :key="car[3]">
      <h2>{{ car[0] }}</h2>
      <p>{{ car[1] }}</p>
      <img :src="car[2]" :alt="car[0]" />
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      cars: [],
    };
  },
  methods: {
    getCars: function () {
      axios
        .request({
          url: "http://127.0.0.1:5000/cars",
          method: "GET",
        })
        .then((response) => {
          console.log(response);
          this.cars = response.data;
        })
        .catch((error) => {
          console.log(error);
        });
    },
  },
};
</script>

<style scoped>
.car-container {
  max-width: 350px;
}
img {
  width: 100%;
}
</style>