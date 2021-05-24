<template>
    <div>
        <li v-for="todo in todoItems" :key="todo.id">
            <span>{{ todo.text }}</span>
        </li>
    </div>
</template>

<script>
export default {
    name: 'TodoList',
    props: {
        todoItems: {
            type: Array
        }
    },
    mounted() {
        console.log(this.todoItems)
    }
}
</script>
<style scoped >
.green {
    color: green;
}
.red {
    color: crimson;
}
</style>