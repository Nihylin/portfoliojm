<template>
  <Profile/>
  <Skills/>
  <Experience/>
  <School/>
  <Interests/>
</template>

<script>
import Profile from './components/Profile.vue';
import Interests from './components/Interests.vue';
import Skills from './components/Skills.vue';
import Experience from './components/Experience.vue';
import School from './components/School.vue';

export default {
  name: 'App',
  components: {
    Profile,
    Interests,
    Skills,
    Experience,
    School
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
