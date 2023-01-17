<template>
  <div>
    <ul class="news-list">
      <li v-for="job in this.$store.state.jobs" v-bind:key="job" class="post">
        <!-- 포인트 영역 -->
        <div class="points">
          <!-- job.points는 null일떼 0이 나오도록... -->
          {{ job.points || 0 }}
        </div>
        <!-- 기타 정보 영역 -->
        <div>
          <p class="news-title">
            <a :href="job.url">
              {{ job.title }}
            </a>
          </p>
          <small class="link-text">
            {{ job.time_ago }} by
            <a :href="job.url">{{ job.domain }}</a>
          </small>
        </div>
      </li>
    </ul>
    <!-- <p v-for="job in this.$store.state.jobs" v-bind:key="job">
      <a :href="job.url">
        {{ job.title }}
      </a>
      <small>{{ job.time_ago }} by {{ job.domain }}</small>
    </p> -->
  </div>
</template>

<script>
export default {
  created() {
    this.$store.dispatch('FETCH_JOBS');
  }
}
</script>

<style scoped>
.news-list {
    margin: 0;
    padding: 0;
  }
  .post {
    display: flex;
    align-items: center;
    list-style: none;
    border-block: 1px solid #eee;
  }
  .points {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 80px;
    height: 60px;
    color: #42b883;
  }
  .news-title {
    margin: 0;
  }
  .link-text {
    color: #828282;
  }
</style>