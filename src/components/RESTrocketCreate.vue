<template>
  <div>
    <v-container>
      <v-card>
        <h1>Create a RESTful rocket</h1>
        <v-layout row wrap>
          <v-flex xs4>
            <v-text-field v-model="name" label="Name" required></v-text-field>
          </v-flex>
          <v-flex xs4>
            <v-text-field v-model="description" label="Description" required></v-text-field>
          </v-flex>
          <v-flex xs4>
            <v-text-field v-model="url" label="URL" required></v-text-field>
          </v-flex>
          <v-flex xs4>
            <v-text-field v-model="emotion" label="Emotion" required></v-text-field>
          </v-flex>
          <v-flex xs4>
            <v-text-field v-model="genus" label="Genus" required></v-text-field>
          </v-flex>
        </v-layout>
        <v-btn @click="createrocket" color="info">Create</v-btn>
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
      description: "",
      url: "",
      emotion: "",
      genus: ""
    };
  },
  methods: {
    createrocket() {
      const rocket = {
        name: this.item.name,
        country: this.item.country,
        price: parseInt(this.item.price)
      };
      console.log(rocketData);
      axios
        .post(
          "https://floating-temple-55389.herokuapp.com/rockets/create",
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