<template>
  <div class="about">
    <v-container>
      <h2>View One Product</h2>
      <v-text-field v-model="item.id" label="ID" required></v-text-field>
      <v-btn v-on:click="getOneGraphql()">One Rocket</v-btn>
      <div v-show="isOpen">{{ error }} {{ item }}</div>
    </v-container>
  </div>
</template>

<script>
import gql from "graphql-tag";
export default {
  data() {
    return {
      error: "",
      item: {
        id: "",
        name: "",
        country: "",
        cost: "",
        payloadLeo: "",
        payloadGto: "",
        kgLeo: "",
        kgGto: "",
        url: ""
      },
      isOpen: false
    };
  },
  methods: {
    getOneGraphql: function() {
      this.$apollo
        .query({
          query: gql`
            query oneRocket($id: ID) {
              product(where: { id: $id }) {
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
          `,
          variables: {
            id: this.item.id,
            name: this.item.name,
            country: this.item.country,
            cost: parseInt(this.item.cost),
            payloadLeo: parseInt(this.item.payloadLeo),
            payloadGto: parseInt(this.item.payloadGto),
            kgLeo: parseInt(this.item.kgLeo),
            kgGto: parseInt(this.item.kgGto),
            url: this.item.url
          }
        })
        .then(res => {
          this.item = res.data;
        })
        .catch(err => {
          this.error = err;
        });
    },
    toggle: function() {
      this.isOpen = !this.isOpen;
    }
  }
};
</script>
<style>
</style>