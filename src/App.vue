<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <router-view />
  </div>
</template>

<script>
export default {
  methods: {
    loadLuckyOrange: () => {
      if (process.env.NODE_ENV === "production") {
        window.__lo_site_id = 249064;
        let script = document.createElement("script");
        script.type = "text/javascript";
        script.async = true;
        script.setAttribute(
          "src",
          "https://d10lpsik1i8c69.cloudfront.net/w.js"
        );
        document.head.appendChild(script);
      }
    }
  },
  beforeMount() {
    this.loadLuckyOrange();
  }
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
