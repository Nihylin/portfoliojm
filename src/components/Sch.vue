<template>
    <p>{{s.name}}</p>
    <p>{{s.city}}, {{s.start_year}} - {{s.end_year}}</p>
</template>

<script>
    export default {
        name:'SchComponent',
        props:{
            s:Object
        }
    }
</script>

<style scoped>

</style>