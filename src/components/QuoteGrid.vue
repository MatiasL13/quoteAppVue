<template>
	<div class="row">
		<my-quote  @click.native="deleteQuote(index)" v-for="(quote, index) in quotes" :quote="quote">{{quote}}</my-quote>
	</div>
</template>


<script>
	import Quote from './Quote.vue';

	export default{
		props:['quotes'],
		components:{
			'my-quote': Quote
		},
		methods:{
			deleteQuote(index){
				this.$emit('deleteQuote', index);
        		/*var index = this.quotes.indexOf(quote);
        		if(index > -1)
        			this.quotes.splice(index, 1);*/

        	}
		}
	}
</script>

<style>
	
</style>