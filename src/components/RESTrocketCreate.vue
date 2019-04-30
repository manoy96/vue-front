<template>
  <div>
    <v-container>
      <v-card class="pa-3" dark>
        <h1>Create a RESTful rocket</h1>
        <v-layout column >
          <v-flex>
            <v-text-field v-model="name" label="Name" required></v-text-field>
          </v-flex>
          <v-flex>
            <v-text-field v-model="country" label="Country" required></v-text-field>
          </v-flex>
          <v-flex>
            <v-text-field v-model="price" label="Cost" ></v-text-field>
          </v-flex>
          <v-flex >
            <v-text-field v-model="company" label="Company" ></v-text-field>
          </v-flex>
        </v-layout>
        <v-btn @click="createRocket" color="info">Create Rocket</v-btn>
      </v-card>
    </v-container>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      name: "",
      country: "",
      price: "",
      company: "",
      result: "test"
    };
  },
  methods: {
    createRocket() {
      const rocketData = {
        name: this.item.name,
        country: this.item.country,
        price: parseInt(this.item.price),
        company: this.item.company
      };
      console.log(rocketData);
      axios
        .post(
          "https://sleepy-taiga-70117.herokuapp.com/products/create",
          rocketData
        )
        .then(res => {
          console.log("rocket Created");
          this.$router.push("/");
        })
        .catch(error => console.log(error));
    }
  }
};
</script>

<style scoped>
</style>