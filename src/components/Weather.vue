<template>
    <div id="app">
        <div class="card text-white bg-primary mb-3">
            <div class="card-header">
                        My Weather 2018
                        <form>
                            <input class="input" type="text" v-model.trim="city" placeholder="Entrez une ville">
                            <button class="btn btn-success"  v-on:click="search" >Recherche   <span class="glyphicon glyphicon-search "></span></button>
                        </form>
            </div>
            <div class="card-body"><hr>
                <h3 class="jojo"> City of {{ info.data.name }}</h3><br><h3>{{ info.data.weather[0].description }}</h3><hr>
                <img class="icon-current-weather" v-bind:src="'http://openweathermap.org/img/w/' + info.data.weather[0].icon + '.png'"/><hr>
                <div class="box"><i class="fas fa-temperature-high " style="font-size:20px;color:#FFFFFF"></i> Temp : {{ Math.round(info.data.main.temp-273.15) }} <strong>C°</strong></div>
                <div class="box"><i class="fas fa-wind"></i> Wind Speed: {{ info.data.wind.speed }} Km/h</div>
                <div class="box"><i class="fas fa-water"></i> Humidity: {{ info.data.main.humidity }} %</div>
                <div class="box"><i class="fas fa-map-marked-alt"></i> Country : {{ info.data.sys.country}}</div>
            </div>
        </div>
    </div>   
</template>

<script>
    export default {
        name: 'Weather',
        data(){
            return {
                info: [],
                city: 'Tours'
            }
        },
        mounted () {
            this.updateWeather('Tours')
            this.animate()
        
        },
        methods:{

            updateWeather: function(city){
                this.$axios
                .get('http://api.openweathermap.org/data/2.5/weather?q=' + city + '&appid=941b9aa3466642077e44fc4d6fefbd08')
                .then(response => (this.info = response))
                .catch(error => {
                    console.log(error);
                })
            },
            search: function(city){          
                this.updateWeather(this.city)
                
            },
            animate: function(){
                const element =  document.querySelector('.jojo')
                element.classList.add('animated', 'bounce')
            }

        }
    }
</script>

<style>

    .card{
        width: 100%;
    }

    .card-header{
        display: flex; 
        flex-direction: row;
        justify-content: space-around;
        align-items: center;
        
    }

    .icon-current-weather{
        width: 25%;
        border: 5px solid white;
    }
    .card-body{
        text-align: center;
        
    }
    .input{
        margin-right: 10px;
    }
    .box{
        font-size: 18px;
    }

</style>

