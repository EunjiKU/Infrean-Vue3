<template>
  <div class="header">
    ⭐섹션3-2⭐
    <router-link to="/news">New</router-link> |
    <router-link to="/ask">Ask</router-link> |
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
.header a:first-child {
  margin-right: 6px;
}
.header a:nth-child(2) {
  margin: 0 6px;
}
.header a:last-child {
  margin-left: 6px;
}
</style>