<template>
  <ProgressBar :count="data.length" />
  <AddQuote :addQuote="addQuote"/>
  <div class="m-5 d-flex flex-wrap">
    <Quote v-for="(item, index) in data" :key="item" :quote="item" :index="index" :deleteQuote="deleteQuote" />
  </div>
</template>

<script>
import AddQuote from './components/add-quote.vue'
import Quote from './components/quote.vue'
import ProgressBar from './components/progress-bar.vue'
// import data from './data/data.json';

export default {
  name: 'App',
  components: {
    AddQuote,
    Quote,
    ProgressBar,
  },
  data() {
      return {
        data: []
      };
  },
  mounted() {
    if (localStorage.getItem('quotes')) {
      try {
        this.data = JSON.parse(localStorage.getItem('quotes'));
      } catch(e) {
        localStorage.removeItem('quotes');
      }
    }
  },
  methods: {
    addQuote(quote) {
      if(this.data.length < 10) {
        this.data.push(quote);
        localStorage.setItem('quotes', JSON.stringify(this.data));
      }
      else {
        alert('Для добавления новых цитат удалите одну из добавленных');
      }
    },
    deleteQuote(index) {
      this.data.splice(index, 1);
      localStorage.setItem('quotes', JSON.stringify(this.data));
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
