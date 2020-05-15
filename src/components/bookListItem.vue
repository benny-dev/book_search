<template>
    <li class="list-group-item media" @click="onBookSelect">
        <img :src="thumbnail" alt="The book cover art" class="mr-3" >
        <div class="media-body">
            <h5 class="mt-0 mb-1">{{ book.volumeInfo.title }}</h5>
            <span class="author">Authors: {{ book.volumeInfo.authors }}</span>
            <p> {{ book.volumeInfo.description }} </p>
        <span>Rating: 
            <span class="fa fa-star checked"></span>
            <span class="fa fa-star checked"></span>
            <span class="fa fa-star checked"></span>
        </span>
        </div>
    </li>
</template>

<script>
export default {
    name: 'bookListItem',
    props: ['book'],
    computed: {
        thumbnail () {
            return this.book.volumeInfo.imageLinks.smallThumbnail
        },
        // authors () {
        //     for (let i = 0; i < this.book.volumeInfo.authors.length; i++){
        //         return this.book.volumeInfo.authors[i];
        //     }
        // }
    },
    methods: {
        onBookSelect () {
            this.$emit('bookSelected', this.book);
        }
    }
}
</script>

<style scoped>
    h5 {
        font-family: 'Montserrat', sans-serif;
        color: blue;
    }

    .author {
        margin: 20px; 
        color: blue;
         
    }

    p{
        font-family: 'Cabin', sans-serif;
        /* width: inherit; */
        margin-bottom: 20px;
        font-size: 16px;
        overflow: hidden;
        display: -webkit-box;
        -webkit-line-clamp: 3;
        -webkit-box-orient: vertical;
        /* white-space: nowrap; */
        /* text-overflow: ellipsis; */
    }

    li {
        display: flex;
        flex-direction: row;
        cursor: pointer;
        margin-right: 5%;
    }

    li:hover {
        background-color: #f7f7f7
    }

    .checked {
         color: orange;
    }
</style>