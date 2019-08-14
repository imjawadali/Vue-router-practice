<template>
  <div class="viewProfile">
    <h1>Profile</h1>
    <p>{{ userId }}</p>
  </div>
</template>

<script>
export default {
  name: "ViewProfile",
  data() {
    return {
      userId: this.$route.params.user_id
    };
  },
  methods: {
    updateId() {
        this.userId = this.$route.params.user_id
    }
  },
  watch: {
    '$route.params.user_id': "updateId"
  }
};
</script>

<style scoped>
.viewProfile {
  text-align: center;
}
</style>
