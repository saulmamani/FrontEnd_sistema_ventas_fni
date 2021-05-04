<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Principal</router-link> |
      <router-link to="/about">Sobre mi</router-link> |
      <router-link to="/personas">Personas</router-link>
    </div>

<!--    Aqui es donde se cargan las vistas de router y de router-link-->
    <router-view/>

  </div>
</template>

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
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
