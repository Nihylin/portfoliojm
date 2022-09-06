<template>
    <h2>Compétences</h2>
    <div v-if="skills">
        <div v-for="s in skills" :key="s.id">
            <p>{{s.name}} :</p>
            <p>Niveau {{s.level}}</p>
        </div>
    </div>
</template>

<script>
    import axios from 'axios';
    export default {
        name:'SkillsComponent',
        data: function(){
            return{
                skills:undefined
            }
        },
        methods :{
            getSkills(){
                axios.get('http://localhost:3000/skills')
                    .then(response => {
                        this.skills = response.data;
                        console.log(this.skills)
                    })
            }
        },
        mounted(){
            this.getSkills()
        }
    }
</script>

<style scoped>

</style>