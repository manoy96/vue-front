<template>
  <div class="about">
    <v-container xs12 md6 lg6>
      <h2>Update a Rocket</h2>
      <v-flex xs12>
        <v-text-field v-model="item.id" label="id" required></v-text-field>
      </v-flex>
      <v-flex xs12>
        <v-text-field v-model="item.name" label="Name" required></v-text-field>
      </v-flex>
       <v-flex xs12>
        <v-text-field v-model="item.cost" label="cost" required></v-text-field>
      </v-flex>
      <v-flex xs12>
        <v-text-field v-model="item.payloadLeo" label="Payload to reach Low Earth Orbit" ></v-text-field>
      </v-flex>
      <v-flex xs12>
        <v-text-field v-model="item.payloadGto" label="Payload to reach Geostationary transfer orbit" ></v-text-field>
      </v-flex>
       <v-flex xs12>
        <v-text-field v-model="item.kgLeo" label="Price per KG to reach Low Earth Orbit" ></v-text-field>
      </v-flex>
      <v-flex xs12>
        <v-text-field v-model="item.kgGto" label="Price per KG to reach Geostationary transfer orbit" ></v-text-field>
      </v-flex>
       <v-flex xs12>
        <v-text-field v-model="item.url" label="Image URL" ></v-text-field>
      </v-flex>
      <v-btn @click="submitUpdate()" dark>Update item</v-btn>
      {{ error }}
      {{ returneditem }}
    </v-container>
  </div>
</template>

<script>
import gql from "graphql-tag";
export default {
  data: () => ({
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
    returneditem: {}
  }),
  methods: {
    submitUpdate: function() {
      console.log(this.item);
      this.$apollo
        .mutate({
          mutation: gql`
            mutation updateitem(
              $id: ID
              $name: String!
              $country: String!
              $cost: Int!
              $payloadLeo: Int
              $payloadGto: Int
              $kgLeo: Int
              $kgGto: Int
              $url: String
            ) {
              updateRocket(
                data: {
                  name: $name
                  country: $country
                  cost: $cost
                  payloadLeo: $payloadLeo
                  payloadGto: $payloadGto
                  kgLeo: $kgLeo
                  kgGto: $kgGto
                  url: $url
                }
                where: { id: $id }
              ) {
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
          this.returneditem = res.data;
        })
        .catch(err => {
          this.error = err;
        });
    }
  }
};
</script>