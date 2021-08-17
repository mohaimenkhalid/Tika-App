<template>
  <div>
    <h1>Welcome!</h1>
    <h1 v-if="response" class="font-bold font-xl">Check - {{ response }}</h1>

    <button @click.prevent="test()">Get Data</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      response: ''
    }
  },

  mounted() {

  },

  methods: {
    test() {
      this.$axios.$get('/test')
      .then((res) => {
        console.log( res);
          this.response = res;
      })
    }
  }
}
</script>
