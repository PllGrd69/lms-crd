<template>
  <div>
<nav class="navbar navbar-expand-lg navbar-dark bg-dark">
  <a class="navbar-brand" href="#">LMS</a>
  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNavDropdown" aria-controls="navbarNavDropdown" aria-expanded="false" aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
  </button>
  <div class="collapse navbar-collapse text-white" id="navbarNavDropdown">
    <ul class="navbar-nav">
      <li class="nav-item active mx-3 text-white bg-dark">
        <router-link to="/"><span>Home</span></router-link>
      </li>
      <li class="nav-item mx-3 text-white bg-dark">
        <router-link to="/ping"><span>Ping</span></router-link>
      </li>
      <li class="nav-item mx-3 text-white bg-dark">
        <router-link to="/persons"><span>Persons</span></router-link>
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
span{
  color:#ffffff;
}
</style>
