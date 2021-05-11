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
<!--          <div class="headline1">LEITUD RAAMATUD</div>-->
          <p v-if="noSearch===false && booksData.length!=0" class="headline1">LEITUD RAAMATUD</p>
          <p v-if="errorMessage" class="regular-text">{{errorMessage}}</p>
          <p v-if="booksData.length===0 && noSearch===false" class="regular-text"> Ei leitud raamatuid </p>

        </v-col>

<!--        <table border="1" style="width:60%" align="center">-->
<!--          <tr v-for="book in booksData">-->
<!--            <td> {{ book.bookTitle }}</td>-->
<!--            <td> {{ book.author }}</td>-->
<!--            <td> {{ book.isbn }}</td>-->
<!--            <td> {{ book.yearOfPublishing }}</td>-->
<!--            <td> {{ book.numberOfPages }}</td>-->
<!--            <td> {{ book.format }}</td>-->
<!--            <td> {{ book.price }}</td>-->
<!--            <td> {{ book.urlImage }}</td>-->
<!--            <td> {{ book.storeName }}</td>-->
<!--            <td> {{ book.urlData }}</td>-->
<!--          </tr>-->
<!--        </table>-->

        <v-card
            style="padding: 8px; margin-bottom: 16px"
            v-for="book in booksData"
            class="mx-auto"
            color="#cbf1f1"
            max-width="300"
            tiled
        >
          <v-list-item three-line>
            <v-img
                height="190"
                :src="book.urlImage"
                contain
            ></v-img>

            <!--            <v-list-item-avatar-->
<!--                tile-->
<!--                size="160"-->
<!--                color="grey"-->
<!--            ></v-list-item-avatar>-->
          </v-list-item>
          <v-list-item-content>
              <v-list-item-title class="book-headline">{{ book.bookTitle }}</v-list-item-title>
              <v-list-item-title class="book-headline">{{ book.author }}</v-list-item-title>
          </v-list-item-content>
            <v-list-item-content>
              <v-list-item-subtitle class="book-regular-text" v-if="book.isbn!=null" >Ribakood: {{ book.isbn }}</v-list-item-subtitle>
              <v-list-item-subtitle class="book-regular-text" v-if="book.yearOfPublishing!=null">Ilmumisaasta: {{ book.yearOfPublishing }}</v-list-item-subtitle>
             <!-- <v-list-item-subtitle class="book-regular-text">Lehekülgi: {{ book.numberOfPages }} -->
              <v-list-item-subtitle class="book-regular-text" v-if="book.format!=null">Formaat: {{ book.format }}</v-list-item-subtitle>
              <v-list-item-subtitle class="book-regular-text">Pood: {{ book.storeName }}</v-list-item-subtitle>
            </v-list-item-content>

          <!-- NB! Raamatukoil on kohati tühjad stringid ilmumisaasta koha peal-->

          <v-card-actions>
            <v-list-item-content class="book-price">
              <v-list-item-title class="book-price">{{ book.price }}</v-list-item-title>
            </v-list-item-content>
            <v-spacer></v-spacer>
            <v-btn class="search-button white--text" color="#136581" v-on:click="search()">Mine ostma {{ book.urlData }}</v-btn>
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
      'booksData': [],
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
            this.errorMessage=''
          })
          .catch(response=>{
            this.errorMessage='Sisesta sobivad otsinguparameetrid'
            this.booksData=[]
          })
    }
  }
}
</script>

<style scoped>

</style>

