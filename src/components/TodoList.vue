<template>
    <div>
        <h2>Hey, Ember.... Do This Stuff Today.</h2>
    </div>
</template>




<script>
import { todoItems } from "../data";
export default {
    data() {
        return {
            todos: [...todoItems],
        };
    },
};
</script>




<style scoped>
    h2 {
        color: teal;
    }
</style>