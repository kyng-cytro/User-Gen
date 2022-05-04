<template>
  <nav class="navMenu">
    <router-link to="/">Gen</router-link>
    <router-link to="/about">About</router-link>
  </nav>
</template>
<style scoped>
.navMenu {
  font-family: Inter, sans-serif;
}
.navMenu a {
  color: #fff;
  text-decoration: none;
  font-size: 1.2em;
  text-transform: uppercase;
  font-weight: 500;
  display: inline-block;
  width: 80px;
  -webkit-transition: all 0.2s ease-in-out;
  transition: all 0.2s ease-in-out;
}
.navMenu a:hover,
.navMenu a.router-link-active {
  color: #000;
}
</style>
