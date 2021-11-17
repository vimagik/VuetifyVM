<template>
  <v-app-bar app color="primary" dark>
    <v-toolbar-title>Vuetify dushboard</v-toolbar-title>
    <v-spacer />
    <v-btn v-for="link in links" :key="link.name" text rounded :to="link.page">
      {{ link.name }}
    </v-btn>
  </v-app-bar>
</template>

<script>
export default {
  name: 'MyBarr',
  props: {
    links: {
      type: Array,
      required: true
    }
  }
}
</script>
