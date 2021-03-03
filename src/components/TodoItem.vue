<template>
    <div>
        <h3>{{ todo.name }} </h3>
        <button @click="handleClick" :class="{ completed: todo.complete }">{{ taskStatus }}</button>
    </div>
</template>



<script>
export default {
    props: ["todo"],
    methods: {
        handleClick() {
            this.$emit("status-change", this.todo);
        },
    },
    computed: {
        taskStatus() {
            return this.todo.complete ? "Mark Incomplete" : "Done!";
        }
    }
};
</script>


<style scoped>
    div {
        margin: 15px;
        padding: 10px;
        border: 3px solid teal;
        width: 20%;
    }

    button {
        padding: 10px;
        margin-bottom: 20px;
        color: white;
        border-radius: 12px;
        background-color: teal;
        border: teal;
    }

    .completed {
        background-color: darkgray;
        border: darkgray;
    }
</style>