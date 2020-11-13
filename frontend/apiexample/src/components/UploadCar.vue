<template>
  <div>
    <p>Car Name</p>
    <input v-model="carName" type="text" />
    <p>Car Description</p>
    <textarea v-model="carDescription"></textarea>
    <p>Car Image URL</p>
    <input v-model="carImage" type="text" />
    <button @click="uploadCar">Submit</button>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      carName: "",
      carDescription: "",
      carImage: "",
    };
  },
  methods: {
    uploadCar: function () {
      axios
        .request({
          url: "http://127.0.0.1:5000/cars",
          method: "POST",
          headers: {
            "Content-Type": "application/json",
          },
          data: {
            name: this.carName,
            description: this.carDescription,
            image: this.carImage,
          },
        })
        .then((response) => {
          console.log(response);
        })
        .catch((error) => {
          console.log(error);
        });
    },
  },
};
</script>

<style scoped>
</style>