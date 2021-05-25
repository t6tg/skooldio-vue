<template>
    <ul>
        <li v-for="item in items" :key="item.time">
            <button @click="done(item.time)">Done</button>{{ item.text }}
        </li>
    </ul>
</template>

<script>
export default {
    name: 'TodoList',
    props: {
        items: {
            type: Array
        }
    },
    methods: {
        itemDone(id) {
            this.$emit('onItemDone', id)
        }
    }
}
</script>