<template>
    <div>
        <input type="text" v-model="text" />
        <button @click="save()">Save</button>
    </div>
</template>
<script>
export default {
    name: 'InputTodo'
}
</script>
<style scoped>
</style>