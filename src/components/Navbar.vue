<template>
  <nav class="mainNav">
    <ul>
      <li>
        <router-link to="/">Home</router-link>
      </li>
      <li>
        <router-link to="/about/">About</router-link>
      </li>
      <li>
        <router-link to="/blogs">Blogs</router-link>
      </li>
    </ul>
    <h2>Profile Links</h2>
    <ul>
      <li v-for="(id, index) in userIds" :key="index">
        <router-link :to="{ name: 'ViewProfile', params: { user_id: id }}">
          <span>Profile {{ id }}</span>
        </router-link>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: "Navbar",
  data() {
    return {
      userIds: ["1", "2", "3"]
    };
  }
};
</script>

<style scoped>
nav {
  text-align: center;
}
nav ul {
  padding: 0;
}
nav li {
  display: inline-block;
  list-style-type: none;
  margin: 10px 20px;
}
nav a {
  color: #42b983;
  text-decoration: none;
}
a.router-link-exact-active {
  color: black;
}
</style>
