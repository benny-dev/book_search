<template>
  <div class="container">
      <SearchBar @termChange="onTermChange"></SearchBar>
      <div class="main">
        <bookList :books="books" @bookSelected="goToBookPage"></bookList>
        <categories></categories>
      </div>
  </div>
</template>
 
<script>
import axios from 'axios';
import SearchBar from './components/SearchBar';
import bookList from './components/bookList';
import categories from './components/categories';
const API_KEY = '';

export default {
    name: 'App',
    components: {
        SearchBar,
        bookList,
        categories
    },
    data() {
        return { books: []};
    },
    methods: {
        onTermChange (searchTerm){
            axios.get('https://www.googleapis.com/books/v1/volumes?', {
                params: {
                    key: API_KEY,
                    q: searchTerm,
                }
            }).then(response => {
                this.books = response.data.items
            });
        },
        goToBookPage (book){
            console.log(book);
            window.open(book.volumeInfo.previewLink, '_blank');
        }
    }
};
</script>

<style>
    .main {
        display: flex;
    }
</style>
