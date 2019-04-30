<template>
    <v-container>
        <h2>ALL Rockets</h2>
        <v-layout row wrap>
            <v-flex
              v-for="rocket in rockets"
              :key="rocket.name"
              xs4
            >
                <rocketCard :rocket="rocket" width="200px" height="200px"/>
            </v-flex>
        </v-layout>
    </v-container>
</template>

<script>
import gql from 'graphql-tag'
import rocketCard from './rocketCard.vue'
    export default {
        name: "display",
        components: {
            rocketCard
        },
        data() {
            return {
                info: "",
                rockets: []
            }
        },
        mounted() {
            // 
        },
        apollo: {
            rockets: gql`
            query{
                rockets {
                    id
                    name
                    country
                    cost
                    payloadLeo
                    payloadGto
                    kgLeo
                    kgGto
                    url
                }
            }`
        }
    }
</script>

<style>
</style>