<template>
  <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link :to="{ name: 'About' }">About</router-link>|
      <router-link :to="{ name: 'Education' }">Education</router-link>|
      <router-link :to="{ name: 'Jobs' }">Jobs</router-link>
  </div>
  <button @click="back">Go Back</button>
  <button @click="forward">Go Forward</button>
  <router-view/>
  <button @click="redirect">Home</button>
</template>
<script>
export default {
  methods: {
    redirect(){
      this.$router.push({name: 'Home'})
    },
    forward(){
      this.$router.go(1)
    },
    back(){
      this.$router.go(-1)
    }
  }
}
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
  text-decoration: none;
  padding: 10px;
  border-radius: 4px;
}

#nav a.router-link-exact-active {
  color: black;
  background: blueviolet;
}
button {
  margin: 0 10px;
  padding: 10px;
  border: none;
  border-radius: 4px;
  background: lightblue;
}
button:hover{
  background: blue;
}
</style>
