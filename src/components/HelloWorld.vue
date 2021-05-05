<template>
  <v-container>
    <v-row class="text-center">
      <v-col cols="12">
<!--        <v-img-->
<!--            :src="require('../assets/logo.svg')"-->
<!--            class="my-3"-->
<!--            contain-->
<!--            height="200"-->
<!--        />-->
        <!-- pildi test panen assets kausta - alla sektsiooni style tag ja sinna määrata properties-->
        <v-img :src="require('@/assets/seaView.jpg')"
               class="minu-pilt"
        />

      </v-col>

      <v-col class="mb-4">
        <h1 class="display-2 font-weight-bold mb-3">
          Welcome to Book Search
        </h1>

        <p class="subheading font-weight-regular">
          To find the cheapest version of a book,
          <br>please enter search parameter#s
          <a
              href="https://community.vuetifyjs.com"
              target="_blank"
          >Siia tuleb sisendi lahter näiteks</a>
        </p>
      </v-col>

<!--      <v-col-->
<!--          class="mb-5"-->
<!--          cols="12"-->
<!--      >-->
<!--        <h2 class="headline font-weight-bold mb-3">-->
<!--          What's next?-->
<!--        </h2>-->

<!--        <v-row justify="center">-->
<!--          <a-->
<!--              v-for="(next, i) in whatsNext"-->
<!--              :key="i"-->
<!--              :href="next.href"-->
<!--              class="subheading mx-3"-->
<!--              target="_blank"-->
<!--          >-->
<!--            {{ next.text }}-->
<!--          </a>-->
<!--        </v-row>-->
<!--      </v-col>-->

<!--      <v-col-->
<!--          class="mb-5"-->
<!--          cols="12"-->
<!--      >-->
<!--        <h2 class="headline font-weight-bold mb-3">-->
<!--          Important Links-->
<!--        </h2>-->

<!--        <v-row justify="center">-->
<!--          <a-->
<!--              v-for="(link, i) in importantLinks"-->
<!--              :key="i"-->
<!--              :href="link.href"-->
<!--              class="subheading mx-3"-->
<!--              target="_blank"-->
<!--          >-->
<!--            {{ link.text }}-->
<!--          </a>-->
<!--        </v-row>-->
<!--      </v-col>-->

<!--      <v-col-->
<!--          class="mb-5"-->
<!--          cols="12"-->
<!--      >-->
<!--        <h2 class="headline font-weight-bold mb-3">-->
<!--          Ecosystem-->
<!--        </h2>-->

<!--        <v-row justify="center">-->
<!--          <a-->
<!--              v-for="(eco, i) in ecosystem"-->
<!--              :key="i"-->
<!--              :href="eco.href"-->
<!--              class="subheading mx-3"-->
<!--              target="_blank"-->
<!--          >-->
<!--            {{ eco.text }}-->
<!--          </a>-->
<!--        </v-row>-->
<!--      </v-col>-->
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: 'HelloWorld',

  data: () => ({
    ecosystem: [
      {
        text: 'vuetify-loader',
        href: 'https://github.com/vuetifyjs/vuetify-loader',
      },
      {
        text: 'github',
        href: 'https://github.com/vuetifyjs/vuetify',
      },
      {
        text: 'awesome-vuetify',
        href: 'https://github.com/vuetifyjs/awesome-vuetify',
      },
    ],
    importantLinks: [
      {
        text: 'Documentation',
        href: 'https://vuetifyjs.com',
      },
      {
        text: 'Chat',
        href: 'https://community.vuetifyjs.com',
      },
      {
        text: 'Made with Vuetify',
        href: 'https://madewithvuejs.com/vuetify',
      },
      {
        text: 'Twitter',
        href: 'https://twitter.com/vuetifyjs',
      },
      {
        text: 'Articles',
        href: 'https://medium.com/vuetify',
      },
    ],
    whatsNext: [
      {
        text: 'Explore components',
        href: 'https://vuetifyjs.com/components/api-explorer',
      },
      {
        text: 'Select a layout',
        href: 'https://vuetifyjs.com/getting-started/pre-made-layouts',
      },
      {
        text: 'Frequently Asked Questions',
        href: 'https://vuetifyjs.com/getting-started/frequently-asked-questions',
      },
    ],
  }),
}
</script>

<style>
.minu-pilt {
  width: 100%;
  alignment: center;
}
</style>