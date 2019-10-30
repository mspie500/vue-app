<template>
  <div id="employee-header">
    <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
  
  
  
    <a class="navbar-brand text-uppercase" href="#">mattspielbauer.com</a>
    <ul class="navbar-nav mr-auto mt-2 mt-lg-0">
      <li class="nav-item active">
        <a class="nav-link text-right" href="#">Home <span class="sr-only">(current)</span></a>
      </li>
    </ul> 
  
</nav>

<header class="masthead">
  <div class="container h-100">
    <div class="row h-100 align-items-center">
      <div class="col-6 offset-md-3 text-center card py-4 shadow bg-dark text-white">
        <h1 class="font-weight-light">Emerging Web Trends LP2</h1>
        <p class="lead">An Exploration of Vue.js</p>
      </div>
    </div>
  </div>
</header>
  </div>
</template>

<script>
export default {
  name: 'employee-header'
}
</script>

<style scoped>
nav {
  box-shadow: 0px 2px 6px rgba(0,0,0,.3);
  border: 1px solid rgba(0,0,0,.1); 
  border-radius: 4px;
}
.masthead {
  height: 50vh;
  min-height: 500px;
  background-image: url('../assets/wht.jpg');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
}
</style>