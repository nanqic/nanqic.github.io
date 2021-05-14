<template>
  <div>
    <div>{{ this.$route.params.archive }}/{{ this.$route.params.name }}</div>
    <h3>{{ page.title }}</h3>
    <hr />
    <div>
      <nuxt-content :document="page" />
    </div>
    <hr />
  </div>
</template>
<script>
export default {
  async asyncData({ params, $content }) {
    const page = await $content(`${params.archive}/${params.name}`).fetch();
    return { page };
  },
};
</script>