<template>
    <div>
        <h1><slot></slot></h1>
    </div>
</template>

<script>
    export default {
        
    }
</script>

<style scoped>
    div {
        border: 1px solid blue;
        background-color: lightblue;
        padding: 30px;
        margin: 20px auto;
        text-align: center;
    }
</style>