<template>
    <h2>Formations</h2>
    <div v-if="school">
        <div v-for="s in school" :key="s.id">
            <p>{{s.name}}</p>
            <p>{{s.city}}, {{s.start_year}} - {{s.end_year}}</p>
        </div>
    </div>
</template>

<script>
    import axios from 'axios';
    export default {
        name:'SchoolComponent',
        data: function(){
            return{
                school:undefined
            }
        },
        methods :{
            getSchool(){
                axios.get('http://localhost:3000/school')
                    .then(response => {
                        this.school = response.data;
                        console.log(this.school)
                    })
            }
        },
        mounted(){
            this.getSchool()
        }
    }
</script>

<style scoped>

</style>