<script setup>
import HeaderApp from './assets/header.vue'
import Todo from './components/todo.vue'
import HelloLog from './components/helloLog.vue'
import weather from './components/weather.vue'
import { ref } from 'vue'

const page = ref('');

function changePage(value) {
    page.value = value;
}
</script>

<template>
    <HeaderApp @updatepage="changePage"/>

    <main>
        <HelloLog v-if="page === 'helloLog'"/>
        <todo v-if="page === 'todo'"/>
        <weather v-if="page === 'weather'"/>

        <div v-if="page === ''" id="none">
            Please chose a page here ^
        </div>
    </main>
</template>

<style scoped>
    #none{
        position: absolute;
        right: 1vh;
    }
</style>