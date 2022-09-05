<template>
    <div id="sole-form">
        <!-- Origin -->
        <div class="row"> 
            <p>Your Origin:</p>    
            <div class="col">
                <input type="text" class="form-control" placeholder="Enter longitude" v-model="waypoints[0].lng">
            </div>
            <div class="col">
                <input type="password" class="form-control" placeholder="Enter latitude" v-model="waypoints[0].lat">
            </div>
        </div>
        <hr>
        <!-- Waypoints -->
        <div class="row"> 
            <p>1:</p>    
            <div class="col">
                <input type="text" class="form-control" placeholder="Enter longitude" v-model="waypoints[1].lng">
            </div>
            <div class="col">
                <input type="password" class="form-control" placeholder="Enter latitude" v-model="waypoints[1].lat">
            </div>
        </div>
        <div class="row"> 
            <p>2:</p>    
            <div class="col">
                <input type="text" class="form-control" placeholder="Enter longitude" v-model="waypoints[2].lng">
            </div>
            <div class="col">
                <input type="password" class="form-control" placeholder="Enter latitude" v-model="waypoints[2].lat">
            </div>
        </div>

        <div class="row"> 
            <p>3:</p>    
            <div class="col">
                <input type="text" class="form-control" placeholder="Enter longitude" v-model="waypoints[3].lng">
            </div>
            <div class="col">
                <input type="password" class="form-control" placeholder="Enter latitude" v-model="waypoints[3].lat">
            </div>
        </div>

        <div class="row"> 
            <p>4:</p>    
            <div class="col">
                <input type="text" class="form-control" placeholder="Enter longitude" v-model="waypoints[4].lng">
            </div>
            <div class="col">
                <input type="password" class="form-control" placeholder="Enter latitude" v-model="waypoints[4].lat">
            </div>
        </div>

        <div class="row"> 
            <p>5:</p>    
            <div class="col">
                <input type="text" class="form-control" placeholder="Enter longitude" v-model="waypoints[5].lng">
            </div>
            <div class="col">
                <input type="password" class="form-control" placeholder="Enter latitude" v-model="waypoints[5].lat">
            </div>
        </div>

        <div class="row"> 
            <p>6:</p>    
            <div class="col">
                <input type="text" class="form-control" placeholder="Enter longitude" v-model="waypoints[6].lng">
            </div>
            <div class="col">
                <input type="password" class="form-control" placeholder="Enter latitude" v-model="waypoints[6].lat">
            </div>
        </div>

        <div class="row"> 
            <p>7:</p>    
            <div class="col">
                <input type="text" class="form-control" placeholder="Enter longitude" v-model="waypoints[7].lng">
            </div>
            <div class="col">
                <input type="password" class="form-control" placeholder="Enter latitude" v-model="waypoints[7].lat">
            </div>
        </div>

        <div class="row"> 
            <p>8:</p>    
            <div class="col">
                <input type="text" class="form-control" placeholder="Enter longitude" v-model="waypoints[8].lng">
            </div>
            <div class="col">
                <input type="password" class="form-control" placeholder="Enter latitude" v-model="waypoints[8].lat">
            </div>
        </div>

        <div class="row"> 
            <p>9:</p>    
            <div class="col">
                <input type="text" class="form-control" placeholder="Enter longitude" v-model="waypoints[9].lng">
            </div>
            <div class="col">
                <input type="password" class="form-control" placeholder="Enter latitude" v-model="waypoints[9].lat">
            </div>
        </div>

        <div class="row"> 
            <p>10:</p>    
            <div class="col">
                <input type="text" class="form-control" placeholder="Enter longitude" v-model="waypoints[10].lng">
            </div>
            <div class="col">
                <input type="password" class="form-control" placeholder="Enter latitude" v-model="waypoints[10].lat">
            </div>
        </div>

        <div class="row"> 
            <p>11:</p>    
            <div class="col">
                <input type="text" class="form-control" placeholder="Enter longitude" v-model="waypoints[11].lng">
            </div>
            <div class="col">
                <input type="password" class="form-control" placeholder="Enter latitude" v-model="waypoints[11].lat">
            </div>
        </div>
    
        <button @click="getOptimizedRoutes">Submit</button>       
    </div>

    <!-- Map below -->
	<div class="card text-center m-3"></div>
</template>

<script>
export default {
  name: "post-request",
  data() {
    return {
            waypoints: [
                { lng: null,  lat : null },
                { lng: null, lat: null },
                { lng: null, lat: null } ,
                { lng: null, lat: null },
                { lng: null, lat: null },
                { lng: null, lat: null },
                { lng: null, lat: null },
                { lng: null, lat: null },
                { lng: null, lat: null },
                { lng: null, lat: null },
                { lng: null, lat: null },
                { lng: null, lat: null },
            ]
    };
  },
  methods: {
    getOptimizedRoutes() {
      
        const data = {

            waypoints: this.waypoints.map((location) => {

            return {

                point: {

                latitude: location.lat,

                longitude: location.lng,

                },

            };

            }),

            options: {

            travelMode: "car",

            vehicleMaxSpeed: 0,

            vehicleCommercial: true,

            vehicleLoadType: ["otherHazmatGeneral"],

            traffic: "live",

        departAt: "now",

            outputExtensions: ["travelTimes", "routeLengths"],

            waypointConstraints: {

                originIndex: 0,

                destinationIndex: 0,

            },

            },

        };

        const requestOptions = {
            method: "POST",

            headers: { "Content-type": "application/json;charset=UTF-8" },

            body: JSON.stringify(data),
        };

        fetch("https://api.tomtom.com/routing/waypointoptimization/1/best?key=rXGP0WD0wr73ApA886gAtl5QPiAgwfeX", requestOptions)
            .then(response => response.json())
            .then(data => console.log(data))
    },
    handleInput() {
      console.log('Text input changed');
    },
  },
  created() {
    console.log('Loaded!');
  }
};
	
</script>

<!-- Use preprocessors via the lang attribute! e.g. <style lang="scss"> -->
<style>
#app {
	font-family: Avenir, Helvetica, Arial, sans-serif;
	text-align: center;
	color: #2c3e50;
	margin-top: 60px;
}

a,
button {
	color: #4fc08d;
}

button {
	background: none;
	border: solid 1px;
	border-radius: 2em;
	font: inherit;
	padding: 0.75em 2em;
}
</style>
