<template>
  <v-container>
    <!--    <v-row align="center">-->
    <div class="my-font">
      <v-row class="text-center">
        <v-col class="my-background" cols="12">
          <div class="intro-text">LEIA PARIM RAAMATU HIND</div>
          <div class="text-field-wrapper">
            <v-text-field
                class="my-searchBlock"
                hide-details="auto"
                color="#cbf1f1"
                placeholder="Sisesta autor, raamatu pealkiri või ISBN number"
                solo
            ></v-text-field>
            <v-btn class="search-button white--text" color="#136581" v-on:click="search()">OTSI</v-btn>
          </div>
        </v-col>

        <v-col class="mb-5">
          <h1 class="display-2 font-weight-bold mb-5">
            LEIA PARIM RAAMATU HIND
          </h1>

          <p class="subheading font-weight-regular">
            For help and collaboration with other Vuetify developers,
            <br>please join our online
            <a
                href="https://community.vuetifyjs.com"
                target="_blank"
            >Discord Community</a>
          </p>
        </v-col>

        <v-col
            class="mb-5"
            cols="12"
        >
          <h2>
            What's next?
          </h2>

          <v-row justify="center">
            <a
                v-for="(next, i) in whatsNext"
                :key="i"
                :href="next.href"
                class="subheading mx-3"
                target="_blank"
            >
              {{ next.text }}
            </a>
          </v-row>
        </v-col>

        <v-col
            class="mb-5"
            cols="12"
        >

        </v-col>
      </v-row>
    </div>
    <!--    </v-row>-->
  </v-container>
</template>

<script>
export default {
  name: 'BookFind',

  data: () => ({

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

<style scoped>

</style>

