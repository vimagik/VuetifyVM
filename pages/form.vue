<template>
  <v-container>
    <v-row>
      <v-col>
        <h1>Форма</h1>
        <v-form ref="signUpForm" v-model="formValidity">
          <v-row>
            <v-col cols="6">
              <v-text-field v-model="email" label="E-mail" type="email" :rules="emailRules" />
            </v-col>
            <v-col cols="6">
              <v-autocomplete v-model="browser" label="Какой браузер вы используете" :items="browserTypes" />
            </v-col>
          </v-row>
          <v-file-input v-model="avatar" label="Загрузите фотографию для аватарки" />
          <v-menu
            v-model="menu2"
            :close-on-content-click="false"
            :nudge-right="40"
            transition="scale-transition"
            offset-y
            min-width="auto"
          >
            <template #activator="{ on, attrs }">
              <v-text-field
                v-model="date"
                label="День рождения"
                prepend-icon="mdi-calendar"
                readonly
                v-bind="attrs"
                v-on="on"
              />
            </template>
            <v-date-picker
              v-model="date"
              @input="menu2 = false"
            />
          </v-menu>
          <v-checkbox v-model="agreeToTerms" label="Присоединяюсь к правилам платформы" :rules="agreeToTermsRules" required />
          <v-btn type="submit" color="primary" class="mr-4" :disabled="!formValidity">
            Отрпавить
          </v-btn>
          <v-btn color="warning" class="mr-4" @click="resetValidation">
            Сбросить проверку
          </v-btn>
          <v-btn color="error" @click="resetForm">
            Перезагрузить
          </v-btn>
        </v-form>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: 'Form',
  data () {
    return {
      email: '',
      browser: '',
      browserTypes: [
        'Mozilla',
        'Chrome',
        'IE',
        'Brave'
      ],
      avatar: null,
      date: (new Date(Date.now() - (new Date()).getTimezoneOffset() * 60000)).toISOString().substr(0, 10),
      menu2: false,
      agreeToTerms: null,
      agreeToTermsRules: [
        value => !!value || 'Нужно в обязательном порядке согласиться с правилами'
      ],
      emailRules: [
        value => value.indexOf('@') !== 0 || 'Email should have a username.',
        value => value.includes('@') || 'Email should include an @ symbol.',
        value =>
          value.indexOf('.') - value.indexOf('@') > 1 ||
        'Email should contain a valid domain.',
        value => value.includes('.') || 'Email should include a period symbol.',
        value =>
          value.indexOf('.') <= value.length - 3 ||
        'Email should contain a valid domain extension.'
      ],
      formValidity: false
    }
  },
  methods: {
    resetForm () {
      this.$refs.signUpForm.reset()
    },
    resetValidation () {
      this.$refs.signUpForm.resetValidation()
    }
  }
}
</script>

<style scoped>

</style>
