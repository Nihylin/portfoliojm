<template>
    <p>{{e.job_name}} chez {{e.company}}</p>
    <p>{{e.description}}</p>
    <p>{{e.city}}, {{e.start_year}} - {{e.end_year}}</p>
</template>

<script>
    export default {
        name:'ExpComponent',
        props:{
            e:Object
        }
    }
</script>

<style scoped>

</style>