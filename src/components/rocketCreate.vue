<template>
  <div class="about">
        <v-container>
          <v-flex xs12>
            <v-text-field v-model="item.name" label="My Var" required></v-text-field>
          </v-flex>
          <v-flex xs12>
            <v-text-field v-model="item.country" label="My Bool" required></v-text-field>
          </v-flex>
          <v-flex xs12>
            <v-text-field v-model="item.cost" label="My Cost" required></v-text-field>
          </v-flex>
      <v-btn @click="submitCreate()">Create</v-btn>
      {{error}}
      {{returnedItem}}
        </v-container>
  </div>
</template>

<script>
import gql from "graphql-tag";
export default {
  data: () => ({
    error: "",
    item: {
      name: "",
      country: "",
      cost: ""
    },
    returnedItem: {}
  }),
  methods: {
    submitCreate: function() {
      this.$apollo.mutate({
          mutation: gql`
            mutation addRocket(
              $name: String!
              $country: String!
              $cost: Int!
            ) {
              createRocket(
                data: {
                  name: $name,
                  country: $country,
                  cost: $cost,
                }
              ) {
                name,
                country,
                cost
              }
            }
          `,
          variables: {
            name: this.item.name,
            country: this.item.country,
            cost: this.item.cost,
          }
        })
        .then(res => {
          this.returnedItem = res.data;
        })
        .catch(err => {
          this.error = err;
        });
    }
  }
};
</script>