<template>
  <div class="about">
        <v-container xs12 md6 lg6>
             <h2>Delete a item</h2>
          <v-flex xs12>
            <v-text-field v-model="item.id" label="id" required></v-text-field>
          </v-flex>
      <v-btn color="error" @click="submitDelete()" dark>Delete</v-btn>
            {{ error }}
            {{ returneditem }}
        </v-container>
  </div>
</template>

<script>
import gql from "graphql-tag";
export default {
  data: () => ({
    error: "",
    item: {
        id: ""
    },
    returneditem: null
  }),
  methods: {
    submitDelete: function() {
      console.log(this.item);
      this.$apollo.mutate({
          mutation: gql`
                mutation removeRocket(
                    $id: ID
                ) {
                     deleteRocket (where: {
                     id: $id 
                     })
                    {
                        id
                    }
                 }
          `,
          variables: {
            id: this.item.id,
          }
        })
        .then(res => {
          this.returneditem = res.data;
        })
        .catch(err => {
          this.error = err;
        });
    }
  }
};
</script>