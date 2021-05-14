<template>
  <div>
    <h1>about this website.</h1>
    <h3>{{ counter }}</h3>
    <b-button @click="increment">喜加一</b-button>
    <hr />
    <nuxt-content :document="md" />
    <img src="~/assets/images/IMG_0372.JPG" width="200" />
  </div>
</template>
<script>
import { mapState } from "vuex";
import { mapMutations } from "vuex";
export default {
  name: "about",
  computed: {
    // 映射store.state
    ...mapState({
      counter: (state) => state.counter,
    }),
  },
  async asyncData({ $content }) {
    const md = await $content("java/java学习记录").fetch();
    return { md };
  },
  methods: {
    ...mapMutations({
      increment: "increment",
    }),
  },
};
</script>