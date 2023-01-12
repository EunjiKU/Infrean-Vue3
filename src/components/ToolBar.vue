<template>
  <div class="header">
    <router-link to="/news">News뉴스</router-link> |
    <router-link to="/ask">Ask애스크</router-link> |
    <router-link to="/jobs">Jobs</router-link>
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
