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
      console.log("lodaing lucky orange ...");

      if (process.env.NODE_ENV === "production") {
        window.__lo_site_id = 246087;
        (function() {
          window.__lo_site_id = 249064;

          (function() {
            var wa = document.createElement("script");
            wa.type = "text/javascript";
            wa.async = true;
            wa.src = "https://d10lpsik1i8c69.cloudfront.net/w.js";
            var s = document.getElementsByTagName("script")[0];
            s.parentNode.insertBefore(wa, s);
          })();
        })();
        console.log("lucky orange script loaded...");
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
