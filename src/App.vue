<template>
    <div class="container">
    	<my-header :maxQuotes="maxQuotes" :cantQuotes="quotes.length"></my-header>
    	<my-new-quote @addQuote="newQuote" ></my-new-quote>
    	<my-quote-grid @deleteQuote="deleteQuote" :quotes="quotes"></my-quote-grid>
    	<div class="row">
    		<div class="col-sm-12 text-center">
    			<div class="alert alert-info">Click for detele</div>
    		</div>
    	</div>
    </div>
</template>

<script>
	import Header from './components/Header.vue';
	import QuoteGrid from './components/QuoteGrid.vue';
	import NewQuote from './components/NewQuote.vue';
    export default {

    	components:{
    		'my-header': Header,
    		'my-quote-grid': QuoteGrid,
    		'my-new-quote': NewQuote
    	},
        data: function(){
        	return{
        		quotes: [
        			'quote'
        			],
        		maxQuotes: 10
        	}
        },
        methods:{
        	newQuote(quote){
        		if(this.quotes.length < this.maxQuotes)
        			this.quotes.push(quote);
        		else
        			alert("delete some quotes");
        	},
        	deleteQuote(index){
        		this.quotes.splice(index, 1);
        	}
        }
    }
</script>

<style>
</style>
