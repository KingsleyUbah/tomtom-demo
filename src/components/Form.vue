<template>
    <div id="sole-form">
    <!-- Origin -->
    <div class="row"> 
        <p>Your Origin:</p>    
        <div class="col">
            <input type="text" class="form-control" placeholder="Enter longitude" v-model="wp1Lng">
        </div>
        <div class="col">
            <input type="password" class="form-control" placeholder="Enter latitude" v-model="wp1Lat">
        </div>
    </div>
    <hr>
    <!-- Waypoints -->
    <div class="row"> 
        <p>1:</p>    
        <div class="col">
            <input type="text" class="form-control" placeholder="Enter longitude" v-model="wp2Lng">
        </div>
        <div class="col">
            <input type="password" class="form-control" placeholder="Enter latitude" v-model="wp2Lat">
        </div>
    </div>
    <div class="row"> 
        <p>2:</p>    
        <div class="col">
            <input type="text" class="form-control" placeholder="Enter longitude" v-model="wp3Lng">
        </div>
        <div class="col">
            <input type="password" class="form-control" placeholder="Enter latitude" v-model="wp3Lat">
        </div>
    </div>

    <div class="row"> 
        <p>3:</p>    
        <div class="col">
            <input type="text" class="form-control" placeholder="Enter longitude" v-model="wp4Lng">
        </div>
        <div class="col">
            <input type="password" class="form-control" placeholder="Enter latitude" v-model="wp4Lat">
        </div>
    </div>

    <div class="row"> 
        <p>4:</p>    
        <div class="col">
            <input type="text" class="form-control" placeholder="Enter longitude" v-model="wp5Lng">
        </div>
        <div class="col">
            <input type="password" class="form-control" placeholder="Enter latitude" v-model="wp5Lat">
        </div>
    </div>

    <div class="row"> 
        <p>5:</p>    
        <div class="col">
            <input type="text" class="form-control" placeholder="Enter longitude" v-model="wp6Lng">
        </div>
        <div class="col">
            <input type="password" class="form-control" placeholder="Enter latitude" v-model="wp6Lat">
        </div>
    </div>

    <div class="row"> 
        <p>6:</p>    
        <div class="col">
            <input type="text" class="form-control" placeholder="Enter longitude" v-model="wp7Lng">
        </div>
        <div class="col">
            <input type="password" class="form-control" placeholder="Enter latitude" v-model="wp7Lat">
        </div>
    </div>

    <div class="row"> 
        <p>7:</p>    
        <div class="col">
            <input type="text" class="form-control" placeholder="Enter longitude" v-model="wp8Lng">
        </div>
        <div class="col">
            <input type="password" class="form-control" placeholder="Enter latitude" v-model="wp8Lat">
        </div>
    </div>

    <div class="row"> 
        <p>8:</p>    
        <div class="col">
            <input type="text" class="form-control" placeholder="Enter longitude" v-model="wp9Lng">
        </div>
        <div class="col">
            <input type="password" class="form-control" placeholder="Enter latitude" v-model="wp9Lat">
        </div>
    </div>

    <div class="row"> 
        <p>9:</p>    
        <div class="col">
            <input type="text" class="form-control" placeholder="Enter longitude" v-model="wp10Lng">
        </div>
        <div class="col">
            <input type="password" class="form-control" placeholder="Enter latitude" v-model="wp10Lat">
        </div>
    </div>

    <div class="row"> 
        <p>10:</p>    
        <div class="col">
            <input type="text" class="form-control" placeholder="Enter longitude" v-model="wp11Lng">
        </div>
        <div class="col">
            <input type="password" class="form-control" placeholder="Enter latitude" v-model="wp11Lat">
        </div>
    </div>

    <div class="row"> 
        <p>11:</p>    
        <div class="col">
            <input type="text" class="form-control" placeholder="Enter longitude" v-model="wp12Lng">
        </div>
        <div class="col">
            <input type="password" class="form-control" placeholder="Enter latitude" v-model="wp12Lat">
        </div>
    </div>
    <button @click="sendLocations">Submit</button>    
    </div>
</template>

<script>
import { ref } from 'vue'

export default {
    setup(props, context) {
        const wp1Lng = ref('')
        const wp1Lat = ref('')

        const wp2Lng = ref('')
        const wp2Lat = ref('')

        const wp3Lng = ref('')
        const wp3Lat = ref('')

        const wp4Lng = ref('')
        const wp4Lat = ref('')

        const wp5Lng = ref('')
        const wp5Lat = ref('')

        const wp6Lng = ref('')
        const wp6Lat = ref('')

        const wp7Lng = ref('')
        const wp7Lat = ref('')

        const wp8Lng = ref('')
        const wp8Lat = ref('')

        const wp9Lng = ref('')
        const wp9Lat = ref('')

        const wp10Lng = ref('')
        const wp10Lat = ref('')

        const wp11Lng = ref('')
        const wp11Lat = ref('')

        const wp12Lng = ref('')
        const wp12Lat = ref('')
        
        const sendLocations = () => {
            context.emit('useLocations', 
            [
                {lat: Number(wp1Lat.value), lng: Number(wp1Lng.value)},
                {lat: Number(wp2Lat.value), lng: Number(wp2Lng.value)},
                {lat: Number(wp3Lat.value), lng: Number(wp3Lng.value)},
                {lat: Number(wp4Lat.value), lng: Number(wp4Lng.value)},
                {lat: Number(wp5Lat.value), lng: Number(wp5Lng.value)},
                {lat: Number(wp6Lat.value), lng: Number(wp6Lng.value)},
                {lat: Number(wp7Lat.value), lng: Number(wp7Lng.value)},
                {lat: Number(wp8Lat.value), lng: Number(wp8Lng.value)},
                {lat: Number(wp9Lat.value), lng: Number(wp9Lng.value)},
                {lat: Number(wp10Lat.value), lng: Number(wp10Lng.value)},
                {lat: Number(wp11Lat.value), lng: Number(wp11Lng.value)},                
            ])
        }
        return {
            wp1Lng,
            wp1Lat,
            wp3Lng,
            wp3Lat,
            wp2Lng,
            wp2Lat,
            wp4Lng,
            wp4Lat,
            wp5Lng,
            wp5Lat,
            wp6Lng,
            wp6Lat,
            wp7Lng,
            wp7Lat,
            wp8Lng,
            wp8Lat,
            wp9Lng,
            wp9Lat,
            wp10Lng,
            wp10Lat,
            wp11Lng,
            wp11Lat,
            wp12Lng,
            wp12Lat,
            sendLocations
        }       
    },
}
</script>

<style scoped>
p {
    font-weight: bold;
}
</style>
