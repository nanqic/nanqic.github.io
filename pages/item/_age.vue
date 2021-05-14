<template>
  <div>
    <h1>年龄</h1>
    <hr />
    <div v-if="this.$route.params.age">
      用户年龄：{{ this.$route.params.age }}
    </div>
  </div>
</template>
<script>
export default {
  validate({ params }) {
    return /^\d+$/.test(params.age);
  },
};
</script>