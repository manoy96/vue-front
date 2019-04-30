<template>
      <div class="about">
        <v-container>
          <v-card class="pa-3" dark>
            <h1>Update An rocket from REST</h1>
            <v-layout row wrap>
            <v-flex xs6>
              <v-text-field v-model="id" label="ID" required></v-text-field>
            </v-flex>
            <v-flex xs6>
              <v-text-field v-model="price" label="price" required></v-text-field>
            </v-flex>
            </v-layout>
            <v-btn @click="updaterocket" color="info">Update</v-btn>
            <!-- {{error}}
            {{returnedItem}} -->
          </v-card>
        </v-container>
  </div>
</template>

<script>
import axios from 'axios'
export default {
    data() {
        return {
            id: this.$route.params.id,
            price: this.price,
            rocket: {
            }
        }
    },
    created() {
        axios
        .get('https://sleepy-taiga-70117.herokuapp.com/products/all')
        .then((res) => {
            this.rocket = res.data
            })
            .catch((error) => {
                console.log(error)
            })
    },
    props: {},
    methods: {
        updaterocket() {
            const rocketData = {
                id: this.id,
                price: this.price
            }
            console.log(rocketData)
            axios
            .put('https://sleepy-taiga-70117.herokuapp.com/products/' + this.id + '/update', rocketData)
            .then((res) => {
                console.log('rocket Updated')
                this.$router.push('/')
            })
            .catch((error) => {
                console.log(error)
            })
        }
    }
}
</script>

<style scoped>
</style>