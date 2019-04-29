<template>
  <v-flex xs12 sm6 offset-sm3>
    <v-card flat tile style="border:1px solid #ccc;margin: 10px;">
      <v-img
        aspect-ratio="3"
        :src="rocket.url"
        height="400px"
        class="black--text"
        style="text-align: center;background-color:#F0F0F0;"
      >
        <h3 class="headline mb-0">{{ rocket.name }}</h3>
      </v-img>
      <v-card-title primary-title>
        <div>
          <h3 class="headline mb-0">{{ rocket.name }}</h3>
        </div>
      </v-card-title>
    </v-card>
  </v-flex>
</template>

<script>
import gql from "graphql-tag";

export default {
  props: {
    rocket: {
      type: Object,
      required: true
    }
  }
};
</script>
