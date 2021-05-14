<template>
  <div>
    <h1>古诗词</h1>
    <div>
      <h2>年代：{{ data.data.dynasty }}</h2>
      <h2>题目：{{ data.data.subject }}</h2>
      <h3>作者：{{ data.data.author }}</h3>
      <p>{{ data.data.content }}</p>
    </div>
    <!-- {{ data.data }} -->
    <br />
    <b-button variant="primary" @click="fetchData()">换一首</b-button>
  </div>
</template>
<script>
export default {
  data: function () {
    return { data: [] };
  },
  async asyncData({ $axios }) {
    let poem = await $axios.$get("/api/yan/gc.php");
    poem = JSON.parse(poem.slice(0, -3));
    return { data: poem };
  },
  methods: {
    async fetchData() {
      let poem = await this.$axios.$get("/api/yan/gc.php");
      this.data = JSON.parse(poem.slice(0, -3));
      // console.log(this.data);
    },
  },
  // mounted: function () {
  //   // this.$options.methods.fetchData(); //不可用，报错$get未定义
  //   this.fetchData(); // 初始化时报错Cannot read property 'dynasty' of undefined
  // },
};
</script>