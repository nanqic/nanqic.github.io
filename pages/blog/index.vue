<template>
  <div>
    <h1>Blog</h1>
    <div>
      <ul>
        <li v-for="item in list" :key="item.title">
          <nuxt-link :to="'/blog' + item.path">{{ item.title }}</nuxt-link>
        </li>
      </ul>
    </div>
  </div>
</template>
<script>
export default {
  async asyncData({ $content }) {
    const mdList = await $content("java").sortBy("position", "asc").fetch();
    return { list: mdList };
  },
};
</script>