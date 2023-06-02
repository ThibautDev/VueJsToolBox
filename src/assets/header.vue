<template>
    <header>
        <div>
            <span>Vue tool box</span>
        </div>
        <div>
            <span @click="changePage('todo')">Todo</span>
            <span @click="changePage('helloLog')">HelloLog</span>
        </div>
    </header>
</template>

<script>
export default {
    methods: {
        changePage(value) {
            this.$emit('updatepage', value);
        }
    }
};
</script>


<style scoped>
header {
    color: var(--c4);
    background-color: var(--c3);

    position: absolute;
    inset: 0;
    height: 2.5em;

    display: flex;
    justify-content: space-between;
}

header > div{
    margin-block: auto;
    margin-inline: 1vh;
    font-variation-settings: 'wght' 700;
}

header > div:first-child > span {
    font-size: 2em;
}

header > div:last-child > span{
    padding-inline: 0.5vh;
    margin-left: 3px;
    border-radius: 5px;

    text-decoration: underline;
}
header > div:last-child > span:hover{
    animation: pagesHover 0.2s forwards;
    cursor: pointer;
}
header > div:last-child > span:not(:hover){
    animation: pagesNotHover 0.2s forwards;
}
@keyframes pagesHover {
    to {
        color: var(--c1);
        background-color: var(--c2);
        text-decoration: none;
    }
}
@keyframes pagesNotHover {
    from {
        color: var(--c1);
        background-color: var(--c2);
        text-decoration: none;
    }
}


</style>