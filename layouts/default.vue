<template>
  <v-app dark>
    <v-navigation-drawer
      class="sidebar hidden-md-and-up"
      v-model="drawer"
      fixed
      app
    >
      <v-list class="pt-0">
        <v-list-item
          dark
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon color="#98A7BF">{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content class="white--text">
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <div class="top-menu pa-2 px-16 hidden-sm-and-down">
      <img src="../static/assets/phone.svg" class="ml-4 mr-4" alt="" />
      +234 802 501 8557
      <img src="../static/assets/location.svg" class="ml-10 mr-4" alt="" />
      35 Freedom Way, Lekki Phase 1, Lagos, Nigeria
      <img src="../static/assets/mail.svg" class="ml-10 mr-4" alt="" />
      sales@thelightinghaus.com
    </div>
    <v-app-bar class="navbar px-16 py-2 hidden-sm-and-down" flat>
      <nuxt-link to="/">
        <img src="../static/assets/logo.svg" alt="" />
      </nuxt-link>
      <v-spacer />
      <v-text-field
        placeholder="Search for a product, category or space."
        class="mt-9 hidden-sm-and-down"
        outlined
        prepend-inner-icon="search"
      ></v-text-field>
      <v-spacer></v-spacer>

      <v-card flat class="text-center menu-item mt-2" to="/">
        <img src="../static/assets/user.svg" alt="" /><br />
        My Account
      </v-card>
      <v-card flat class="text-center menu-item mx-10 mt-2" to="/">
        <img src="../static/assets/list.svg" alt="" /><br />
        list
      </v-card>
      <v-card flat class="text-center menu-item mt-2" to="/">
        <img src="../static/assets/cart.svg" alt="" /><br />
        cart
      </v-card>
    </v-app-bar>
    <v-app-bar flat class="px-16 white hidden-sm-and-down">
      <v-btn class="menu-item" text> LIGHTING EXPLORER </v-btn>
      <v-btn class="menu-item" text> OFFICE </v-btn>
      <v-btn class="menu-item" text> HOTEL </v-btn>
      <v-btn class="menu-item" text> HOME </v-btn>
      <v-btn class="menu-item" text> ALL PRODUCTS </v-btn>
      <v-btn class="menu-item" text> PENDANT LIGHT </v-btn>
      <v-btn class="menu-item" text> CHANDELIER </v-btn>
      <v-btn class="menu-item" text> SWITCHES & SOCKETS </v-btn>
      <v-btn class="menu-item" text> CEILING LAMP </v-btn>
      <v-btn class="menu-item" text> WALL LAMP </v-btn>
    </v-app-bar>
    <v-app-bar flat class="white hidden-md-and-up">
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-spacer></v-spacer>
      <nuxt-link to="/">
        <img src="../static/assets/logo.svg" alt="" />
      </nuxt-link>
      <v-spacer></v-spacer>
      <v-menu transition="slide-x-transition" bottom left>
        <template v-slot:activator="{ on, attrs }">
          <v-btn icon v-on="on" v-bind="attrs">
            <img src="../static/assets/cart.svg" alt="" />
          </v-btn>
        </template>

        <v-list style="width: 200px">
          <v-list-item v-for="(item, i) in userdropdown" :key="i">
            <v-list-item-action class="mx-0">
              <img :src="item.src" width="14px" alt />
            </v-list-item-action>
            <v-list-item-content class="primaryalt--text">
              <v-list-item-title class="menu">{{
                item.title
              }}</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list>
      </v-menu>
    </v-app-bar>
    <div class="search hidden-md-and-up">
      <v-text-field
        outlined
        prepend-inner-icon="search"
        placeholder="Search for a product, category or space."
        class="mx-3 mt-2"
      >
      </v-text-field>
    </div>
    <v-main>
      <v-responsive>
        <nuxt />
      </v-responsive>
    </v-main>
    <v-footer class="pa-0">
      <div class="footer-top py-5">
        <v-container>
          <v-layout px-4 row wrap>
            <v-flex md3 pr-8>
              <nuxt-link to="/">
                <img src="../static/assets/logo-white.svg" alt="" />
              </nuxt-link>
              <p class="about mt-4">
                //Talk about the company here// <br />Brighten your nights with
                modern designer lighting from Thelightinghaus.com Our range
                features top brands and all the latest contemporary lighting
                styles to illuminate your home and garden.
              </p>
            </v-flex>
            <v-flex md2 pt-6>
              <h5 class="title mb-6">Quick Links</h5>
              <nuxt-link to="#" class="about"> LIGHTING EXPLORER </nuxt-link
              ><br />
              <nuxt-link to="#" class="about"> OFFICE </nuxt-link><br />
              <nuxt-link to="#" class="about"> HOTEL </nuxt-link><br />
              <nuxt-link to="#" class="about"> HOME </nuxt-link><br />
              <nuxt-link to="#" class="about"> MY ACCOUNT </nuxt-link><br />
              <nuxt-link to="#" class="about"> CART </nuxt-link>
            </v-flex>
            <v-flex md3 pt-6>
              <h5 class="title mb-6">Connect</h5>
              <p class="about">Connect with us on social media</p>
              <v-btn icon small class="white--text">
                <v-icon small>fab fa-telegram</v-icon>
              </v-btn>
              <v-btn icon small class="white--text">
                <v-icon small>fab fa-whatsapp</v-icon>
              </v-btn>
              <v-btn icon small class="white--text">
                <v-icon small>fab fa-linkedin</v-icon>
              </v-btn>
              <v-btn icon small class="white--text">
                <v-icon small>fab fa-youtube</v-icon>
              </v-btn>
              <v-btn icon small class="white--text">
                <v-icon small>fab fa-twitter</v-icon>
              </v-btn>
              <v-btn icon small class="white--text">
                <v-icon small>fab fa-facebook-f</v-icon>
              </v-btn>
              <v-btn icon small class="white--text">
                <v-icon small>fab fa-instagram</v-icon>
              </v-btn>
            </v-flex>
            <v-flex md4>
              <v-row>
                <v-col cols="1">
                  <img src="../static/assets/logo-alt.svg" alt="" />
                </v-col>
                <v-col class="pl-8">
                  <h5 class="title">Download our mobile app</h5>
                  <p class="about">Get access to exclusive offers</p>
                </v-col>
              </v-row>
              <img src="../static/assets/apple.svg" width="100px" alt="" />
              <img src="../static/assets/android.svg" width="100" alt="" />
            </v-flex>
          </v-layout>
        </v-container>
      </div>
      <div class="top-menu hidden-sm-and-down">
        <v-container pa-2>
          <img src="../static/assets/phone.svg" class="mr-4" alt="" />
          +234 802 501 8557
          <img src="../static/assets/location.svg" class="ml-10 mr-4" alt="" />
          35 Freedom Way, Lekki Phase 1, Lagos, Nigeria
          <img src="../static/assets/mail.svg" class="ml-10 mr-4" alt="" />
          sales@thelightinghaus.com
        </v-container>
      </div>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      drawer: false,

      items: [
        {
          icon: 'wb_sunny',
          title: 'LIGHTING EXPLORER',
          to: '#lighting',
        },
        {
          icon: 'apartment',
          title: 'OFFICE',
          to: '#office',
        },
        {
          icon: 'hotel',
          title: 'HOTEL',
          to: '#hotel',
        },
        {
          icon: 'home',
          title: 'HOME',
          to: '#home',
        },
        {
          icon: 'group_work',
          title: 'ALL PRODUCTS',
          to: '#products',
        },
        {
          icon: 'highlight',
          title: 'PENDANT LIGHT',
          to: '#pendant',
        },
        {
          icon: 'mdi-cog',
          title: 'CHANDELIER',
          to: '#chandelier',
        },
        {
          icon: 'toggle_on',
          title: 'SWITCHES & SOCKETS',
          to: '#switch',
        },
        {
          icon: 'mdi-cog',
          title: 'CEILING LAMP',
          to: '#celing',
        },
        {
          icon: 'mdi-cog',
          title: 'WALL LAMP',
          to: '#wall',
        },
      ],
      userdropdown: [
        {
          title: 'My Account',
          to: '',
          src: require('../static/assets/user.svg'),
        },
        {
          title: 'List',
          to: '',
          src: require('../static/assets/list.svg'),
        },
        {
          title: 'Cart',
          to: '/',
          src: require('../static/assets/cart.svg'),
        },
      ],
    }
  },
}
</script>
<style lang="scss" scoped>
.menu-item {
  font-family: Poppins;
  font-style: normal;
  font-weight: 600;
  font-size: 12px !important;
  line-height: 18px;

  align-items: center;
  text-align: center;
  text-transform: uppercase;

  /* Gray 2 */

  color: #4f4f4f !important;
  &:hover{
    color: #F4811F !important;
  }
}
.navbar {
  background: #ffffff 0% 0% no-repeat padding-box !important;
  border-bottom: 1px solid #828282 !important;
  height: 85px !important;
  // opacity: 1;
}
.top-menu {
  background: #000;
  width: 100%;
  font-family: Poppins;
  font-style: normal;
  font-weight: normal;
  font-size: 14px;
  line-height: 21px;

  color: #ffffff;
}
.sidebar {
  background: #111 !important;
}
.logo-box {
  background: #0000001a 0% 0% no-repeat padding-box;
  box-shadow: 0px 2px 3px #0000000d;
  opacity: 1;
  height: 70px;
}
.logo {
  text-align: left;
  font: normal normal bold 15px/21px Source Sans Pro;
  letter-spacing: 3px;
  color: #ffffff;
  opacity: 1;
}
.footer-top {
  background: #333;
  width: 100%;
  .about {
    font-family: Poppins !important;
    font-style: normal;
    font-weight: normal;
    font-size: 12px;
    line-height: 18px;

    color: #ffffff;
  }
  .title {
    font-family: Poppins !important;
    font-style: normal;
    font-weight: 600;
    font-size: 14px;
    line-height: 21px;

    color: #ffffff;
  }
}
a {
  text-decoration: none;
  &:hover {
    color: #f4811f !important;
  }
}
</style>
