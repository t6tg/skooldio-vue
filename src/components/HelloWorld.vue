<template>
    <div>
        <li v-for="todo in sortItem" :key="todo.id">
            <span
                v-show="todo.id !== 2"
                :class="{ red: todo.id === 3, green: todo.id === 1 }"
                :style="{ color: color }"
                >{{ todo.text }}</span
            >
            <img :src="image" alt="image" width="100" />
        </li>
        <input type="button" @click="save2" value="save" />
    </div>
</template>

<script>
export default {
    name: 'HelloWorld',
    watch: {
        todos(oldVal, newVal) {
            console.log(oldVal, newVal)
        }
    },
    beforeCreate() {
        console.log('BeforeCreate')
    },
    mounted() {
        console.log('mouted!!!')
    },
    computed: {
        sortItem() {
            return this.todos.sort((a, b) => {
                b.id - a.id
            })
        }
    },
    updated() {
        console.log('update!!')
    },
    methods: {
        save() {
            console.log('save')
        },
        save2() {
            this.save()
        }
    },
    filters: {
        capitalize(val) {
            return val.toUpperCase()
        }
    },
    data() {
        return {
            name: '',
            todos: [
                { id: 4, text: 'james7' },
                { id: 2, text: 'james2' },
                { id: 3, text: 'jame3' }
            ],
            color: '#ff00ff',
            image:
                'https://upload.wikimedia.org/wikipedia/commons/thumb/b/b6/Image_created_with_a_mobile_phone.png/1200px-Image_created_with_a_mobile_phone.png'
        }
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