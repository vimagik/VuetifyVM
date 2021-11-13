<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <v-toolbar-title>Vuetify dushboard</v-toolbar-title>
      <v-spacer />
      <v-btn text rounded>
        Home
      </v-btn>
      <v-btn text rounded>
        Login
      </v-btn>
    </v-app-bar>
    <v-main>
      <nuxt />
    </v-main>
    <my-footer />
  </v-app>
</template>

<script>
import MyFooter from '~/components/MyFooter'

export default {
  components: {
    MyFooter
  },
  data () {
    return {}
  }
}
</script>
