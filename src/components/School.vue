<template>
  <section class="school">
    <h2>Formations</h2>
    <div v-if="school">
        <div v-for="s in school" :key="s.id">
            <Sch :s="s"/>
        </div>
    </div>
  </section>
</template>

<script>
    import axios from 'axios';
import Sch from './Sch.vue';
    export default {
    name: "SchoolComponent",
    data: function () {
        return {
            school: undefined
        };
    },
    methods: {
        getSchool() {
            axios.get("http://localhost:3000/school")
                .then(response => {
                this.school = response.data;
                console.log(this.school);
            });
        }
    },
    mounted() {
        this.getSchool();
    },
    components: { Sch }
}
</script>

<style scoped>

</style>
