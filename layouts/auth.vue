<template>
  <v-app>
    <v-main>
      <div fluid fill-height>
        <v-layout row wrap justify-center align-center>
          <v-flex md6>
            <div class="bg"></div>
          </v-flex>
          <v-flex md6>
            <nuxt />
          </v-flex>
        </v-layout>
      </div>
    </v-main>
  </v-app>
</template>
<style lang="scss" scoped>
.bg {
  width: 100%;
  height: 100vh;
  background-image: url('../static/assets/bg.png') !important;
  // background-position: top left;
  background-size: cover;
}
</style>
