<template>

  <div class="jumbotron">
      <div class="container">
        <h1>Bienvenue sur l'application météo</h1><img src="http://icons.iconarchive.com/icons/wikipedia/flags/256/FR-France-Flag-icon.png" style=" width: 100px; height: 100px;">
        <h1>Welcome to App-Weather</h1><img src="http://www.iconarchive.com/download/i47324/icons-land/vista-flags/United-Kingdom-Flag-1.ico" style=" width: 100px; height: 100px;">
      </div>
      <div class="header">
        <img src="http://download.seaicons.com/icons/wineass/ios7-redesign/512/Weather-icon.png">
      </div>
      <div class="textarea">
      <p> Bienvenue sur l'application météo, pour avoir la météo en temps réel partout dans le monde dans 
          n'importe quel pays.</p>
      <p>Cette application a été réalisée en : 
        <ul>
          <li>JavaScript</li>
          <li>VueJS</li>
        </ul>
      </p>
      </div>
  </div>
</template>


<script>
export default {
  name: 'Home',
  data () {
    return {
     success: false
    }
  },
  methods: {
    
    open: function() {
      if(this.success == false){
        this.success = true
      }
      else{
        this.success = false
      }
    }
    
  }
}
</script>


<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>

.container
{
  display: flex;
  justify-content: space-around;
  background-color: lightblue;
}
.jumbotron
{
  background-color: #2a9fd6;
}

.header
{
  display: flex;
  flex-direction: row;
  justify-content: center;
  margin-top: 20px;
}
.textarea
{
  margin-top: 20px;
  text-align: center;
}
img
{
  width: 300px;
  height: 300px;
}

</style>
