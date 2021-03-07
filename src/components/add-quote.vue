<template>
  <div class="form-floating d-flex flex-column align-items-center">
    <div class="block d-flex flex-column align-items-start mb-3">
      <span class="mb-2">Quote</span>
      <textarea class="form-control" rows="3" name="text" v-model="text"/>
    </div>
    <div>
      <button type="button" class="btn btn-primary" @click="onAddQuote">Add Quote</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AddQuote',
  props: {
    addQuote: Function,
  },
  data() {
      return {
        text: ''
      };
  },
  methods: {
    onAddQuote() {
      if(this.text) {
      this.addQuote(this.text);
      this.text = '';
      }
      
    }
  }
}
</script>


<style>
  .block {
    width: 500px;
  }
</style>
