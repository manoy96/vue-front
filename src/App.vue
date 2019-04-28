<template>
  <div>
    <rocketAll />
    <rocketCreate />
    <rocketUpdate />
    <rocketDelete />
    <rocketRestAll />
  </div>
</template>

<script>
import rocketAll from "./components/rocketAll";
import rocketCreate from "./components/rocketCreate";
import rocketUpdate from "./components/rocketUpdate";
import rocketDelete from "./components/rocketDelete";
import rocketRestAll from "./components/rocketRestAll";

export default {
  data() {
    return {
      error: "",
      myItem: {}
    };
  },
  components: {
    rocketAll,
    rocketCreate,
    rocketUpdate,
    rocketDelete,
    rocketRestAll,
  },
  methods: {
  }
};
</script>

<style>
</style>