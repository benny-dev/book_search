<template>
    <div>
        <input @input="onInput" class="form-control"/>   
    </div>
</template>

<script>
export default {
    name: 'SearchBar',
    methods : {
        onInput: function (evt){
            this.$emit('termChange', evt.target.value);
        }
    }
}
</script>

<style scoped>
    input{
        width: 75%;
    }

    div {
        text-align: center;
        margin: 20px;
    }
</style>>