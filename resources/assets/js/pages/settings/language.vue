<template>
  <card :title="$t('edit_language')">

      <ul class="navbar-nav">
          <locale-dropdown/>
          <!-- <li class="nav-item">
          <a class="nav-link" href="#">Link</a>
        </li> -->
      </ul>

  </card>
</template>

<script>

import Form from 'vform'
import LocaleDropdown from '../../components/LocaleDropdown'

export default {

  scrollToTop: false,

  components: {
    LocaleDropdown
  },

  metaInfo () {
    return { title: this.$t('settings') }
  },

  data: () => ({
    // form: new Form({
    //   password: '',
    //   password_confirmation: ''
    // })
  }),

  methods: {
    // async update () {
    //   await this.form.patch('/api/settings/password')
    //
    //   this.form.reset()
    // }
  }
}
</script>
