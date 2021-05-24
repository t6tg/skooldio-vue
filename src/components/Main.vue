<template>
    <div>
        <!-- <Alert>
            <h1>Alert here...!!</h1>
            <p>Alert here...!!</p>
        </Alert> -->
        <todo-list :todoItems="todoItems"></todo-list>
        <input-todo></input-todo>
    </div>
</template>

<script>
import TodoList from './TodoList.vue'
import Alert from './Alert.vue'
import InputTodo from './InputTodo.vue'
export default {
    name: 'Main',
    components: {
        TodoList,
        Alert,
        InputTodo
    },
    data() {
        return {
            todoItems: [
                { id: 1, text: 'james1' },
                { id: 2, text: 'james2' },
                { id: 3, text: 'james3' }
            ]
        }
    }
}
</script>