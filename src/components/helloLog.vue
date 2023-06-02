<template>
    <button @click="helloLog()">Say hello to log</button>
</template>

<script>
export default {
    methods: {
        helloLog() {
            console.log("hello log");
        }
    }
};
</script>

<style scoped>

</style>