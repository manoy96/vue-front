<template>
  <div class="header">
    <v-toolbar my-5 color="blue-grey darken-2" app>
      <v-layout justify-start align-center class="pa-2 my-2">
        <v-toolbar-title class="font-weight-regular display-2 white--text">Rockets</v-toolbar-title>
      </v-layout>

      <!-- <div id="nav">
        <router-link to="/">Home</router-link> |
        <router-link to="/rest">REST</router-link> |
        <router-link to="/graphql">GraphQL</router-link> -->
      <!-- </div> -->
    </v-toolbar>
  </div>
</template>

<script>
export default {
    name: 'Header'
};
</script>

<style scoped>
    p {
        color: #fff;
    }
</style>

