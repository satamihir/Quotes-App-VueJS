<template>
    <div class="row">
        <appQuote v-for="(quote,index) in quotes" @click.native="deleteQuote(index)">{{quote}}</appQuote>
    </div>
</template>

<script>
import Quote from './Quote';
export default {
    props: ['quotes'],
    methods:{
        deleteQuote(index) {
            this.$emit('quoteWasDeleted',index);
        }
    },
    components: {
    appQuote: Quote
    }

}



</script>

<style scoped>

</style>
