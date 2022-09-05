<template>  
  <Form @useLocations="useLocations"/>
  <div ref="mapRef" id="map"></div>
</template>

<script>
import Form from './Form.vue'
import { ref, reactive, onMounted } from 'vue'
import axios from 'axios';
 
export default {
    components: {
        Form
    },
    setup() {        
        const mapRef = ref(null)

        const state = reactive({
            locations: []
        })

        const useLocations = (locations) => {
            state.locations = locations

            createMap(locations)
        }
    
        const createMap = (waypoints) => {            
            const API_KEY = 'rXGP0WD0wr73ApA886gAtl5QPiAgwfeX' 
            

            // lets create the URL for thewaypoint optimization API_KEY
            let URL = 'http://api.tomtom.com/routing/waypointoptimization/1?key=' + API_KEY

            axios.post(URL, {
                waypoints: waypoints.map(function (element) {
                    return {
                        point: {
                            latitude: element.lat,
                            longitude: element.lng
                        }
                    }
                })
            })
            .then(function (response) {
                console.log(response.data.optimizedOrder)                
            })
            .catch(function (error) {
                console.log(error)
            })            
        }
        
        return {
            useLocations,
            mapRef
        }
   }     
   
}
</script>

<style scoped>
#map {
      height: 70vh;
      width: 50vw;
      margin: 0 auto;
      background-color: aquamarine;
}
</style>
