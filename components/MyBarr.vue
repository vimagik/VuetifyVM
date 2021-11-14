<template>
  <v-app-bar app color="primary" dark>
    <v-toolbar-title>Vuetify dushboard</v-toolbar-title>
    <v-spacer/>
    <v-btn text rounded to="/">
      Home
    </v-btn>
    <v-btn text rounded :to="{name: 'login'}">
      Login
    </v-btn>
    <v-btn text rounded :to="{name: 'dashboard'}">
      Dashboard
    </v-btn>
  </v-app-bar>
</template>

<script>
export default {
  name: 'MyBarr'
}
</script>
