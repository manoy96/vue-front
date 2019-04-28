<template>
  <div class="about">
    <v-container>
      <v-flex xs12>
        <v-text-field v-model="item.name" label="Rocket Name" required></v-text-field>
      </v-flex>
      <v-flex xs12>
        <v-text-field v-model="item.country" label="Country" required></v-text-field>
      </v-flex>
      <v-flex xs12>
        <v-text-field v-model="item.cost" label="Cost" required></v-text-field>
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

      <v-btn @click="submitCreate()" dark>Create</v-btn>
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
      cost: "",
      payloadLeo: "",
      payloadGto: "",
      kgLeo: "",
      kgGto: "",
      url: ""
    },
    returnedItem: {}
  }),
  methods: {
    submitCreate: function() {
      this.$apollo
        .mutate({
          mutation: gql`
            mutation addRocket(
              $name: String!
              $country: String!
              $cost: Int!
              $payloadLeo: Int
              $payloadGto: Int
              $kgLeo: Int
              $kgGto: Int
              $url: String
            ) {
              createRocket(
                data: { 
                  name: $name, 
                  country: $country, 
                  cost: $cost, 
                  payloadLeo: $payloadLeo, 
                  payloadGto: $payloadGto, 
                  kgLeo: $kgLeo,
                  kgGto: $kgGto,
                  url: $url 
                  }
              ) {
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
          this.returnedItem = res.data;
        })
        .catch(err => {
          this.error = err;
        });
    }
  }
};
</script>