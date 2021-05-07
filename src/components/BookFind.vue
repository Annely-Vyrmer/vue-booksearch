<template>
  <v-container>
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
            <v-btn class="search-button white--text" v-on:click="search()">OTSI</v-btn>
          </div>
        </v-col>
<!--        <p v-if="booksData.length==0" >"Raamatuid ei leitud"</p>-->
<!--        {{booksdata}}-->
<!--        <p v-if="errorMessage" >{{errorMessage}}</p>-->
<!--        {{booksdata}}-->

        <v-col cols="12">
          <div class="headline1">LEITUD RAAMATUD</div>
          <div class="regular-text"> Siia tuleb errorMessage kui ühtegi raamatut ei leitud</div>
        </v-col>

        <v-card
            class="mx-auto"
            color="#cbf1f1"
            max-width="300"
            tiled
        >
          <v-list-item three-line>
            <v-list-item-avatar
                tile
                size="160"
                color="grey"
            ></v-list-item-avatar>
          </v-list-item>
          <v-list-item-content>
              <v-list-item-title class="book-headline">Raamatu pealkiri</v-list-item-title>
              <v-list-item-title class="book-headline">Autor</v-list-item-title>
          </v-list-item-content>
            <v-list-item-content>
              <v-list-item-subtitle class="book-regular-text">Ribakood: </v-list-item-subtitle>
              <v-list-item-subtitle class="book-regular-text">Ilmumisaasta: </v-list-item-subtitle>
              <v-list-item-subtitle class="book-regular-text">Kirjastus: </v-list-item-subtitle>
              <v-list-item-subtitle class="book-regular-text">Lehekülgi: </v-list-item-subtitle>
              <v-list-item-subtitle class="book-regular-text">Formaat: </v-list-item-subtitle>
              <v-list-item-subtitle class="book-regular-text">E-pood: </v-list-item-subtitle>
            </v-list-item-content>

          <v-card-actions>
            <v-list-item-content>
              <v-list-item-title class="book-price">HIND</v-list-item-title>
            </v-list-item-content>
            <v-spacer></v-spacer>
            <v-btn class="search-button white--text" color="#136581" v-on:click="search()">Mine ostma</v-btn>
          </v-card-actions>
        </v-card>

<!--        <v-col-->
<!--            class="mb-5"-->
<!--            cols="12"-->
<!--        >-->
<!--          <h2>-->
<!--            What's next?-->
<!--          </h2>-->

<!--          <v-row justify="center">-->
<!--            <a-->
<!--                v-for="(next, i) in whatsNext"-->
<!--                :key="i"-->
<!--                :href="next.href"-->
<!--                class="subheading mx-3"-->
<!--                target="_blank"-->
<!--            >-->
<!--              {{ next.text }}-->
<!--            </a>-->
<!--          </v-row>-->
<!--        </v-col>-->

        <v-col
            class="mb-15"
            cols="12"
        >
        </v-col>
      </v-row>
    </div>
  </v-container>
</template>

<script>
export default {
  name: 'BookFind',

  data: () => ({

    // whatsNext: [
    //   {
    //     text: 'Explore components',
    //     href: 'https://vuetifyjs.com/components/api-explorer',
    //   },
    //   {
    //     text: 'Select a layout',
    //     href: 'https://vuetifyjs.com/getting-started/pre-made-layouts',
    //   },
    //   {
    //     text: 'Frequently Asked Questions',
    //     href: 'https://vuetifyjs.com/getting-started/frequently-asked-questions',
    //   },
    // ],
  }),
}
</script>

<style scoped>

</style>

