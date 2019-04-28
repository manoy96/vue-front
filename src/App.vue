<template>
  <div>
    <v-container justify-center align-center>
      <GQLrocketAll/>
      <GQLrocketCreate/>
      <GQLrocketUpdate/>
      <GQLrocketDelete/>
      <!-- <rocketRestAll/> -->
    </v-container>
  </div>
</template>

<script>
import GQLrocketAll from "./components/GQLrocketAll";
import GQLrocketCreate from "./components/GQLrocketCreate";
import GQLrocketUpdate from "./components/GQLrocketUpdate";
import GQLrocketDelete from "./components/GQLrocketDelete";
// import rocketRestAll from "./components/rocketRestAll";

export default {
  data() {
    return {
      error: "",
      myItem: {}
    };
  },
  components: {
    GQLrocketAll,
    GQLrocketCreate,
    GQLrocketUpdate,
    GQLrocketDelete,
    // rocketRestAll
  },
  methods: {}
};
</script>

<style>
</style>