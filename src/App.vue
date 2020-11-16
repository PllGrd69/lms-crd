<template>
  <div>

  <p>
    <!-- use router-link component for navigation. -->
    <!-- specify the link by passing the `to` prop. -->
    <!-- `<router-link>` will be rendered as an `<a>` tag by default -->
    <!--
    <router-link to="/">Home</router-link>
    <router-link to="/ping">Go to Ping</router-link>
    <router-link to="/persons">Go to Persons</router-link> -->
  </p>
<nav class="navbar navbar-expand-lg navbar-dark bg-dark">
  <a class="navbar-brand" href="#">Navbar</a>
  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNavDropdown" aria-controls="navbarNavDropdown" aria-expanded="false" aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
  </button>
  <div class="collapse navbar-collapse text-white" id="navbarNavDropdown">
    <ul class="navbar-nav">
      <li class="nav-item active mx-3 text-white bg-dark">
        <router-link to="/">Home</router-link>
      </li>
      <li class="nav-item mx-3 text-white bg-dark">
        <router-link to="/ping">Go to Ping</router-link>
      </li>
      <li class="nav-item mx-3 text-white bg-dark">
        <router-link to="/persons">Go to Persons</router-link>
      </li>
    </ul>
  </div>
</nav>


    <router-view/>
  </div>
</template>


<style>
.appx {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
li{
  color:#ffffff;
}
</style>
