<template>
    <div class="container">
    <appHeader :quoteCount= "quotes.length" :maxQuotes= "maxQuotes"></appHeader>
    <appNewQuote @addNewQuote="newQuote"></appNewQuote>
    <appQuoteGrid :quotes="quotes" @quoteWasDeleted="deleteQuote"></appQuoteGrid>

    <div class="row">
        <div class= "col-sm-12 text-center">
            <div class="alert alert-info">Info: Click on a quote to delete it!</div>
        </div>
    </div>
    </div>
</template>

<script>

import QuoteGrid from './components/QuoteGrid';
import NewQuote from './components/NewQuote';
import Header from './components/Header';
    export default {
        data(){
            return{
                quotes: [
                    'Just a Quote'
                ],
                maxQuotes: 10
            }
           
        },
        methods:{
            newQuote(quote){
                if(this.quotes.length >= this.maxQuotes){
                    return alert('Please delete some of the quotes');
                }
                this.quotes.push(quote);
            },
            deleteQuote(index){
                this.quotes.splice(index,1);
            }
        },
         
        
        components: {
            appQuoteGrid: QuoteGrid,
            appNewQuote: NewQuote,
            appHeader: Header   
        }
    }
    
    
</script>

<style>
</style>
