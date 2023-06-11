<script setup>
    import axios from 'axios';
</script>

<template>
    Brussels: {{ Brussels }}°C <br>
    Paris: {{ Paris }}°C 
</template>

<script>
const d = new Date();
let hour = d.getHours();

console.log(hour);

export default {
    data() {
        return {
            Brussels: '',
            Paris: ''
        }
    },
    mounted() {
        axios
            .get('https://api.open-meteo.com/v1/forecast?latitude=49.79&longitude=5.07&hourly=temperature_2m&forecast_days=1')
            // .then(response => (this.Brussels = response.data.hourly.temperature_2m[hour]))
            .then(response => (this.Brussels = response))

        axios
            .get('https://api.open-meteo.com/v1/forecast?latitude=48.85&longitude=2.35&hourly=temperature_2m&forecast_days=1')
            // .then(response => (this.Paris = response.data.hourly.temperature_2m[hour]))
            .then(response => (this.Paris = response))

    },
}
</script>