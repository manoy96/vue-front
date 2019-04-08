<template>
  <v-app>
     <main-header></main-header>
    <!-- <v-toolbar app>
      <v-toolbar-title class="headline text-uppercase">
        <span>Server</span>
        <span class="font-weight-light">Practice</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
    </v-toolbar> -->

    <v-content>
      <HelloWorld/>
    </v-content>
  </v-app>
</template>

<script>
import Header from './components/Header.vue'
import HelloWorld from './components/HelloWorld'


export default {
  name: 'App',
  components: {
    HelloWorld, 
    'main-header': Header,
  },
  data () {
    return {
      //
    }
  }
}
</script>
