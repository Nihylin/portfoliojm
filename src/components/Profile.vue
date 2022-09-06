<template>
  <section class="profile">
    <h2>Portfolio</h2>
    <div v-if="profile">
        <p>{{profile.firstname}}</p>
        <p>{{profile.lastname}}</p>
        <p>{{profile.phone}}</p>
        <p>{{profile.job}}</p>
        <p>{{profile.address.number}} {{profile.address.street}},</p>
        <p>{{profile.address.zipcode}} {{profile.address.city}}</p>
    </div>
  </section>
</template>

<script>
    import axios from 'axios';
    export default {
        name:'ProfileComponent',
        data: function(){
            return{
                profile:undefined
            }
        },
        methods :{
            getProfile(){
                axios.get('http://localhost:3000/profile')
                    .then(response => {
                        this.profile = response.data;
                        console.log(this.profile)
                    })
            }
        },
        mounted(){
            this.getProfile();
        }
    }
</script>

<style scoped>

</style>
