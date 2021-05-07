<template>
  <v-container>
    <div class="my-font">
      <v-row class="text-center">
        <v-col class="my-background" cols="12">
          <div class="intro-text">LEIA PARIM RAAMATU HIND</div>
          <div class="text-field-wrapper">

<!--            <input v-model="searchInput" placeholder="enter key-word">-->
<!--            <button v-on:click="getBookData()"> Search</button>-->
<!--            <p v-if="errorMessage" >{{errorMessage}}</p>-->
<!--            <p v-if="booksData.length===0 && noSearch===false"> No books found </p>-->

            <v-text-field
                input v-model="searchInput"
                class="my-searchBlock"
                hide-details="auto"
                color="#cbf1f1"
                placeholder="Sisesta autor, raamatu pealkiri või ISBN number"
                solo
            ></v-text-field>
            <v-btn class="search-button white--text" v-on:click="getBookData()">OTSI</v-btn>
          </div>
        </v-col>
<!--        <p v-if="booksData.length==0" >"Raamatuid ei leitud"</p>-->
<!--        {{booksdata}}-->
<!--        <p v-if="errorMessage" >{{errorMessage}}</p>-->
<!--        {{booksdata}}-->

        <v-col cols="12">
          <div class="headline1">LEITUD RAAMATUD</div>
          <div class="regular-text"> Siia tuleb errorMessage kui ühtegi raamatut ei leitud</div>
          <p v-if="errorMessage" >{{errorMessage}}</p>
          <p v-if="booksData.length===0 && noSearch===false"> No books found </p>
        </v-col>

        <table border="1" style="width:60%" align="center">
          <tr>
            <td> Book title</td>
            <td> Author</td>
            <td> ISBN</td>
            <td> Year of publishing</td>
            <td> No. of pages</td>
            <td> Format</td>
            <td> Price</td>
            <td> Image</td>
            <td> Store</td>
            <td> Link </td>
          </tr>
          <tr v-for="book in booksData">
            <td> {{ book.bookTitle }}</td>
            <td> {{ book.author }}</td>
            <td> {{ book.isbn }}</td>
            <td> {{ book.yearOfPublishing }}</td>
            <td> {{ book.numberOfPages }}</td>
            <td> {{ book.format }}</td>
            <td> {{ book.price }}</td>
            <td> {{ book.urlImage }}</td>
            <td> {{ book.storeName }}</td>
            <td> {{ book.urlData }}</td>
          </tr>
        </table>

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
export default{
  data: function () {
    return {
      'searchInput': '',
      'booksData': '',
      'errorMessage': '',
      'notFoundMessage': '',
      'noSearch': true
    }
  },
  methods: {
    'getBookData': function (){
      this.$http.get('api/booksearch/'+this.searchInput)
          .then(response=> {
            console.log(response);
            this.booksData=response.data
            this.noSearch=false
          })
          .catch(response=>{
            this.errorMessage='Insert valid search parameters'
          })
    }
  }
}
</script>

<style scoped>

</style>

