<template>
  <div>
    <h2>Show All Rockets</h2>
    <v-flex xs12 md6 lg6>
      <v-btn dark color="info" v-on:click="getAllGraphql()">All</v-btn>
    {{myItem}}
    error: {{error}}
    </v-flex>
  </div>
</template>

<script>
import gql from "graphql-tag";
export default {
  data() {
    return {
      error: "",
      myItem: {}
    };
  },
  methods: {
    getAllGraphql: function() {
      this.$apollo
        .query({
          query: gql`
            query allRocket {
              rockets {
                id
                name
                country
                cost
                payloadLeo
                payloadGto
                kgLeo
                kgGto
                url
              }
            }
          `
        })
        .then(res => {
          this.myItem = res.data;
        })
        .catch(err => {
          this.error = err;
        });
    }
  }
};
</script>

<style>
</style>