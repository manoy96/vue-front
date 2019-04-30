<template>
    <!-- <div>
    <v-tabs
      v-model="active"
      color="cyan"
      dark
      slider-color="yellow"
    >
      <v-tab
        v-for="n in 3"
        :key="n"
        ripple
      >
        Item {{ n }}

      </v-tab>
      <v-tab-item
        v-for="n in 3"
        :key="n"
      >
        <v-card flat>
          <v-card-text>{{ text }}</v-card-text>
        </v-card>
      </v-tab-item>
    </v-tabs>

    <div class="text-xs-center mt-3">
      <v-btn @click="next">next tab</v-btn>
    </div>
  </div> -->

    <v-container>
      <Header />
      <GQLrocketAll/>
      <GQLrocketCreate/>
      <GQLrocketUpdate/>
      <GQLrocketDelete/>
      <display />

      <RESTrocketAll />
    </v-container>
</template>

<script>
import Header from "./components/Header";
import display from "./components/display";
import GQLrocketAll from "./components/GQLrocketAll";
import GQLrocketCreate from "./components/GQLrocketCreate";
import GQLrocketUpdate from "./components/GQLrocketUpdate";
import GQLrocketDelete from "./components/GQLrocketDelete";

import RESTrocketAll from "./components/RESTrocketAll";
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
    display,

    RESTrocketAll,
    
  },
  methods: {}
};
</script>

<style>
</style>