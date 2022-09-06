<template>
    <h2>Centres d'intérêt</h2>
    <div v-if="interests">
        <div v-for="i in interests" :key="i.id">
            <p>{{i}}</p>
        </div>
    </div>
</template>

<script>
    import axios from 'axios';
    export default {
        name:'InterestsComponent',
        data: function(){
            return{
                interests:undefined
            }
        },
        methods :{
            getInterests(){
                axios.get('http://localhost:3000/interests')
                    .then(response => {
                        this.interests = response.data;
                        console.log(this.interests)
                    })
            }
        },
        mounted(){
            this.getInterests()
        }
    }
</script>

<style scoped>

</style>