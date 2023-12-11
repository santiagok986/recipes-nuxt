<template>
  <v-container>
    <v-row>
      <v-col cols="3" v-for="category in categories" :key="category.id">
        <app-ui-nav-card :category="category"></app-ui-nav-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
//import { categorias } from '../graphql/querys'

export default {
  middleware:"initData",
  data() {
    return {
     // categories: [],
      // query: categorias,
    };
  },
  computed:{
    categories(){
      return this.$store.getters.readCategories
    }
  }
  // async fetch() {
  //   //const client = this.$apollo.getClient();
  //   const query = {
  //     query: require("../graphql/categories.gql"),
  //   };

  //   await this.$apollo.query(query).then((data) => {
  //     console.log(data);
  //     this.categories = data.data.categories;
  //   });
  // },
  // async asyncData(context) {
  //   const client = context.app.apolloProvider.defaultClient

  //   const query = {
  //     query:require("../graphql/categories.gql")
  //   }

  //   let categories = []
  //   await client.query(query).then(data => {
  //     console.log(data)
  //     categories = data.data.categories
  //   })

  //   return {categories}
  // },
  // apollo:{
  //   cat:{
  //     query:categorias,
  //     update: data => data.categories
  //   }
  // }
};
</script>
