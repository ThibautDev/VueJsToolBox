<script setup>
import HeaderApp from './assets/header.vue'
import Todo from './components/todo.vue'
import HelloLog from './components/helloLog.vue'
import { ref } from 'vue'

const page = ref('todo');

function changePage(value) {
    page.value = value;
}
</script>

<template>
    <HeaderApp @updatepage="changePage"/>

    <main>
        <HelloLog v-if="page === 'helloLog'"/>
        <todo v-if="page === 'todo'"/>

        <div v-if="page === ''" id="none">
            Please chose a page here ^
        </div>
    </main>
</template>

<style scoped>
    main{
        margin-top: 3em;
    }

    #none{
        position: absolute;
        right: 1vh;
    }
</style>