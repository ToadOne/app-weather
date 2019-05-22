<template>
  <div id="app">
    <nav class="navbar navbar-expand-lg navbar-dark bg-primary">
      <a class="navbar-brand" href="#">What's weather today ?</a>
      <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarColor01" aria-controls="navbarColor01" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>

      <div class="collapse navbar-collapse" id="navbarColor01">
        <ul class="navbar-nav mr-auto">
          <li class="nav-item">
            <router-link class="nav-link" to="/">Accueil</router-link>
          </li>
          <li class="nav-item">
            <router-link class="nav-link" to="/meteo">Meteo</router-link>
          </li>
        </ul>
      </div>
    </nav>
    <router-view/>
    <footer class="footer"> App weather - 2018</footer>
  </div>
</template>

<script>
export default {
  name: 'App'
}

</script>

<style>
  .footer{
    width: 100%;
     height: 50px;
      background-color: #2a9fd6;
      text-align: center;
      color: #FFFFFF;
      padding-top: 10px;
      

  }

</style>
