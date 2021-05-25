<template>
    <div id="app">
        <todo-list :items="sortedItem" @onItemDone="done"></todo-list>
        <input-form @onSave="save"></input-form>
    </div>
</template>

<script>
import TodoList from './components/TodoList.vue'
import InputForm from './components/InputForm.vue'
export default {
    name: 'App',
    components: {
        TodoList,
        InputForm
    },
    data() {
        return {
            items: []
        }
    },
    mounted() {
        this.items = JSON.parse(localStorage['todoItems'])
    },
    computed: {
        sortedItem() {
            return this.items
                .sort((a, b) => {
                    return b.time - a.time
                })
                .filter((r) => {
                    console.log(r)
                    return r.completed === false
                })
        }
    },
    methods: {
        done(id) {
            this.items.map((r) => {
                if (id === r.time) {
                    r.completed = true
                }
                return r
            })
            localStorage.setItem('todoItems', JSON.stringify(this.items))
        },
        save(text) {
            this.items.push({
                text: text,
                time: Date.now(),
                completed: false
            })
            localStorage.setItem('todoItems', JSON.stringify(this.items))
        }
    }
}
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
</style>
