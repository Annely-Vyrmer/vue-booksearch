<template>
  <v-app>
    <v-app-bar
      app
      color="#cbf1f1"
      flat
    >
      <div class="d-flex align-center">
        <span class="my-font">LEIA RAAMAT</span>
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
        href="https://www.raamatukoi.ee/"
        target="_blank"
        text
      >
        <span class="mr-2">Raamatukoi</span>
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
