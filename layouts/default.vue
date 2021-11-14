<template>
  <v-app>
    <my-barr />
    <v-main>
      <nuxt />
    </v-main>
    <my-footer />
  </v-app>
</template>

<script>
import MyFooter from '~/components/MyFooter'
import MyBarr from '@/components/MyBarr'

export default {
  components: {
    MyBarr,
    MyFooter
  },
}
</script>
