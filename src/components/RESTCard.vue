<template>
    <v-card flat tile style="padding-left:5px; padding-right: 5px;">
        <v-img :src="rocket.url" height="400px" class="white--text" style="text-align: center; text-shadow: 2px 2px 4px #000000;">
            <h3 class="headline mb-0">{{rocket.name}}</h3>
        </v-img>
        <v-card-title primary-title>
            <div >
                <h3 class="headline mb-0">{{rocket.name}}</h3>
                <ul>
                    <li>ID: {{rocket._id}}</li>
                    <li>Name: {{rocket.name}}</li>
                    <li>Country: {{rocket.country}}</li>
                    <li>Cost: {{rocket.cost}}</li>
                </ul>
            </div>
        </v-card-title>
    </v-card>
</template>

<script>
import axios from 'axios'
export default {
    data() {
        return {
            //
        }
    },
    props: {
        rocket: {
            type: Object,
            required: true
        }
    },
    created () {
        // axios
        // .get('https://floating-temple-55389.herokuapp.com/rockets/all')
        // .then((res) => {
        //     this.rockets = res.data
        // })
        // .catch(error => console.log(error))
    }
}
</script>

<style scoped>
    ul {
        list-style: none;
    }
</style>