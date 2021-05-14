<template>
  <div>
    <h1>商品</h1>
    <hr />
    <div v-if="this.$route.params.id">商品id：{{ this.$route.params.id }}</div>
  </div>
</template>