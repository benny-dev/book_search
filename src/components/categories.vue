<template>
  <div>
      <h5>Categories</h5>
    <ul class="list-group list-group-flush">
      <li v-for="category in categories" :key="category" @click:>{{category}}</li>
    </ul>
  </div>
</template>

<script>
const categories = ['Self Improvement', 'Fiction', 'Non-Fiction', 'Sci-Fi', 'Cooking', 'Sports'];

export default {
    name: "Categories",
    data () {
        categories
    },
    methods: {
        makeSearchOnCategory (){

        }
    }
};
</script>

<style scoped>
    /* div{
        width: 10%;
        text-align: center;
        padding: 0;
    }

    h5 {
        font-family:  'Montserrat', sans-serif;
    }

    ul{
        display: inline-block;
        margin: 0;
        padding: 0;
    }

    li{
        font-family:  'Cabin', sans-serif;
        font-size: small;
        margin: 10px;
        color: blue;
    } */
</style>>