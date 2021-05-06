<template>
  <div class="about">
    <h3>This is a test page to check book search results</h3>

    <p> Enter key word to look for results: </p>
    <br/>
    <input v-model="searchInput" placeholder="enter key-word">
    <button v-on:click="getBookData()"> Search</button>
    <br/>
    <br/>
    <p v-if="errorMessage" >{{errorMessage}}</p>
    <p v-if="booksData.length===0 && noSearch===false"> No books found </p>


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


  </div>
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
      location.reload()
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
