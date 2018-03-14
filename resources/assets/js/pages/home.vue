<template>
  <card :title="$t('home')">
    {{ $t('you_are_logged_in') }}

  </card>
</template>

<script>

export default {

  middleware: 'auth',

  data(){
    return{
    }
  },

  metaInfo () {
    return { title: this.$t('home') }
  },

  created(){
      axios.get('/api/user').then(({ data }) => {
          console.log(data)
      })
  }

}
</script>
