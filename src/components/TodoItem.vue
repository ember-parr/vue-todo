<template>
    <div>
        <h3>{{ todo.name }} </h3>
        <button @click="handleClick" class="btnComplete">Done</button>
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
    }

    .btnComplete {
        background-color: teal;
        border: teal;
    }

    .btnIncomplete {
        background-color: maroon;
        border: maroon;
    }
</style>