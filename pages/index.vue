<template>
  <div class="container">
    <h1 class="title">myweb</h1>
    <b-button variant="danger">按钮</b-button>
    <b-button variant="outline-primary" @click="hello()">hello</b-button>
  </div>
</template>

<script>
export default {
  methods: {
    hello: function () {
      alert("hello, nuxtjs");
    },
  },
};
</script>

<style>
</style>
