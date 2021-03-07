<template>
  <div class="border rounded p-3 quote mx-4 mb-4" @click="deleteQuote(index)">{{quote}}</div>
</template>

<script>
export default {
  name: 'Quote',
  props: {
    quote: String,
    index: Number,
    deleteQuote: Function,
  },
}
</script>


<style>
    .quote {
        font-family: Arizonia;
        width: 300px;
        text-align: start;
    }
</style>
