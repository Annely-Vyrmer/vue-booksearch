<template>
  <v-app>
    <v-app-bar
      app
      color="#cbf1f1"
      flat
    >
      <div class="d-flex align-center">
<!--        <v-img-->
<!--          alt="Vuetify Logo"-->
<!--          class="shrink mr-2"-->
<!--          contain-->
<!--          src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"-->
<!--          transition="scale-transition"-->
<!--          width="40"-->
<!--        />-->
<!--        <v-img-->
<!--          alt="Vuetify Name"-->
<!--          class="shrink mt-1 hidden-sm-and-down"-->
<!--          contain-->
<!--          min-width="100"-->
<!--          src="https://cdn.vuetifyjs.com/images/logos/vuetify-name-dark.png"-->
<!--          width="100"-->
<!--        />-->
        <span class="my-font">BOOK FIND</span>
<!--        <router-link to="/">Book Find </router-link>-->
<!--        <router-link to="/about"> About</router-link>-->
      </div>

      <v-spacer></v-spacer>

      <v-btn
          href="https://www.apollo.ee/"
          target="_blank"
          text
      >
        <span class="mr-2">Apollo</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>

      <v-btn
          href="https://www.kriso.ee/"
          target="_blank"
          text
      >
        <span class="mr-2">Krisostomus</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>

      <v-btn
        href="https://www.rahvaraamat.ee/et"
        target="_blank"
        text
      >
        <span class="mr-2">Rahva Raamat</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
    </v-app-bar>

    <v-main>
      <router-view/>
    </v-main>
  </v-app>
</template>

<script>

export default {
  name: 'App',

  data: () => ({
    //
  }),
};
</script>
