<template>
    <v-card>
    <v-card-title primary-title>
      <div>
        <h3 class="headline mb-0">{{ rocket.name.charAt(0).toUpperCase()}}</h3>
        <ul>
            <li>{{ rocket.country }}</li>
        </ul>
      </div>
    </v-card-title>
  </v-card>
    
</template>

<script>
import gql from "graphql-tag";

export default {
    props: {
        rocket: {
        type: Object,
        required: true
        }
  },
//   apollo: {
//       rocket: gql `query {
//           rocket {
//               id
//               name
//               country
//           }

//       }`
//   }

    
}
</script>
