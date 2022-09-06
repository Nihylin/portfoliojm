<template>
    <h2>Experience</h2>
    <div v-if="exp">
        <div v-for="e in exp" :key="e.id">
            <Exp :e="e"/>
        </div>
    </div>
</template>

<script>
    import axios from 'axios';
    import Exp from './Exp.vue';
    export default {
    name: "ExperienceComponent",
    data: function () {
        return {
            exp: undefined
        };
    },
    methods: {
        getExp() {
            axios.get("http://localhost:3000/experience")
                .then(response => {
                this.exp = response.data;
                console.log(this.exp);
            });
        }
    },
    mounted() {
        this.getExp();
    },
    components: { Exp } 
}
</script>

<style scoped>

</style>