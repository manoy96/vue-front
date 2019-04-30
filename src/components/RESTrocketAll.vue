<template>
    <v-container>
        <v-layout row wrap>

            <v-flex
              v-for="rocket in rockets"
              :key="rocket._id"
              xs4>
                <RESTCard :rocket="rocket" width="200px" height="200px"/>
            </v-flex>
        </v-layout>
    </v-container>
</template>

<script>
import axios from 'axios'
import RESTCard from './RESTCard.vue'
export default {
    name: "RESTdisplay",
    components: {
        RESTCard
    },
    data() {
        return {
            rockets: []
        }
    },
    created() {
        axios
        .get('https://sleepy-taiga-70117.herokuapp.com/products/all')
        .then((res) => {
            console.log(res);
            this.rockets = res.data
        })
        .catch(error => console.log(error))
    }
}
</script>

<style scoped>
</style>