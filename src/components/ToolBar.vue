<template>
  <div class="header">
    <router-link to="/news">News이지미디어</router-link> |
    <router-link to="/ask">Ask이지미디어</router-link> |
    <router-link to="/jobs">Jobs이지미디어</router-link>
  </div>
</template>

<style scroped>
.header {
  display: flex;
  padding: 8px;
  color: white;
  background-color: #42b883;
}
.header .router-link-exact-active {
  color: #35495e;
}
.header a {
  color: white;
}
</style>
