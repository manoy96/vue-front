<template>
    <v-container>
      <Header />
      <GQLrocketAll/>
      <GQLrocketCreate/>
      <GQLrocketUpdate/>
      <GQLrocketDelete/>
    </v-container>
</template>

<script>
import Header from "./components/Header";
import GQLrocketAll from "./components/GQLrocketAll";
import GQLrocketCreate from "./components/GQLrocketCreate";
import GQLrocketUpdate from "./components/GQLrocketUpdate";
import GQLrocketDelete from "./components/GQLrocketDelete";
export default {
  data() {
    return {
      error: "",
      myItem: {}
    };
  },
  components: {
    Header,
    GQLrocketAll,
    GQLrocketCreate,
    GQLrocketUpdate,
    GQLrocketDelete,
    
  },
  methods: {}
};
</script>

<style>
</style>