<template>
    <main>
        <input type="text"  placeholder="New task" v-model="taskInput">
        <button @click="newTask()">send</button>
        <div>
            <span v-for="(todo, index) in todo" :key="index">
                {{ todo }} <button @click="checkTask(index)">X</button>
                <br>
            </span>
        </div>
    </main>
</template>

<script>
export default {
    data() {
        return {
            todo: [],
            taskInput: '',
        }
    },
    methods: {
        newTask() {
            this.todo[this.todo.length] = this.taskInput;
            this.taskInput = '';
            console.log(this.todo);
        },
        checkTask(index) {
            this.todo.splice(index, 1);
            console.log(this.todo);
        }
    }
};
</script>