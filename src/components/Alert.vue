<template>
    <div class="alert">
        <slot></slot>
    </div>
</template>

<script>
export default {}
</script>
<style scoped>
.alert {
    border: 1px solid red;
    padding: 10px;
}
</style>