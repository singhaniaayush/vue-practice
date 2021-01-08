<template>
  <div id="app">
    {{ user.userName }} - {{ fullName }}
    <div><strong> followers </strong> {{ followers }}</div>
    <button @click="follow">follow</button>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      followers: 0,
      user: {
        id: 1,
        userName: "@ayushSinghania",
        firstName: "Ayush",
        lastName: "Singhania",
        email: "ayushSinghania@gmail.com",
        isAdmin: true,
      },
    };
  },
  computed: {
    fullName() {
      return `${this.user.firstName} ${this.user.lastName}`;
    },
  },

  methods: {
    follow() {
      this.followers++;
    },
  },
  watch: {
    followers(oldValue, newValue) {
      console.log(oldValue + ':' + newValue);
    },
  },
  mounted() {
    this.follow();
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
