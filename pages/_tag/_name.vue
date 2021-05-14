<template>
  <div v-if="this.$route.params.name">
    作者：{{ this.$route.params.tag }} 书名：{{ this.$route.params.name }}
  </div>
</template>