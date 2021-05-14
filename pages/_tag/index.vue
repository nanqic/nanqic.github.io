<template>
  <div>
    书籍一览（{{ this.$route.params.tag }}）
    <ul>
      <li>
        <a :href="this.$route.params.tag + '/《灵魂永生》'">《灵魂永生》</a>
      </li>
      <li>
        <a :href="this.$route.params.tag + '/《个人实相的本质》'"
          >《个人实相的本质》</a
        >
      </li>
    </ul>
  </div>
</template>