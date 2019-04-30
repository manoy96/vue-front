<template>
   <v-card flat tile style="border:1px solid #ccc;margin: 10px;">
        <v-img :src="rocket.url" height="400px" class="black--text" style="text-align: center;background-color:#F0F0F0;">
            <!-- <h2 class="headline mb-0" color="#ffffff">{{ rocket.name }}</h2> -->
        </v-img>
        <v-card-title primary-title color="blue-grey darken-2">
            <div>
                <ul>
                  <li>rocket ID: {{ rocket.id }}</li>
                    <br>
                    <li>Name: {{ rocket.name }}</li>
                    <br>
                    <li>Country: {{ rocket.country }} </li>
                    <br>
                    <li>Cost: ${{ rocket.cost }} </li>
                    <br>
                    <li>Payload to LEO: ${{ rocket.payloadLeo }} </li>
                    <br>
                    <li>Payload to GTO: ${{ rocket.payloadGto }}</li>
                    <br>
                    <li>Price/KG to LEO: ${{ rocket.kgLeo }} </li>
                    <br>
                    <li>Price/KG to GTO: ${{ rocket.kgGto }} </li>
                </ul>
            </div>
        </v-card-title>
    </v-card>
</template>

<script>
import gql from "graphql-tag";

export default {
  name: 'rocketCard',
  props: {
    rocket: {
      type: Object,
      required: true
    }
  }
};
</script>

<style scoped>
ul li {
  list-style-type: none;
}
</style>

