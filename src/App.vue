<template>
<v-app>
  
</v-app>

  <!-- <div id="app">
      <main-header></main-header>

  <main class="App__main">
    <transition
      name="fade"
      mode="out-in"
    >
      <router-view/>
    </transition>
  </main>

    <p v-if="['home','about'].includes($route.name)" class="myUser">Hello, {{ userName }}</p>
    <app-user v-if="['about'].includes($route.name)"></app-user>
    <main-footer></main-footer>
  </div> -->
</template>

  <!-- <v-app>
    <v-toolbar app>
      <v-toolbar-title class="headline text-uppercase">
        <span>Vuetify</span>
        <span class="font-weight-light">MATERIAL DESIGN</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn
        flat
        href="https://github.com/vuetifyjs/vuetify/releases/latest"
        target="_blank"
      >
        <span class="mr-2">Latest Release</span>
      </v-btn>
    </v-toolbar>

    <v-content>
      <HelloWorld/>
    </v-content>
  </v-app> -->

<script>
import HelloWorld from './components/HelloWorld'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data () {
    return {
      //
    }
  }
}
</script>
