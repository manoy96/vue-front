<template>
  <div>
    <v-container>
      <v-card class="pa-3" dark>
        <h1>Delete A Rocket</h1>
        <v-flex xs12>
          <v-text-field v-model="id" label="ID" required></v-text-field>
        </v-flex>
        <v-btn @click="deleteRocket" color="info">Delete</v-btn>
      </v-card>
    </v-container>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      id: this.$route.params.id,
      rocket: {}
    };
  },
  created() {
    axios
      .get("https://floating-temple-55389.herokuapp.com/rockets/all")
      .then(res => {
        this.rocket = res.data;
      })
      .catch(error => {
        console.log(error);
      });
  },
  props: {
    //
  },
  methods: {
    deleteRocket() {
      const rocketData = {
        id: this.id
      };
      console.log(rocketData);
      axios
        // .delete('https://floating-temple-55389.herokuapp.com/rockets/' + this.id + '/delete')
        .delete(
          "https://sleepy-taiga-70117.herokuapp.com/products/" +
            this.id +
            "/delete"
        )

        .then(res => {
          console.log("rocket Deleted");
          this.$router.push("/");
        })
        .catch(error => {
          console.log(error);
        });
    }
  }
};
</script>

<style scoped>
</style>