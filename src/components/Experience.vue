<template>
    <h2>Experience</h2>
    <div v-if="exp">
        <div v-for="e in exp" :key="e.id">
            <p>{{e.job_name}} chez {{e.company}}</p>
            <p>{{e.description}}</p>
            <p>{{e.city}}, {{e.start_year}} - {{e.end_year}}</p>
        </div>
    </div>
</template>

<script>
    import axios from 'axios';
    export default {
        name:'ExperienceComponent',
        data: function(){
            return{
                exp:undefined
            }
        },
        methods :{
            getExp(){
                axios.get('http://localhost:3000/experience')
                    .then(response => {
                        this.exp = response.data;
                        console.log(this.exp)
                    })
            }
        },
        mounted(){
            this.getExp()
        }
    }
</script>

<style scoped>

</style>