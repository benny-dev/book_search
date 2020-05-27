<template>
    <ul class="list-group list-group-flush">
        <bookListItem v-for="book in books" :key="book.etag" :book="book" @bookSelected="onBookSelect">

        </bookListItem>
    </ul>
</template>

<script>
import bookListItem from './bookListItem';

export default {
    name: 'bookList',
    components: {
        bookListItem
    },  
    props: ['books'],
    methods: {
        onBookSelect (book){
            this.$emit('bookSelected', book);
        }
    }
}
</script>

<style>
    ul {
        margin: 20px;
        width: 70%;
        /* text-align: center; */
    }
</style>
