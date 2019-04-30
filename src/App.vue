<template>
  <div>
    <Header/>

    <v-tabs dark slider-color="red">
      <v-tab ripple>GQL Show All</v-tab>
      <v-tab ripple>GQL Create Rocket</v-tab>
      <v-tab ripple>GQL Update Rockdet</v-tab>
      <v-tab ripple>GQL Delete Rocket</v-tab>
      <v-tab ripple>REST Show All</v-tab>
      <v-tab ripple>REST Create Rocket</v-tab>
      <v-tab ripple>REST Delete Rocket</v-tab>
      <v-tab ripple>REST Update Rocket</v-tab>

      <v-tab-item>
        <v-card flat>
          <v-card-text>
            <display/>
          </v-card-text>
        </v-card>
      </v-tab-item>
      <v-tab-item>
        <v-card flat>
          <v-card-text>
            <GQLrocketCreate class="mt-5"/>
          </v-card-text>
        </v-card>
      </v-tab-item>
      <v-tab-item>
        <v-card flat>
          <v-card-text>
            <GQLrocketUpdate/>
          </v-card-text>
        </v-card>
      </v-tab-item>
      <v-tab-item>
        <v-card flat>
          <v-card-text>
            <GQLrocketDelete/>
          </v-card-text>
        </v-card>
      </v-tab-item>
      <v-tab-item>
        <v-card flat>
          <v-card-text>
            <RESTrocketAll/>
          </v-card-text>
        </v-card>
      </v-tab-item>
      <v-tab-item>
        <v-card flat>
          <v-card-text></v-card-text>
          <RESTrocketCreate/>
        </v-card>
      </v-tab-item>
      <v-tab-item>
        <v-card flat>
          <v-card-text></v-card-text>
          <RESTrocketUpdate/>
        </v-card>
      </v-tab-item>
      <v-tab-item>
        <v-card flat>
          <v-card-text></v-card-text>
          <RESTrocketDelete/>
        </v-card>
      </v-tab-item>
      
    </v-tabs>
  </div>
</template>

<script>
import Header from "./components/Header";
import display from "./components/display";
import GQLrocketAll from "./components/GQLrocketAll";
import GQLrocketCreate from "./components/GQLrocketCreate";
import GQLrocketUpdate from "./components/GQLrocketUpdate";
import GQLrocketDelete from "./components/GQLrocketDelete";

import RESTrocketAll from "./components/RESTrocketAll";
import RESTrocketCreate from "./components/RESTrocketCreate";
import RESTrocketDelete from "./components/RESTrocketDelete";

export default {
  data() {
    return {
      model: "tab-2",
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
    RESTrocketCreate,
    RESTrocketDelete
  },
  methods: {}
};
</script>

<style>
</style>