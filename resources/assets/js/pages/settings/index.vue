<template>
  <div class="row">
    <div class="col-md-3">
      <card :title="$t('settings')" class="settings-card">
        <ul class="nav flex-column nav-pills">
          <li v-for="tab in tabs" class="nav-item">
            <router-link :to="{ name: tab.route }" class="nav-link" active-class="active">
              <!-- <fa :icon="tab.icon" fixed-width/> -->
              <i :class="tab.icon" aria-hidden="true"></i>
              {{ tab.name }}
            </router-link>
          </li>
        </ul>
      </card>
    </div>

    <div class="col-md-9">
      <transition name="fade" mode="out-in">
        <router-view/>
      </transition>
    </div>
  </div>
</template>

<script>
export default {
  middleware: 'auth',

  computed: {
    tabs () {
      return [
        {
          icon: 'fa fa-user',
          name: this.$t('profile'),
          route: 'settings.profile'
        },
        {
          icon: 'fa fa-language',
          name: this.$t('language'),
          route: 'settings.language'
        },
        {
          icon: 'fa fa-lock',
          name: this.$t('password'),
          route: 'settings.password'
        }
      ]
    }
  }
}
</script>

<style>
.settings-card .card-body {
  padding: 0;
}
</style>
