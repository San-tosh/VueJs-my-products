<template>
  <div id="app">
    <div class="container">
        <app-progress-bar></app-progress-bar>
        <app-add-quote></app-add-quote>
        <app-quote-list></app-quote-list>
        <app-footer></app-footer>
    </div>
  </div>
</template>

<script>
import ProgressBar from './components/ProgressBar.vue';
import AddQuote from './components/AddQuote.vue';
import QuoteList from './components/QuoteList.vue';
import Footer from './components/Footer.vue';
export default {
  components:{
    appProgressBar:ProgressBar,
    'app-add-quote':AddQuote,
    appQuoteList:QuoteList,
    appFooter:Footer
  }

}
</script>

<style>

</style>
