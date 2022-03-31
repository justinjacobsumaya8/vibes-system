<template>
  
  <div class="p-m-4">
   <v-app-bar
      flat
      absolute
      color="transparent"
    >
      <div class="boxed-container w-full">
        <div class="d-flex align-center mx-6">
          <!-- Left Content -->
          <v-app-bar-nav-icon
            class="d-block d-lg-none me-2"
            @click="isDrawerOpen = !isDrawerOpen"
          ></v-app-bar-nav-icon>
          
          <div class="vertical-nav-header d-flex items-center ps-6 pe-5 pt-5 pb-2">
            <router-link to="/" class="d-flex align-center text-decoration-none">
              <v-img
                :src="require('@/assets/images/logos/logo.svg').default"
                max-height="30px"
                max-width="30px"
                alt="logo"
                contain
                eager
                class="app-logo me-3"
              ></v-img>
              <v-slide-x-transition>
                <h2 class="app-title text--primary">ViBes POS</h2>
              </v-slide-x-transition>
            </router-link>
          </div>
          <v-spacer></v-spacer>

          <!-- Right Content -->
          <a
            href="/"
            target="_blank"
            rel="nofollow"
          >
            <v-icon class="ms-6 me-4">
              {{ icons.mdiHomeOutline }}
            </v-icon>
          </a>
          <theme-switcher></theme-switcher>
          <v-btn
            icon
            small
            class="ms-3"
          >
            <v-icon>
              {{ icons.mdiBellOutline }}
            </v-icon>
          </v-btn>
          <app-bar-user-menu></app-bar-user-menu>
        </div>
      </div>
    </v-app-bar>
    
    <div class="inner">
      <v-row>
        <v-col cols="12" md="8" sm="12">
          <booking-payment></booking-payment>
        </v-col>
        <v-col cols="12" md="4" sm="12">
          <booking-summary></booking-summary>
        </v-col>
      </v-row>
    </div>
  </div>
</template>

<script>
import { mdiMagnify, mdiBellOutline, mdiHomeOutline } from '@mdi/js'
import ThemeSwitcher from '../../layouts/components/ThemeSwitcher.vue'
import AppBarUserMenu from '../../layouts/components/AppBarUserMenu.vue'
import BookingPayment from './components/BookingPayment.vue'
import BookingSummary from './components/BookingSummary.vue'

export default {
  components: {
    BookingPayment,
    AppBarUserMenu,
    ThemeSwitcher,
    BookingSummary,
  },
  setup() {
    return {
      // Icons
      icons: {
        mdiMagnify,
        mdiBellOutline,
        mdiHomeOutline
      },
    }
  },
}
</script>

<style lang="scss" scoped>
.inner {
  padding: 6em 3em;
}

.p-m-4 {
  padding: 8px;
  margin: 8px;
}
main {
  padding:0;
}
</style>
