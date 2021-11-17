<template>
  <v-app>
    <my-barr :links="links" />
    <v-main>
      <nuxt />
    </v-main>
    <my-footer :links="links" />
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
  data () {
    return {
      links: [
        { name: 'Home', page: '/' },
        { name: 'Login', page: { name: 'login' } },
        { name: 'Dashboard', page: { name: 'dashboard' } },
        { name: 'Form', page: { name: 'form' } }
      ]
    }
  }
}
</script>
